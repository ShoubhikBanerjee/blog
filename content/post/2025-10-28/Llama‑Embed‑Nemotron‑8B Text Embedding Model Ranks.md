---
title: "Llama-Embed-Nemotron-8B Text Embedding Model Ranks First on Multilingual MTEB Leaderboard"
description: "NVIDIA's Llama-Embed-Nemotron-8B achieves state-of-the-art performance on
multilingual text embedding tasks, enabling developers to build smarter, language-aware search
and retrieval systems across diverse languages."
date: 2025-10-28T00:54:42.115354+05:30
tags: ["NVIDIA", "AI", "NLP", "Embedding", "Multilingual", "Machine Learning", "Hugging Face", "Retrieval", "Semantic Search", "MTEB"]
categories: ["AI", "Natural Language Processing", "Machine Learning"]
image: "NA"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 Llama-Embed-Nemotron-8B Text Embedding Model Ranks First on Multilingual MTEB Leaderboard

## 🌍 Build Smarter, Language-Aware Search and Retrieval Systems

As global information continues to expand across languages, developers face a growing challenge:
 how to make models understand text in dozens of languages with the same precision, nuance, and
semantic clarity. Traditional multilingual embedding models often struggle with alignment,
scalability, and consistent performance.

The NVIDIA Llama-Embed-Nemotron-8B model changes this. Built by fine-tuning the Llama-3.1-8B
foundation model, this embedding model applies cross-lingual representation learning to deliver
unified, high-fidelity embeddings across linguistically diverse content. Whether you're building
 cross-language retrieval systems, search engines, or conversational AI, this model helps close
the comprehension gap between languages – high-resource or low-resource alike.

This article provides an overview of the model's architecture, training methodology and
evaluation results, highlighting how it empowers developers to build more intelligent and
inclusive multilingual applications.

## ⚙️ Architectural Highlights

- **Base model:** 7.5B parameters, consisting of 32 hidden layers (hidden size dimension =
4,096).
- **Key innovation:** Replaces uni-directional causal attention with bi-directional
self-attention, enabling richer semantic understanding across the full token context.
- **Embedding output:** Global average pooling compresses token information into a
4,096-dimensional dense vector, optimized for semantic search and cross-lingual tasks.

This design allows the model to generate consistent embeddings regardless of input language or
structure — a crucial step when tackling multilingual retrieval or alignment problems.

## 🧠 Training Methodology

The model is trained using a bi-encoder architecture, independently encoding a pair of sentences
 (for example, query and passage) using the embedding model. Using contrastive learning, it
maximizes similarity between the query and the passage that contains the answer, while
minimizing it between the query and sampled negative passages that are not useful for answering the question.

### Training Data Mix (16M pairs):
- 8M from publicly available datasets: Nemotron-CC-v2, MIRACL, HotpotQA, MS MARCO, Natural
Questions, SQuAD, and more.
- 8M from synthetic datasets: Generated from open-source LLMs covering retrieval, semantic
similarity and classification problem types.

### Two-stage Training Pipeline:
- **Pre-training:** 11.5M query, document pairs curated from Nemotron-CC-v2 – NVIDIA's
state-of-the-art LLM pre-training dataset.
- **Fine-tuning:** 4.5M pairs combining public and high-quality synthetic datasets to refine
semantic precision.

We plan to open-source our multilingual data mix soon, and publish a detailed technical report
covering training dynamics and multilingual alignment.

## 📊 Performance Evaluation

We evaluate our model on the MMTEB Benchmark, specifically, on the main `MTEB (Multilingual,
v2)` split. It consists of 131 tasks across 9 task types and 1,038 languages. Ranking on the
MMTEB Leaderboards is performed based on the Borda rank. Each task is treated as a preference
voter, which gives votes on the models per their relative performance on the task. The best
model obtains the highest number of votes. The model with the highest number of votes across
tasks obtains the highest rank. The Borda rank tends to prefer models that perform well broadly across tasks.

Our model achieves **state-of-the-art performance** on the MMTEB Benchmark (as of October 21,
2025). Ranking list is presented below:

| Borda Rank | Model | Borda Votes | Mean (Task) |
| --- | --- | --- | --- |
| **1.** | llama-embed-nemotron-8b | **39,573** | 69.46 |
| 2. | gemini-embedding-001 | 39,368 | 68.37 |
| 3. | Qwen3-Embedding-8B | 39,364 | **70.58** |
| 4. | Qwen3-Embedding-4B | 39,099 | 69.45 |
| 5. | Qwen3-Embedding-0.6B | 37,419 | 64.34 |
| 6. | gte-Qwen2-7B-instruct | 37,167 | 62.51 |
| 7. | Linq-Embed-Mistral | 37,149 | 61.47 |

Modern applications — from document search to coding assistants — require embeddings that scale
and generalize. With Llama-Embed-Nemotron-8B, developers can:

- Build cross-language retrieval systems that align semantically across diverse alphabets and
syntax.
- Power multi-lingual QA and semantic similarity tasks without compromising accuracy.
- Leverage an open, high-performing model that integrates easily with existing Hugging Face
pipelines.

## 🔧 Try it Yourself

Deploy Llama-Embed-Nemotron-8B, or learn more about the NVIDIA NeMo Retriever family of Nemotron
 RAG models on the product page.

Stay up to date on NVIDIA Nemotron by subscribing to NVIDIA news and following NVIDIA AI on
LinkedIn, X, YouTube and the Nemotron channel on Discord.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/nvidia/llama-embed-nemotron-8b*

## ✅ Final Thoughts

The Llama-Embed-Nemotron-8B model represents a significant breakthrough in multilingual text
understanding, achieving top rankings on the MMTEB benchmark through innovative architectural
design and comprehensive training methodology. Its bi-directional attention mechanism and
extensive multilingual training data make it an ideal choice for developers building
next-generation search and retrieval systems that need to operate seamlessly across language barriers.

The model's open availability on Hugging Face, combined with NVIDIA's commitment to releasing
the training data mix, positions it as a valuable resource for the broader AI community working
on multilingual applications.

*#NVIDIA #AI #NLP #EMBEDDING #MULTILINGUAL #MACHINELEARNING #HUGGINGFACE #RETRIEVAL
#SEMANTICSEARCH*

