---
title: "Beam: A 501B-Parameter MoE Model for Long-Context Reasoning and Coding"
slug: "beam-a-501b-parameter-moe-model-for-long-context-reasoning-and-coding"
description: "Beam is a text-only model built for long-context (1M context length) reasoning and agentic work. It is a sparse MoE model designed for teams that want a frontier-scale model on their own hardware,..."
date: 2026-10-16T22:06:38+05:30
tags: [M, i, x, t, u, r, e, O, f, E, x, p, e, r, t, s, L, o, n, g, C, o, n, t, e, x, t, R, u, s, t, A, I, A, g, e, n, t, s, C, o, d, i, n, g]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "A", "I", "A", "g", "e", "n", "t", "s", ",", "N", "a", "t", "u", "r", "a", "l", "L", "a", "n", "g", "u", "a", "g", "e", "P", "r", "o", "c", "e", "s", "s", "i", "n", "g", ",", "O", "p", "e", "n", "S", "o", "u", "r", "c", "e"]
image: "https://huggingface.co/blog/assets/reflection-beam/thumbnail.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Beam: A 501B-Parameter MoE Model for Long-Context Reasoning and Coding

Beam is a text-only model built for long-context (1M context length) reasoning and agentic work. It is a sparse MoE model designed for teams that want a frontier-scale model on their own hardware, infrastructure, or cloud, and want to customize it to their own use cases.

## 🔍 Overview
Beam is a 501B-parameter MoE LLM with 23B active parameters per token. It features a 1M token context window and supports five reasoning values: "low", "medium" (default), "high", "xhigh", and "max".

*   **Context Window:** 1M tokens
*   **Reasoning Modes:** "low", "medium", "high", "xhigh", "max"
*   **Active Parameters:** 23B per token

## 🧩 Architecture
The model consists of 52 layers. The first 3 layers use a dense SwiGLU MLP, while the remaining 49 layers use a Mixture-of-Experts block.

| Layer Type | Count | Details |
| :--- | :--- | :--- |
| Dense Layers | 3 | SwiGLU MLP |
| MoE Layers | 49 | 256 experts per layer |

The MoE layers contain 256 experts, each a SwiGLU MLP with an intermediate size of 2,560. The experts hold 98.4% of the model's parameters. Only 8 experts run per token, so the model computes each token with about 23B parameters.

## 🧠 Attention and Context
Beam uses a hybrid attention mechanism to handle long contexts efficiently. Most layers use sliding-window attention over the previous 512 tokens, while every sixth layer and the last one attend to the full context.

*   **Sliding Window Layers:** 43 layers using RoPE
*   **Global Layers:** 9 layers using no positional encoding

Global layers use a scaler `(1 + (pos + 1) / 2048) ** 0.1` to maintain precision in the softmax as the context lengthens. The model supports reasoning that stays in context across turns via "preserve_thinking" and tool calling with a dedicated grammar.

## ⚙️ Performance and Tooling
Beam ships with its own dedicated open source Rust-based harness that delivers the best performance from the model. It has a native transformers implementation, as well as downstream libraries like vLLM and SGLang.

*   **Speed:** Runs at the speed of a 23B model
*   **Memory:** Requires the memory of a 501B model
*   **Checkpoint Size:** ~1 TB in BF16 safetensors format

The provider has worked with the Reflection team to bring inference, SFT (supervised fine tuning), and RL (reinforcement learning) recipes. Day-0 support is available in transformers, SGLang, and vLLM.

## 🚀 Availability
Beam is available for teams to deploy on their own hardware, infrastructure, or cloud. The provider is offering $10,000 Hub credits to the best projects that use Beam.

![figure](https://huggingface.co/buckets/huggingface/Beam-blog-assets/resolve/images/beam-banner.jpg)

![figure](https://huggingface.co/buckets/huggingface/Beam-blog-assets/resolve/images/beam-architecture.png)

![figure](https://huggingface.co/buckets/huggingface/Beam-blog-assets/resolve/images/beam-attention.png)

#M #i #x #t #u #r #e #O #f #E #x #p #e #r #t #s #, # #L #o #n #g #C #o #n #t #e #x #t #, # #R #u #s #t #, # #A #I #A #g #e #n #t #s #, # #C #o #d #i #n #g

---

*Source: [Welcome Beam: a 501B open model you can own, customize, and scale](https://huggingface.co/blog/reflection-beam)*
