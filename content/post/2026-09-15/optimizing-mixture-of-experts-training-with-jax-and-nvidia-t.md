---
title: "Optimizing Mixture of Experts Training with JAX and NVIDIA Transformer Engine"
slug: "optimizing-mixture-of-experts-training-with-jax-and-nvidia-transformer-engine"
description: "NVIDIA Transformer Engine, a library for accelerating Transformer models on NVIDIA GPUs, combined with the JAX Python library, has delivered significant performance improvements in Mixture of Experts..."
date: 2026-09-15T22:08:30+05:30
tags: [NVIDIA, JAX, MixtureOfExperts, TransformerEngine, DeepSeekV3]
categories: ["AI", "Machine Learning", "GPU Acceleration", "Deep Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/green-cube-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Optimizing Mixture of Experts Training with JAX and NVIDIA Transformer Engine

NVIDIA Transformer Engine, a library for accelerating Transformer models on NVIDIA GPUs, combined with the JAX Python library, has delivered significant performance improvements in Mixture of Experts (MoE) training operations. In DeepSeek-V3 training on NVIDIA GB200, an unoptimized baseline achieved just 103 TFLOPS/GPU with inter-GPU communication consuming 84% of accumulated kernel time. With JAX and targeted Transformer Engine kernel optimizations, that performance rose to 1,068 TFLOPS/GPU, a 10.4x improvement.

## 🔍 Overview
Mixture of experts (MoE) has become one of the defining architectural trends in large-scale AI model training. Models utilizing this architecture provide efficient training through conditional computation.
* **Key Models:** DeepSeek, Qwen, and Mixtral are examples of MoE models that match or exceed the performance of their dense model counterparts at a fraction of the training compute.
* **Core Mechanism:** Instead of a single dense feed-forward network (FFN) shared by all tokens, MoE replaces it with many smaller expert networks and a learned router that decides which Top-K experts to activate.

## 🧩 How it works
In a dense FFN, every token passes through the same weight matrix. In MoE, tokens are routed dynamically to different experts, which distributes them unevenly and breaks the regular GEMM shape that typical kernels are optimized for:
* **Routing and Dispatch:** The router assigns each token to an expert, and dispatch moves tokens to their expert's GPU.
* **Grouped MLP:** Runs two grouped GEMMs on variable-length groups.
* **Combine:** Reverses the exchange to restore the original token order.

## ⚙️ Key details
Production-scale MoE training introduces bottlenecks that do not exist with dense models, including token routing, expert dispatch and gather, all-to-all communication, and ragged expert GEMMs. Because no two batches produce the same expert loads, one expert might receive many more tokens than another. With expert parallelism (EP), tokens must be dispatched and outputs must be combined and restored to original token order. A poorly optimized all-to-all forces GPUs to stall and wait for data before doing any useful work. Solving this requires specialized kernels that can natively handle ragged layouts.

These layout challenges are typically handled through different MoE training approaches:

| MoE Approach | Token Handling | Computational Impact |
| :--- | :--- | :--- |
| **Capacity-Based** | Each expert is assigned a fixed token budget; overflow is trimmed or padded to fit. | Batched GEMM computes worst-case token capacity even if fewer tokens are used because of padding, leading to extra compute. The loop requires Device-to-Host copies of token counts on the critical path, incurring latency and breaking CUDA graphs. |
| **Dropless MoE (MegaBlocks)** | Every token is processed by its selected expert no matter how uneven the load. | Reformulates expert computation as block-sparse matrix multiplication, allowing each expert to operate on a different number of tokens without dropping or padding. |

To resolve these performance limitations, a grouped GEMM handles all expert matmuls in a single kernel call, each with its actual token count. It computes only the regions with valid tokens and is more performant as a result. The Transformer Engine `grouped_gemm` and `ragged_dot` operations back this with cuBLAS and cuBLASLt, mapping directly onto the best-performing NVIDIA GEMM libraries to deliver full Tensor Core utilization even with irregular expert shapes.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/capacity-based-versus-dropless-moe-comparison.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/ragged-tensore-moe-training.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/end-to-end-training-performance-moe-jax-transformer-engine.webp)

#NVIDIA #JAX #MixtureOfExperts #TransformerEngine #DeepSeekV3

---

*Source: [Accelerating Dropless MoE Training in JAX with NVIDIA Transformer Engine | NVIDIA Technical Blog](https://developer.nvidia.com/blog/accelerating-dropless-moe-training-in-jax-with-nvidia-transformer-engine/)*
