---
title: "KVFetch adds temporal recall channel to improve KV‑cache compression"
slug: "kvfetch-adds-temporal-recall-channel-to-improve-kvcache-compression"
description: "KVFetch: Temporal Prefetching for the Missing Half of KV Cache Compression was submitted on 23 Sep 2026. It introduces a new mechanism to address a key limitation of current KV‑cache compressors used..."
date: 2026-10-08T22:04:21+05:30
tags: [KVCache, LLMInference, Compression]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Computer Systems"]
author: "Shoubhik Banerjee"
draft: false
---

# KVFetch adds temporal recall channel to improve KV‑cache compression

KVFetch: Temporal Prefetching for the Missing Half of KV Cache Compression was submitted on 23 Sep 2026. It introduces a new mechanism to address a key limitation of current KV‑cache compressors used during long‑context LLM inference.

## 🔍 Overview
- As context windows grow to tens or hundreds of thousands of tokens, KV‑cache compression becomes essential for efficient inference.
- Existing compressors belong to three families: score‑based eviction, summary compensation, and offload‑and‑recall.
- All three decide what to keep or recall solely by content relevance to the current query.

## ⚙️ Problem with existing KV‑cache compressors
- A cache supports two access modes: **associative lookup by content** and **sequential traversal by position**.
- Current compressors implement only the associative (content‑based) mode.
- This omission matters for tasks such as retrieval‑augmented generation, code completion, and structured‑data extraction, which need verbatim reproduction of identifiers, field values, or code tokens.
- Under compression, content‑based eviction keeps the head of a sequence but discards its continuation, causing "sequential forgetting" – a failure that persists despite better scoring, larger budgets, summary compensation, or dynamic re‑scoring.
- Sequential forgetting is identified as the dominant source of remaining quality loss under compression.

## 🛠️ KVFetch design
- KVFetch is a **training‑free, drop‑in framework** that adds a **temporal recall channel** to any score‑based compressor.
- It **demotes evicted candidates to a quantized cold tier**.
- It **detects active copying** through a **monotone read pointer**.
- It **prefetches positional successors** into fixed‑size hot‑tier slots **without increasing attention cost**.

## 📊 Results
- Evaluation on **RULER‑16K** under an iso‑budget control shows:
  - Verbatim copying recovery improves from **0.8 % to 78.4 %**.
  - The 13‑task average score rises by **+8.4** points, with gains concentrated on tasks requiring sequential access.
- On **LongBench**, where no task requires sequential access, the temporal channel stays dormant and imposes no cost.

## 🚀 Availability
- KVFetch is presented as a **drop‑in framework**, implying it can be incorporated into existing score‑based compressors without additional training.
- The work is hosted on arXiv Labs, a platform that encourages community collaboration and upholds values of openness, community, excellence, and user data privacy.

---
*The story is based on the arXiv preprint titled “KVFetch: Temporal Prefetching for the Missing Half of KV Cache Compression.”*

#KVCache #LLMInference #Compression

---

*Source: [KVFetch: Temporal Prefetching for the Missing Half of KV Cache Compression](https://arxiv.org/abs/2610.08811v1)*
*Source: [Task-Oriented Key-Layer KV Communication for Efficient Latent Multi-Agent Collaboration](https://arxiv.org/abs/2610.08820v1)*
*Source: [Algorithmic Scratchpads and Curriculum Staging for Arithmetic Reasoning in Tiny Transformers](https://arxiv.org/abs/2610.09003v1)*
*Source: [SPIN: Shadow Predictive Indexer for Sparse Attention](https://arxiv.org/abs/2610.09025v1)*
*Source: [A Self-Pruning Transformer: Extreme KV-Cache Compression with Universal Attention](https://arxiv.org/abs/2610.09051v1)*
*Source: [LRCC: Generalizing Low-Rank Compression with Conditional Computation](https://arxiv.org/abs/2610.08858v1)*
*Source: [OnlineQAT: On-Policy Distillation for Ultra-Low-Bit Large Language Models](https://arxiv.org/abs/2610.09346v1)*
