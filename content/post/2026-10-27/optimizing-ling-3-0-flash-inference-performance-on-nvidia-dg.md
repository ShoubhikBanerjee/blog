---
title: "Optimizing Ling-3.0-flash Inference Performance on NVIDIA DGX Spark"
slug: "optimizing-ling-3-0-flash-inference-performance-on-nvidia-dgx-spark"
description: "Performance evaluations of the Ling-3.0-flash model from Inclusion AI on NVIDIA DGX Spark have identified that decoding is memory-bound, with model weight reading driving execution time. These..."
date: 2026-10-27T22:02:24+05:30
tags: [InclusionAI, NVIDIADGX, MixtureOfExperts, ModelInference]
categories: ["AI", "Machine Learning", "Performance Optimization", "AI Infrastructure"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/dgx-spark-inference-featured-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Optimizing Ling-3.0-flash Inference Performance on NVIDIA DGX Spark

Performance evaluations of the Ling-3.0-flash model from Inclusion AI on NVIDIA DGX Spark have identified that decoding is memory-bound, with model weight reading driving execution time. These findings have led to several performance optimizations focused on reducing weight traffic and improving token verification efficiency.

## 🔍 Overview

Ling-3.0-flash-fp4 is a mixture-of-experts (MoE) model featuring 124 billion total parameters and 5.1 billion active parameters per token. Profiling at batch-size-1 identified two specific operations that limit inference performance: the MoE computation and the output-layer projection (LM head) that produces vocabulary scores. To address these bottlenecks, optimizations were applied to the kernel execution path and memory read volume.

## 🧩 How it works

Performance improvements were achieved through three primary technical interventions:

| Optimization | Mechanism | Impact |
| :--- | :--- | :--- |
| Humming Kernel Library | Replaces flashinfer_mxfp4; uses NVIDIA CUDA Runtime Compilation (NVRTC) to specialize kernels for specific model shapes. | Compiles individual kernels in seconds and specializes for narrow intermediate sizes. |
| FP8 LM Head Quantization | Moves LM-head weights from BF16 to FP8 via dynamic quantization. | Halves the memory read volume for the output-layer projection. |
| Speculative Decoding | Utilizes the native NEXTN prediction layer as a draft model for verification rounds. | Reduces the number of decode steps with a measured ratio of approximately 2.26. |

## ⚙️ Key details

The model architecture and optimization environment include several specialized configurations:

*   **Layer Composition:** 42 layers total, consisting of 35 Kimi Delta Attention (KDA) linear-attention layers and seven multi-head latent attention (MLA) layers.
*   **MoE Architecture:** Each layer routes tokens to eight of 512 routed experts plus one shared expert.
*   **Context Window:** Supports a native 256K-token window, expandable to 1M tokens for agentic workflows.
*   **LM Head Projection:** Projects a hidden dimension of 2,560 to a vocabulary of 157,184 tokens.
*   **Drafting Configuration:** Uses three draft steps and a four-token verification window to process up to 32 experts during verification.
*   **Software Integration:** Humming kernels are available through the humming-kernels pip package and cache compiled binaries in local storage.

## 💡 Why it matters

Identifying that decoding was memory-bound allowed for targeted reductions in weight traffic during each decode step. By using the internal NEXTN prediction layer (num_nextn_predict_layers: 1) as a native draft model, the system can perform speculative decoding without requiring additional downloads or external model training. This combination of kernel specialization and memory volume reduction directly addresses the performance limits of high-parameter MoE architectures on specialized hardware.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/dgx-spark-inference-featured-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/04/ai-model-representation-2-660x370.png)

#InclusionAI #NVIDIADGX #MixtureOfExperts #ModelInference

---

*Source: [3 Ways to Boost MoE Inference on NVIDIA DGX Spark | NVIDIA Technical Blog](https://developer.nvidia.com/blog/3-ways-to-boost-moe-inference-on-nvidia-dgx-spark/)*
