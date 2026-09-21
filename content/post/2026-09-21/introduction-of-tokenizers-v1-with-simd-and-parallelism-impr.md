---
title: "Introduction of tokenizers v1 with SIMD and Parallelism Improvements"
slug: "introduction-of-tokenizers-v1-with-simd-and-parallelism-improvements"
description: "A new version of the tokenizers library, v1, has been released. The goal of this version was to improve performance while preserving the API, vocabulary, merge ranks, and output of v0.23, ensuring v1..."
date: 2026-09-21T22:03:11+05:30
tags: [tokenizers, BPE, SIMD, NLP, Rust]
categories: ["AI", "Machine Learning", "Software Engineering", "Natural Language Processing"]
image: "https://huggingface.co/blog/assets/tokenizers-v1/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of tokenizers v1 with SIMD and Parallelism Improvements

A new version of the tokenizers library, v1, has been released. The goal of this version was to improve performance while preserving the API, vocabulary, merge ranks, and output of v0.23, ensuring v1 produces the same token IDs as the previous version.

## 🧩 How it works

Tokenizers run conversions in four stages:

| Stage | Description |
| :--- | :--- |
| Normalization | Applies operations such as Unicode normalization or lowercasing to raw text. |
| Pre-tokenization | Splits text into smaller pieces called pre-tokens. |
| Model | Maps each pre-token to IDs in its vocabulary. |
| Post-processing | Adds special tokens expected by the model. |

## ⚙️ Key details

### BPE and Model Support
* The library supports three model types: Byte Pair Encoding (BPE), WordPiece, and Unigram.
* Eight of the ten measured model families use BPE.
* BPE models use regular expressions to split input text into pre-tokens; merges occur inside a pre-token and never across boundaries.

### Performance Optimizations
* **SIMD Instructions:** For a handful of common grammars, a hand-written function uses SIMD instructions to find splits via boolean operations over bitstreams instead of a regex engine. This process, using bitcannon, views input bytes as parallel streams and decides 64 bytes per register operation.
* **Memory Management:** The merge working set uses a caller-owned scratch buffer to avoid touching the allocator. Merged pieces form an intrusive doubly-linked list inside one preallocated buffer, allowing merges to update two indices rather than moving data.
* **Caching:** A thread-local memo maps pre-token bytes to finished IDs, allowing repeated words to be merged once.
* **Concurrency:** Each thread draws its scratch buffer and word cache from its own sub-pool, allowing one shared tokenizer to encode from many threads at once without queuing on a single lock.

### Architecture Changes
* The library remains general across tokenizer families and loads everything v0.23 loaded.
* The project structure moved from one crate to a workspace:
    * `tk-encode`: The required runtime.
    * `tk-serialize`, `tk-convert`, and `tk-train`: Linked only when an application needs them.

![figure](https://huggingface.co/blog/assets/tokenizers/thumbnail.png)

#tokenizers #BPE #SIMD #NLP #Rust

---

*Source: [tokenizers v1: encode, decode and scaling, measured](https://huggingface.co/blog/tokenizers-v1)*
