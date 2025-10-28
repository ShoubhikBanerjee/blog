---
title: "How I Built Lightning-Fast Vector Search for Legal Documents"
description: "A comprehensive guide to building high-performance semantic search over 143,485
legal document segments using vector embeddings, optimization techniques, and CPU-based
indexing."
date: 2025-10-28T00:45:06.055750+05:30
tags: ["vector-search", "embeddings", "legal-technology", "semantic-search", "usearch", "isaacus", "performance-optimization", "rag", "simd", "hnsw"]
categories: ["Machine Learning", "Information Retrieval", "Legal Technology"]
image: "https://cdn-uploads.huggingface.co/production/uploads/65839aaab6a60815eefed378/RPd8hpWDbLMKzhy5p5iee.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# ⚡ How I Built Lightning-Fast Vector Search for Legal Documents

![API Terms Comparison](https://cdn-uploads.huggingface.co/production/uploads/65839aaab6a60815eefed378/RPd8hpWDbLMKzhy5p5iee.png)
*Comparison of embedding API provider terms and data usage policies*

I wanted to see if I could build semantic search over a large legal dataset — specifically,
every High Court decision in Australian legal history up to 2023, chunked down to 143,485
searchable segments. Not because anyone asked me to, but because the combination of scale and
domain specificity seemed like an interesting technical challenge. Legal text is dense,
context-heavy, and full of subtle distinctions that keyword search completely misses. Could
vector search actually handle this at scale and stay fast enough to be useful?

I'll walk you through what I learned testing different embedding providers, the performance
benchmarks that surprised me, the code for actually implementing this with
[USearch](https://github.com/unum-cloud/usearch) and [Isaacus embeddings](https://isaacus.com),and, most importantly, why you need to read the fine print on embedding API terms before you
feed them anything you care about.

## 🔍 Choosing an API Provider (Or Going Local?)

Before diving into implementation, I spent some time doing what every developer should do but
most don't: actually reading the Terms of Service for various embedding API providers. What I
found was... sobering. With some help from Claude, I got this comparison table:

**Correction**: *I've been informed that Google, even for paid individual users will train on
your data. For Google Workspace users (at least in the USA), they will not.*

Now, I'm not trying to throw shade at any specific provider — these are all legitimate
businesses with different business models and constraints. But if you're working with legal
documents, medical records, or anything remotely sensitive, these terms matter a lot. Some
providers explicitly claim rights to train on your data, and even may share it or sell it to
third parties under different terms. Others require you to opt out manually, which means your
data is fair game by default. And in a few cases, free tier users get no protection at all.

The standout for me was [Isaacus](https://isaacus.com), which doesn't train on user data unless
you explicitly provide feedback, allows benchmarking, and protects free users. (Full disclosure:
 I'm working with them so I may be a little biased. But even I wasn't, those terms would matter a lot to me.)

## 🏠 So, Why Not Just Go Local?

You might be thinking: "Why deal with API terms at all? Just run embeddings locally." That's
actually a completely reasonable approach, especially for sensitive data. You get full control,
no data leaves your infrastructure, and you're not at the mercy of rate limits or pricing changes.

The trade-off is quality and convenience. Some of the best-performing embedding models are
proprietary and only available through APIs.

For this project, I'm testing several approaches. On the API side, I'm comparing Isaacus,
OpenAI, Voyage AI (with opt-out enabled), and Google Gemini — all using their best models at
maximum embedding dimensions. I picked these because they either have reasonable terms or, in
Voyage's case, at least let you opt out of training (but you must do this from the get-go, the
opt-out won't retroactively apply to any data you've already submitted). I'll also show you
performance results from a small and fast local model I fine-tuned myself: a sentence-transformers model based on
[BAAI/bge-small-en](https://huggingface.co/BAAI/bge-small-en), trained specifically on High
Court of Australia case law from the Open Australian Legal Corpus... which happens to be the
exact dataset I'm searching through here.

Does this give my local model an unfair advantage? Absolutely. It was literally trained on the
data I'm now querying. But for this article, I'm focusing on speed and ease of implementation
(building reliable inference infrastructure for local models can be quite involved). The choice
of embedding model matters a lot and varies by use case, so you should run your own evaluations on your specific data.

## 🚀 Getting Embeddings Fast

### ⚡ Async All The Things (But Carefully)

When you're processing 143,000 text chunks, doing it sequentially would take... a long time. So
I went async, but with guardrails to avoid hammering the APIs and running into rate limits:

```python
# Process up to 5 batches concurrently
semaphore = asyncio.Semaphore(max_concurrent_batches)

async def process_batch(batch_texts):
    async with semaphore:  # Rate limiting embeddings = await embed_batch_async(batch_texts)
        return embeddings
```

This simple pattern gave me 3-5x speedup for API calls. For local models, async doesn't help
much (GPU compute is the bottleneck, not network I/O), but batching still works.

### 📊 The Speed Numbers

After implementing these optimizations, here's what the different providers look like in practice:

**Batch Processing Speed (1,000 legal documents):**
- Local Model (auslaw-embed, 384d): 924 texts/sec on a 32GB GPU
- OpenAI (text-embedding-3-large, 3072d): 184 texts/sec
- Isaacus (kanon-2-embedder, 1792d): 102 texts/sec
- Google (gemini-embedding-001, 3072d) 19.8 texts/sec
- Voyage AI (voyage-3-large, 2048d): 14 texts/sec (ouch)

**Single Query Latency (what one user experiences):**
- Local Model: 7ms average, 15ms p95*
- Google: 501.1ms average, 662.3ms p95
- OpenAI: 1,114ms average 1,723ms p95
- Isaacus: 1,532ms average, 2,097ms p95
- Voyage AI: 1,693ms average, 7,657ms p95

Note: these timings are during Australian business hours (relevant for my use-case). For
off-shore providers (OpenAI, Google and Voyage) you can tack on ~80% to those times during on-peak hours.

*p95 means "95th percentile" — basically, 95% of requests are faster than this. It's a better
measure than average because it shows you what your slower requests look like, which matters for user experience.*

The tiny local model absolutely crushes the APIs on speed — 5x faster for batches, 70x faster
for single queries. But here's the catch, it's using 384-dimensional embeddings vs 1792-3072 for
 the APIs. That dimension difference matters for search quality, which is why I'm focusing on
the API providers for this article.

A few surprises:
- Voyage's throttling is painful:14 texts/sec on a paid API is rough
- Google doesn't benefit from async: seems to process sequentially anyway
- OpenAI is remarkably consistent: lowest variance despite being network-based
- Isaacus hits a nice middle ground: good speed for the dimensionality

## 🧩 Embedding Legal Texts with Isaacus

After testing all the providers, I will focus on Isaacus for the deep dive. The
[kanon-2-embedder](https://isaacus.com) embeddings are also such that first dimensions carry
most of the information allowing us to do some interesting things.

Here's how simple it is to generate embeddings with Isaacus and save them for later use. You
will need to install the required packages first and will need Python ≥3.8.

```bash
pip install isaacus numpy
```

```python
import asyncio import numpy as np
from isaacus import AsyncClient import os

async def generate_embeddings():
    """Generate embeddings for your legal corpus using Isaacus API."""

    # Initialize the async client (API key from environment) client = AsyncClient(api_key=os.getenv("ISAACUS_API_KEY"))

    # Your corpus and queries corpus_texts = ["The High Court of Australia...", ...]  # 143,485 docs
    queries = ["What is the highest court?", ...]  # Your queries

    # Generate corpus embeddings with task-aware encoding corpus_response = await client.embed(
        model="kanon-2-embedder", inputs=corpus_texts,
        task="retrieval/document"  # Tell model these are documents )
    corpus_embeddings = np.array(corpus_response.embeddings, dtype=np.float32)

    # Generate sample query embeddings with task-aware encoding query_response = await client.embed(
        model="kanon-2-embedder", inputs=queries,
        task="retrieval/query"  # Tell model these are queries )
    query_embeddings = np.array(query_response.embeddings, dtype=np.float32)

    # Create an embeddings dir if it doesn't exist os.makedirs("embeddings", exist_ok=True)

    # Save to disk for later use np.save("embeddings/corpus_embeddings.npy", corpus_embeddings)
    np.save("embeddings/query_embeddings.npy", query_embeddings)

    await client.close()

# Run it
asyncio.run(generate_embeddings())
```

That's it! The embeddings are now saved and ready for optimisation.

## ✨ The 256-Dimension Magic

Isaacus embeddings are 1792-dimensional, but they're trained with a special property where the
first dimensions carry the most information (think principal components). This means we can
truncate to just 256 dimensions and still maintain surprisingly good search quality:

```python
# Load the full embeddings we saved
corpus_embeddings = np.load("embeddings/corpus_embeddings.npy")

# Use only the first 256 dimensions
corpus_256d = corpus_embeddings[:, :256].astype(np.float32)
```

Which results in...
- 8.6x faster searches (459 q/s vs 53 q/s)
- 7x less memory (140 MB vs 1,028 MB)
- 61% recall@10† (vs 100% for full dimensions — explained below)
- 57% recall@50

Important context on these numbers: The recall percentages here are relative to a synthetic
baseline, not absolute retrieval quality. Here's what I did:

1. I used the exact same documents as both corpus and queries (143K documents querying against themselves)
2. The "perfect" 100% baseline is full 1792-dimensional exact search — each document finding itself as the top result
3. The 61% and 57% numbers show how much information is lost when optimizing with 256 dimensions

This is a benchmark of information loss from optimisation, not real-world retrieval quality. For
 actual legal search quality, you'd need human-labelled test sets (like the [MLEB
benchmark](https://arxiv.org/abs/2406.14928)).

Why this still matters: It tells you that the optimizations preserve about 60% of the ranking
order. The "missing" 40% aren't wrong results, they're just ranked differently. For RAG where
you're pulling 50-100 chunks anyway, this is often perfectly fine.

*†Recall@10 means "what percentage of the true top-10 results did we actually find?" Recall@50
is lower here because this test uses self-matching over identical documents — as k grows, there
are more "perfect" matches to retrieve, so missing any lowers the recall fraction.*

### 🔥 USearch: From 53 to 2,880 Queries per Second (on Just a CPU!)

Now for the fun part. Most vector search tutorials will tell you to use FAISS or Pinecone and
build approximate indexes. But I wanted something different: great results when I need them,
blazing speed when I don't, and critically no GPU is required.

Enter [USearch](https://github.com/unum-cloud/usearch). It's a lesser-known library that
delivers both exact and approximate search through SIMD optimization (basically, modern CPU
instructions that process multiple data points at once). The killer feature? Everything runs on CPU, which means:

- Way cheaper deployment: no expensive GPU instances needed
- Easier scaling: just add more CPU cores
- Lower complexity: no CUDA drivers, no GPU memory management
- Still insanely fast: thanks to SIMD vectorisation

For a legal search system running 24/7, avoiding GPUs can cut infrastructure costs by 70-80%
while still delivering sub-millisecond response times. That's a game-changer.

You can install it with:

```bash
pip install usearch
```

**Level 1: Just Use More Cores**

```python
# Batch with multi-threading
matches = search(corpus, queries, 100, MetricKind.Cos, exact=True, threads=8)
# Result: 374 q/s (7x speedup from single-threaded)
```

**Level 2: Build an HNSW Index**

For workloads where you query more than you update, building an index pays off:

```python
from usearch.index import Index

index = Index( ndim=1792,
    metric=MetricKind.Cos, connectivity=32,  # Higher = better quality, more memory
    expansion_add=200,  # Build quality expansion_search=100  # Search quality
)

# Build once (214 seconds)
for i, embedding in enumerate(corpus_embeddings):
    index.add(i, embedding)

# Search many times (blazing fast)
matches = index.search(query, 100)
# Result: 993 q/s with 98.6% recall@10
```

HNSW (Hierarchical Navigable Small World graphs) is basically a clever data structure that lets
you find approximate nearest neighbours way faster than brute force, while still being super accurate.

**Level 3: The Full Stack**

Combining 256d reduction, HNSW indexing, and half-precision storage:

```python
# Prepare 256d embeddings in half precision
corpus_256d = corpus_embeddings[:, :256].astype(np.float16)

index = Index( ndim=256,
    metric=MetricKind.Cos, dtype="f16",  # Half precision saves 2x memory
    connectivity=32, expansion_add=200,
    expansion_search=100 )

# Build (59 seconds for 143K docs)
for i, emb in enumerate(corpus_256d):
    index.add(i, emb)
```

Final numbers:
- 2,880 queries/sec (54x faster than baseline!)
- 0.35ms per query (sub-millisecond!)
- 70 MB total (14.7x memory reduction)
- 61% recall@10 (still good enough for RAG)

### 📈 The Complete Performance Ladder

![Performance Comparison Chart](https://cdn-uploads.huggingface.co/production/uploads/65839aaab6a60815eefed378/czppJH5L3QKob3V8Z8jml.png)
*Complete performance comparison across different optimization levels*

Reminder: these are relative to 1792-dimensional exact search on the same corpus. These measure
optimisation trade-offs, not absolute retrieval quality. For legal-specific retrieval
benchmarks, see [MLEB](https://arxiv.org/abs/2406.14928).

**Baseline system (53 q/s):**
- 1 user: 19ms (fine)
- 100 concurrent users: 1.9 seconds (not that great)
- 1,000 users: 19 seconds (really, really bad)

**Optimised system (2,880 q/s):**
- 1 user: 0.35ms
- 100 concurrent users: 35ms
- 1,000 concurrent users: 347ms
- 10,000 concurrent users: 3.5s

The optimised system can handle serious traffic on a single machine.

## ⚙️ Choosing Your Configuration

The right choice depends on your requirements:

**Use "accuracy" mode (baseline + multi-threading) when:**
- Legal compliance requires perfect recall
- You're doing careful research, not RAG
- Corpus is small enough (<100K docs)

**Use "balanced" mode (HNSW, full dimensions) when:**
- You need near-perfect results (>95% recall)
- Building a production legal search tool
- Can afford 3-4 minutes of index build time
- This is my recommendation for legal applications

**Use "speed" mode (full stack) when:**
- Building consumer-facing applications
- Memory is very limited (<200MB for index)
- Using RAG with reranking (60% recall is fine as first pass)
- Need to handle thousands of concurrent users

## 💻 Production-Ready Code

Here's the full implementation you can adapt:

```python
import numpy as np from usearch.index import Index, search, MetricKind
from pathlib import Path from typing import Optional, Union, List
import time

class OptimizedLegalSearch:
    def __init__( self,
        corpus_embeddings: np.ndarray,
        optimization_level: str = "balanced",
        save_path: Optional[str] = None
    ):
        """ Initialize the search system.

        Args:
            corpus_embeddings: Corpus embeddings (N × D array)
            optimization_level: One of "accuracy", "balanced", or "speed"
            save_path: Optional path to save/load index
        """ self.corpus_embeddings = corpus_embeddings
        self.optimization_level = optimization_level self.save_path = save_path
        self.index = None

        # Configure based on optimization level if optimization_level == "speed":
            # Maximum speed: 256d + HNSW + f16 print("Configuring for maximum speed (256d + HNSW + f16)...")
            self.use_dimensions = 256 self.use_index = True
            self.dtype = "f16" self.connectivity = 32
            self.expansion_add = 200 self.expansion_search = 100

        elif optimization_level == "balanced":
            # Balanced: Full dimensions + HNSW print("Configuring for balanced speed/quality (HNSW M=32)...")
            self.use_dimensions = None  # Use all dimensions self.use_index = True
            self.dtype = "f32" self.connectivity = 32
            self.expansion_add = 200 self.expansion_search = 100

        elif optimization_level == "accuracy":
            # Maximum accuracy: Full dimensions, exact search
            print("Configuring for maximum accuracy (exact search)...") self.use_dimensions = None
            self.use_index = False self.dtype = "f32"
        else:
            raise ValueError(f"Unknown optimization level: {optimization_level}")

        # Prepare corpus self._prepare_corpus()

        # Build or load index if needed if self.use_index:
            if save_path and Path(save_path).exists():
                self.load_index(save_path) else:
                self._build_index() if save_path:
                    self.save_index(save_path)

    def _prepare_corpus(self):
        """Prepare corpus embeddings based on optimization settings.""" if self.use_dimensions:
            # Truncate to specified dimensions self.corpus_processed = self.corpus_embeddings[:, :self.use_dimensions]
            if self.dtype == "f16":
                self.corpus_processed = self.corpus_processed.astype(np.float16) else:
                self.corpus_processed = self.corpus_processed.astype(np.float32)
            print(f"Corpus reduced to {self.use_dimensions} dimensions") else:
            self.corpus_processed = self.corpus_embeddings.astype(np.float32)
            print(f"Using full {self.corpus_embeddings.shape[1]} dimensions")

        # Ensure contiguous memory for SIMD optimization
        self.corpus_processed = np.ascontiguousarray(self.corpus_processed)

    def _build_index(self):
        """Build HNSW index for fast approximate search."""
        ndim = self.use_dimensions or self.corpus_embeddings.shape[1]
        print(f"Building HNSW index (M={self.connectivity}, ef={self.expansion_search})...")

        start_time = time.time() self.index = Index(
            ndim=ndim, metric=MetricKind.Cos,
            dtype=self.dtype, connectivity=self.connectivity,
            expansion_add=self.expansion_add, expansion_search=self.expansion_search
        )

        # Add vectors to index with progress tracking n_docs = len(self.corpus_processed)
        for i, embedding in enumerate(self.corpus_processed):
            self.index.add(i, embedding) if (i + 1) % 10000 == 0:
                print(f"  Indexed {i+1}/{n_docs} documents...")

        build_time = time.time() - start_time print(f"Index built in {build_time:.1f} seconds")

        # Report memory usage memory_mb = self.index.size * (2 if self.dtype == "f16" else 4) / (1024 * 1024)
        print(f"Index memory usage: {memory_mb:.1f} MB")

    def search( self,
        query_embeddings: Union[np.ndarray, List[np.ndarray]],
        k: int = 100,
        return_scores: bool = False
    ) -> Union[np.ndarray, List[np.ndarray]]:
        """ Search for top-k similar documents.

        Args:
            query_embeddings: Query vector(s) - can be single or batch
            k: Number of results to return
            return_scores: Whether to return similarity scores

        Returns:
            Document indices (and optionally scores) for top-k matches """
        # Ensure numpy array if isinstance(query_embeddings, list):
            query_embeddings = np.vstack(query_embeddings)

        # Truncate query dimensions if needed if self.use_dimensions:
            if len(query_embeddings.shape) == 1:
                query_processed = query_embeddings[:self.use_dimensions] else:
                query_processed = query_embeddings[:, :self.use_dimensions] else:
            query_processed = query_embeddings

        # Ensure float32 for queries (better precision) query_processed = query_processed.astype(np.float32)

        if self.use_index:
            # HNSW approximate search if len(query_processed.shape) == 1:
                # Single query matches = self.index.search(query_processed, k)
                if return_scores:
                    return matches.keys, matches.distances return matches.keys
            else:
                # Batch queries results_keys = []
                results_scores = [] for q in query_processed:
                    matches = self.index.search(q, k) results_keys.append(matches.keys)
                    if return_scores:
                        results_scores.append(matches.distances)

                if return_scores:
                    return results_keys, results_scores return results_keys
        else:
            # Exact search with multi-threading matches = search(
                self.corpus_processed, query_processed,
                k, MetricKind.Cos,
                exact=True, threads=8  # Use 8 threads for parallel processing
            )

            if return_scores:
                return matches.keys, matches.distances return matches.keys

    def save_index(self, path: str):
        """Save HNSW index to disk for fast loading.""" if self.index:
            print(f"Saving index to {path}...") self.index.save(path)

            # Also save metadata import json
            metadata = { "optimization_level": self.optimization_level,
                "use_dimensions": self.use_dimensions, "dtype": self.dtype,
                "connectivity": self.connectivity, "expansion_add": self.expansion_add,
                "expansion_search": self.expansion_search, "corpus_size": len(self.corpus_processed)
            }

            with open(f"{path}.meta.json", "w") as f:
                json.dump(metadata, f, indent=2)

            print("Index saved successfully")

    def load_index(self, path: str):
        """Load pre-built HNSW index from disk.""" print(f"Loading index from {path}...")
        self.index = Index.restore(path)

        # Load metadata if available import json
        meta_path = f"{path}.meta.json" if Path(meta_path).exists():
            with open(meta_path, "r") as f:
                metadata = json.load(f)
            print(f"Loaded {metadata['optimization_level']} index with {metadata['corpus_size']} documents")

# Example usage
if __name__ == "__main__":
    # Load your embeddings corpus_embeddings = np.load("embeddings/corpus_embeddings.npy")

    # Load your queries, if stored similarly query_embeddings = np.load("embeddings/query_embeddings.npy")

    # Create search system with desired optimization searcher = OptimizedLegalSearch(
        corpus_embeddings, optimization_level="balanced",  # or "speed" or "accuracy"
        save_path="indices/legal_search.index" )

    # Search for similar documents results = searcher.search(query_embeddings[0], k=100)
    print(f"\nFound {len(results)} similar documents")
```

A minimal query workflow would be as simple as:

```python
query = "What is the doctrine of precedent?"
query_emb = client.embed(model="kanon-2-embedder", inputs=[query], task="retrieval/query")
results = searcher.search(np.array(query_emb.embeddings[0]), k=5) print(results)
```

## 🎯 The Bottom Line

For legal search specifically, I'd probably stick with the "balanced" configuration — 993 q/s
with 98.6% recall@10 is plenty fast while maintaining near-perfect accuracy. But for general RAG
 applications where you're pulling 50+ chunks and reranking anyway, the fully optimised "speed"
mode at 2,880 q/s is incredibly compelling.

A 61% recall system that responds in 0.35ms often beats a 100% recall system that takes 19ms,
especially when your retrieval is just the first stage of a multi-step pipeline.

Now you can build your own performant legal search engine!

--- 
## 🙌 Credits

*Originally posted at:
https://huggingface.co/blog/adlumal/lightning-fast-vector-search-for-legal-documents*

## ✅ Final Thoughts

This project demonstrates that high-performance vector search doesn't require expensive GPU
infrastructure or complex distributed systems. By carefully choosing embedding providers with
reasonable terms, optimizing dimensions intelligently, and leveraging CPU-based SIMD operations,
 you can build production-ready semantic search that scales to hundreds of thousands of
documents while maintaining sub-millisecond response times.

The key insights are threefold: first, always read the fine print on API terms before processing
 sensitive data; second, dimension reduction can provide dramatic performance gains with
acceptable quality trade-offs for many use cases; and third, modern CPU-based vector search
libraries like USearch can deliver exceptional performance without the complexity and cost of GPU deployments.

Whether you're building legal document search, medical record retrieval, or any domain-specific
semantic search system, these techniques provide a practical path to production deployment that
balances speed, accuracy, and infrastructure costs.

_#VECTORSEARCH #LEGALTECHNOLOGY #EMBEDDINGS #ISAACUS #USEARCH #SEMANTICSEARCH #RAG
#PERFORMANCEOPTIMIZATION #MACHINELEARNING #AI_

