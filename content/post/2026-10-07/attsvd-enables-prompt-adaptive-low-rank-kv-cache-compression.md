---
title: "AttSVD Enables Prompt-Adaptive Low-Rank KV Cache Compression"
slug: "attsvd-enables-prompt-adaptive-low-rank-kv-cache-compression"
description: "AttSVD is a new, interpretable low‑rank compression method that adapts to each prompt’s attention geometry, reducing key‑value (KV) cache memory while preserving performance."
date: 2026-10-07T22:09:50+05:30
tags: [KVCache, LowRank, Transformer, MemoryEfficiency]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Deep Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# AttSVD Enables Prompt-Adaptive Low-Rank KV Cache Compression

AttSVD is a new, interpretable low‑rank compression method that adapts to each prompt’s attention geometry, reducing key‑value (KV) cache memory while preserving performance.

## 🔍 Overview
- KV caches of autoregressive transformers grow linearly with context length and dominate memory at long context.
- Traditional training‑free remedies evict low‑importance tokens, an irreversible choice along the sequence axis.
- AttSVD keeps every token but stores it more cheaply along the *feature* axis.

## 🧩 How it works
- Performs an online, per‑prompt truncated Singular Value Decomposition (SVD) that retains only the directions attention actually reads.
- The retained rank determines the proportion of persistent per‑head KV memory that is kept.
- Two decode‑time caching strategies are offered:
  - **Accumulating** – suited for short generation regimes.
  - **Streaming** – suited for long generation regimes.

## ⚙️ Key details
- **Per‑matrix energy rule**: sizes the logit space and the attention mass independently.
- **Attention‑aware basis**: truncates only in the spaces attention reads, preserving both attention logits and output.
- Provides free, per‑head interpretability insights into effective rank and the geometry attention consumes.

## 📊 Performance
- Across multiple models, on an agentic benchmark and the full LongBench suite, AttSVD stays on par with the dense cache while using up to **50 %** of the KV‑cache memory.


#KVCache #LowRank #Transformer #MemoryEfficiency

---

*Source: [AttSVD:Prompt-Adaptive Low-Rank KV Cache Compression via Attention-Guided SVD](https://arxiv.org/abs/2610.06927v1)*
*Source: [Mask-Guided KV Cache Eviction in Block Diffusion Language Models](https://arxiv.org/abs/2610.06996v1)*
*Source: [WavePrune: One period is often enough for RoPE](https://arxiv.org/abs/2610.06963v1)*
*Source: [Recurrent Looped Transformer](https://arxiv.org/abs/2610.07591v1)*
*Source: [Monte Carlo Estimation for KV Cache Eviction](https://arxiv.org/abs/2610.07643v1)*
*Source: [Readout Stability in Prefill-Only Decision Models:Zero-Label Prediction and Inference-Time Compute Allocation](https://arxiv.org/abs/2610.07716v1)*
