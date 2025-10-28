---
title: "Australian-made LLM beats OpenAI and Google at legal retrieval"
description: "Isaacus launches Kanon 2 Embedder, achieving 9% higher accuracy than OpenAI and 6% higher than Google in legal information retrieval while running 30% faster."
date: 2025-10-28T00:56:04.405046+05:30
tags: ["Legal AI", "LLM", "Embeddings", "RAG", "Australia", "Kanon 2", "MLEB", "Legal Tech", "Information Retrieval", "Benchmark"]
categories: ["Artificial Intelligence", "Legal Technology", "Machine Learning"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6497ffbf2a997a45e987e139/W-d5QjuF-f9CYUctuHleg.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🇦🇺 Australian-made LLM beats OpenAI and Google at legal retriev

![MLEB score vs inference time](https://cdn-uploads.huggingface.co/production/uploads/6497ffbf2a997a45e987e139/W-d5QjuF-f9CYUctuHleg.png)
*Performance comparison showing MLEB scores versus inference time for various embedding models*

**Isaacus**, an Australian foundational legal AI startup, has launched **Kanon 2 Embedder**, a
state-of-the-art legal embedding LLM, and unveiled the **Massive Legal Embedding Benchmark
(MLEB)**, an open-source benchmark for evaluating legal information retrieval performance across
 six jurisdictions (the US, UK, EU, Australia, Singapore, and Ireland) and five domains (cases,
statutes, regulations, contracts, and academia).

Kanon 2 Embedder ranks first on MLEB as of 23 October 2025, delivering **9% higher accuracy than
 OpenAI Text Embedding 3 Large** and **6% higher accuracy than Google Gemini Embedding** while
running **>30% faster** than both LLMs. Kanon 2 Embedder leads a field of 20 LLMs, including
Qwen3 Embedding 8B, IBM Granite Embedding R2, and Microsoft E5 Large Instruct.

> "The quality of search results sets the ceiling for legal RAG applications", said Umar Butler,
 founder of Isaacus. "Kanon 2 Embedder raises that ceiling, dramatically."

## ⚖️ Why it matters

Embedding models convert documents and queries into sets of numbers known as 'embeddings' that
can be compared with each other to identify relevant search results.

Embeddings power the 'retrieval' component of retrieval-augmented generation (RAG) applications
and are widely used across the legal tech industry, including by Harvey, LexisNexis, and Relativity.

In legal RAG applications, low-quality embeddings lead to low-quality search results, which in
turn lead to low-quality responses and increased hallucinations.

Despite their importance, limited attention has been paid to ensuring that embedding models are
genuinely fit for legal information retrieval.

## 🏆 A new gold standard for legal information retrieval

Isaacus believes **MLEB is the most comprehensive and diverse legal embedding benchmark to
date**. It spans multiple countries, document types, and areas of law. Every dataset in MLEB has
 been curated and vetted by domain experts.

On MLEB, legal-tuned LLMs consistently outperform similar-sized general-purpose LLMs. The
top-ranked Kanon 2 Embedder is derived from **Kanon 2, a new legal foundation model trained on
millions of laws, regulations, cases, contracts, and papers from 38 jurisdictions**. The second-
 and third-best LLMs—Voyage 3 Large and Voyage 3.5—were also optimized for law, possibly thanks
to Voyage's (owned by MongoDB) partnership with Harvey.

### 🎯 Key achievements

1. **Kanon 2 Embedder ranks first on MLEB** while running **340% faster** and being several
times smaller than the second-ranked LLM, Voyage 3 Large.
2. MLEB covers decisions, laws, regulations, contracts, and textbooks across the US, UK,
Australia, Singapore, and Ireland.

Isaacus hopes Kanon 2 Embedder and MLEB will **elevate the quality of legal retrieval globally**
 by setting a new gold standard for what superior legal search capabilities and benchmarks look like.

## 🔐 Respecting legal data sovereignty

Isaacus takes the sensitivity of legal data seriously. Unlike others in the embeddings space
(see, for example, Voyage, Cohere, and Jina), Isaacus has chosen to not opt businesses into
using their private data for training by default.

Additionally, for customers with heightened privacy, security, or reliability concerns, Isaacus
will soon be offering air-gapped model deployment containers on AWS Marketplace and Microsoft Marketplace.

## 🚀 Available today

Isaacus is inviting the legal tech industry to try Kanon 2 Embedder for themselves and see
whether it delivers superior retrieval results for their own use cases. They can do so by
following the quick start guide on the Isaacus docs.

Enterprises interested in private AWS and Azure deployments should follow Isaacus on LinkedIn to
 get updated in the next few weeks on the release of their AWS Marketplace and Microsoft Marketplace products.

Isaacus has also made the data and code behind MLEB openly and freely available on Hugging Face
and GitHub. The MLEB leaderboard is hosted on their website, as is a full writeup of their
methodology, soon to be released as a paper.

*Note: since posting this, Jina AI has clarified to Isaacus that they are not training and have
not trained on user data.*

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/isaacus/kanon-2-embedder*

## 🏁 Conclusion

The emergence of Kanon 2 Embedder represents a significant milestone in legal AI technology,
demonstrating that specialized, domain-focused models can outperform general-purpose solutions
from tech giants. With its superior accuracy, faster inference times, and commitment to data
sovereignty, this Australian-made LLM sets a new benchmark for legal information retrieval.

The introduction of MLEB as a comprehensive evaluation framework will likely drive further
innovation in the legal AI space, encouraging the development of more specialized and effective
legal embedding models. For legal tech companies seeking to improve their RAG applications and
reduce hallucinations, Kanon 2 Embedder offers a compelling solution that prioritizes both performance and privacy.

*#LEGALAI #AUSTRALIA #RAG #EMBEDDINGS #MACHINELEARNING #LEGALTECH #ARTIFICIALINTELLIGENCE*

