---
title: "FlexComp Introduces Any-Ratio Soft Context Compression for Large Language Models"
slug: "flexcomp-introduces-any-ratio-soft-context-compression-for-large-language-models"
description: "A new method-agnostic framework called FlexComp has been developed to decouple the compression ratio from the training and deployment of soft context compressors."
date: 2026-09-11T12:15:38+05:30
tags: [LLM, ContextCompression, FlexComp, MachineLearning]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# FlexComp Introduces Any-Ratio Soft Context Compression for Large Language Models

A new method-agnostic framework called FlexComp has been developed to decouple the compression ratio from the training and deployment of soft context compressors.

## 🔍 Overview
Soft context compression reduces a context into memory tokens for use by a frozen LLM. Previous compressors required separate models for each deployed ratio and applied a uniform ratio to all inputs regardless of their specific needs. FlexComp addresses these limitations by allowing a single model to function as an any-ratio compressor.

## 🧩 How it works
FlexComp utilizes Matryoshka-style training that samples the memory budget $K$ per instance. After training, the budget is selected per input using one of two methods:

| Method | Description |
| :--- | :--- |
| Confidence-based cascade routing | Determines the budget based on confidence levels |
| Lightweight learned $K$ predictor | Predicts the budget in a single compression-decoding pass |

## ⚙️ Key details
Testing across SAC, 500xCompressor, and ICAE on MRQA showed that a single FlexComp model matches the performance of separately trained fixed-ratio specialists with minimal degradation. Performance metrics include:

* **Cascade routing**: Maintains over 98% of the accuracy of the mildest ratio at an average compression of up to 266x.
* **$K$ predictor**: Reaches 158-236x compression within 0.7 F1 of the mildest ratio.
* **Efficiency**: At serving-scale batch sizes, the $K$ predictor improves decoding throughput by 47% and reduces the context KV cache by 50%.

#LLM #ContextCompression #FlexComp #MachineLearning

---

*Source: [FlexComp: One Model for Every Ratio in Context Compression](https://arxiv.org/abs/2609.11192v1)*
