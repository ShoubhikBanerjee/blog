---
title: "Update on end-to-end post-training conversion for ultra-low-bit language models"
description: "Researchers have completed an end-to-end post-training conversion of the Qwen 4B-parameter model to evaluate the performance and runtime behavior of ultra-low-bit quantization."
date: 2026-09-03T22:06:46+05:30
tags: [AI, Quantization, LLM, MachineLearning, ModelCompression]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Update on end-to-end post-training conversion for ultra-low-bit language models

Researchers have completed an end-to-end post-training conversion of the Qwen 4B-parameter model to evaluate the performance and runtime behavior of ultra-low-bit quantization.

## 🧩 How it works
The study utilized a weight-only conversion process while maintaining 16-bit precision for activations. The technical workflow included:
- KOTMS rotation
- E2M-ATQ ternarization
- GPTQ-style error compensation from TWLA

## ⚙️ Key details
The final conversion targeted 81.62% of model parameters with 1.641 effective bits per weight. A subsequent packing run reduced the model size from 8.29 GiB to 3.96 GiB with essentially unchanged perplexity.

### Perplexity Comparison
| Dataset | Original Perplexity | Quantized Perplexity |
| :--- | :--- | :--- |
| WikiText-2 | 13.639 | 18.748 |
| PTB | 24.700 | 31.992 |
| C4 | 19.831 | 28.966 |

## 📊 Performance and Deployment
- Capability: Across ten scored comparisons, accuracy decreased from 64.5% to 54.7%.
- Degradation: Performance is uneven; BoolQ retained 84.6% of teacher performance, while ARC-Challenge retained 43.8%.
- Inference: A preliminary Triton GEMV microbenchmark is 4.6x slower than FP16 cuBLAS on one tested shape; compression alone does not yield faster inference.
- Exclusions: A third-party packing attempt was lossy and is excluded from the primary claim.

#AI #Quantization #LLM #MachineLearning #ModelCompression

---

*Source: [Post-Training Ternarization of Qwen3-4B Capability, Effective Bit Budget, Storage Compression, and Deployment](https://arxiv.org/abs/2609.01962v1)*
