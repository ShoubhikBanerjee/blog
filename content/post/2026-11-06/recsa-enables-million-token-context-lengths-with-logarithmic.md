---
title: "RecSA Enables Million-Token Context Lengths with Logarithmic Selection Cost"
slug: "recsa-enables-million-token-context-lengths-with-logarithmic-selection-cost"
description: "A new development in context length extrapolation, Recursive Sparse Attention (RecSA), has been introduced to address the scaling limitations of dense attention. While dense attention becomes..."
date: 2026-11-06T22:02:31+05:30
tags: [RecSA, LLM, MachineLearning, KVcache]
categories: ["AI", "Natural Language Processing", "Machine Learning", "AI Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# RecSA Enables Million-Token Context Lengths with Logarithmic Selection Cost

A new development in context length extrapolation, Recursive Sparse Attention (RecSA), has been introduced to address the scaling limitations of dense attention. While dense attention becomes prohibitively expensive at lengths near 1 million tokens, RecSA provides a method for efficient prefill and decoding by reducing selection costs to logarithmic complexity.

## 🔍 Overview

Existing sparse attention methods often rely on selection costs that scale linearly ($O(L)$) with context length. RecSA overcomes this by building a tree structure over the KV cache. In this architecture, each node in the tree summarizes its subtree using a single key and one mean-pooled value. This allows each query to achieve $O(\log L)$ selection cost and read only $O(\log L)$ entries.

## 🧩 How it works

RecSA utilizes a hierarchical selection mechanism that maintains performance even at extreme scales. Key components of the architecture include:

*   **KV Cache Tree:** A tree structure where each level above the tokens selects a maximum of $k$ candidates.
*   **Shared Poolers:** One pooler per layer, shared by all levels, is distilled from dense attention to generate keys for summary nodes.
*   **Logarithmic Softmax:** Summaries of unselected candidates share a single softmax with the exact tokens, ensuring comprehensive attention coverage.
*   **Positional Encoding:** Using Rotary Positional Embeddings (RoPE), each entry's position is defined as its index among candidates at its specific level. This ensures relative distances remain within the range observed during training.

## ⚙️ Key details

RecSA was evaluated using a model initialized from Qwen3-4B and trained on 0.62 billion tokens at a 32K training length. Performance results demonstrate significant improvements over standard sparse and dense baselines:

| Metric | RecSA Performance | Baseline (Dense + DCA) |
| :--- | :--- | :--- |
| RULER Score (1M tokens) | 60.5 | 40.0 |
| Prefill Speedup (524K) | 3.2x | - |
| Decoding Speedup (524K) | 3.8x | - |

Tested on a single H200 GPU, optimized kernels for RecSA were found to be faster than dense attention for both end-to-end prefill and decoding tasks across context lengths ranging from 64K to 2M tokens.

## 💡 Why it matters

This approach addresses a critical bottleneck in large language model deployment: the scarcity of long-document training data and the quadratic cost of dense attention. By keeping relative distances within training bounds and reducing the memory and compute overhead of KV cache selection, RecSA allows models trained on shorter sequences to extrapolate effectively to contexts as large as 2 million tokens.

#RecSA #LLM #MachineLearning #KVcache

---

*Source: [LowRAM: Low-Rank Keys and Amortised Values for Composable KV Cache Compression at Test-Time](https://arxiv.org/abs/2611.07025v1)*
*Source: [On the Opportunities and Challenges of Prefill-to-Autoregressive Cross-Model Transfer](https://arxiv.org/abs/2611.06976v1)*
*Source: [Recursive Sparse Attention: Million-Token Length Extrapolation at Logarithmic Cost](https://arxiv.org/abs/2611.07232v1)*
*Source: [SPARE: Fast Linear Attention Decoding with Compact Recurrent States](https://arxiv.org/abs/2611.07552v1)*
*Source: [SKIM: Pruning Large Language Model Agents via Selective Knowledge Informed Masking](https://arxiv.org/abs/2611.07558v1)*
*Source: [The Gating Mechanism of KV Cache Eviction](https://arxiv.org/abs/2611.07605v1)*
