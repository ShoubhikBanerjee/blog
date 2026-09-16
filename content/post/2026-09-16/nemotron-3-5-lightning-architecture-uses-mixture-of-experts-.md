---
title: "Nemotron 3.5 Lightning Architecture Uses Mixture-of-Experts and Mamba-2 Hybrid Design"
slug: "nemotron-3-5-lightning-architecture-uses-mixture-of-experts-and-mamba-2-hybrid-design"
description: "Nemotron 3.5 Lightning illustrates how a 30B-parameter model can activate only 3B parameters per token while utilizing the capacity of a larger model. This is achieved through a Mixture-of-Experts..."
date: 2026-09-16T06:07:24+05:30
tags: [Nemotron, MixtureOfExperts, Mamba2, NVIDIA, ModelArchitecture]
categories: ["AI", "Machine Learning", "Model Architecture", "Deep Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image2-8-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Nemotron 3.5 Lightning Architecture Uses Mixture-of-Experts and Mamba-2 Hybrid Design

Nemotron 3.5 Lightning illustrates how a 30B-parameter model can activate only 3B parameters per token while utilizing the capacity of a larger model. This is achieved through a Mixture-of-Experts (MoE) architecture that selects a specific subset of parameters for each token, allowing for high throughput and managed serving complexity.

## 🔍 Overview

There are two dominant model architectures used in large language models: dense models and MoE models. While raw parameter count is a common metric, how a model organizes those parameters significantly affects throughput, memory cost, and serving complexity. The choice between these architectures is driven primarily by deployment constraints.

*   **Dense Models:** Activate all parameters for every token. For example, all 27B parameters of a 27B model fire through a single shared feed-forward network (FFN) block per decoder layer.
*   **MoE Models:** Store multiple expert networks but route each token through only a selected subset. This allows the model to read fewer weight bytes per token during decoding.

## 🧩 How it works

In a standard dense decoder layer, a single shared FFN is used. An MoE model replaces this with multiple FFN blocks, also known as experts. Inside each layer, there may be 8, 64, or 128 experts.

*   **Routing Network:** A learned gate network, or router, sits in front of the experts and assigns each incoming token to the top k scoring experts.
*   **Layer Independence:** The routing decision is made separately for every layer, so a token is not restricted to a single expert for the duration of the computation.
*   **Attention and Embeddings:** While the router decides which FFN blocks are skipped, tokens still pass through the full attention mechanism as normal. The reported "3B active parameters" in Nemotron 3.5 Lightning includes these attention and embedding weights along with the selected FFN weights.
*   **Hybrid Structure:** Nemotron 3.5 Lightning utilizes a hybrid of Mamba-2, MoE, and Attention. Mamba-2 layers replace attention in most layers, carrying a constant-size recurrent state rather than a growing KV cache, which changes the memory profile at long context.

## ⚙️ Deployment Comparison

| Feature | Dense Model | Mixture-of-Experts (MoE) |
| :--- | :--- | :--- |
| **Parameter Activation** | Full network participates in every forward pass. | Only a subset of FFN parameters fire per token. |
| **Deployment Profile** | Simpler, more predictable latency. | Faster token throughput but higher serving complexity. |
| **Memory Requirements** | Standard memory usage. | VRAM is paid up front; all experts must live in GPU memory simultaneously. |
| **Efficiency** | Compute scales with total parameters. | Scaling is limited to the experts that fire; efficient at batch size 1. |

## 💡 Why it matters

MoE models are often faster for token throughput because they limit the active feed-forward parameters per token. At batch size 1, where decoding is bound by available memory rather than compute, MoE performs particularly well. However, at high concurrency, the advantages of MoE can be narrowed by the overhead of routing and memory movement. To further optimize performance, Nemotron 3.5 Lightning also employs speculative decoding.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image2-8-1024x576.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image3-8.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2024/03/llm-graphic-representation-960x540.jpg)

#Nemotron #MixtureOfExperts #Mamba2 #NVIDIA #ModelArchitecture

---

*Source: [Dense vs. MoE Models: Active Parameters, Throughput, and When to Choose Each | NVIDIA Technical Blog](https://developer.nvidia.com/blog/dense-vs-moe-models-active-parameters-throughput-and-when-to-choose-each/)*
