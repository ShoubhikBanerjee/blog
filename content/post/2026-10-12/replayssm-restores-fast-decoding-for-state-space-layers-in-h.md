---
title: "ReplaySSM Restores Fast Decoding for State‑Space Layers in Hybrid LLMs"
slug: "replayssm-restores-fast-decoding-for-statespace-layers-in-hybrid-llms"
description: "Hybrid large‑language models interleave state‑space model (SSM) layers with a few attention layers. Recent work – *ReplaySSM: Cache SSM Inputs, Not State* – shows how to make those SSM layers fast..."
date: 2026-10-12T22:04:14+05:30
tags: [ReplaySSM, SSM, HybridModels, InferenceOptimization]
categories: ["AI", "Machine Learning", "Large Language Models", "Inference Acceleration", "Hardware Optimization"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/06/cube-black-background-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# ReplaySSM Restores Fast Decoding for State‑Space Layers in Hybrid LLMs

## 🔍 Overview
Hybrid large‑language models interleave state‑space model (SSM) layers with a few attention layers. Recent work – *ReplaySSM: Cache SSM Inputs, Not State* – shows how to make those SSM layers fast again, removing a major latency bottleneck that appears at serving batch sizes.

## 🧩 How it works
ReplaySSM changes the way an SSM’s internal state is stored during generation:
- The state is split into a **checkpoint** (a full copy of the SSM state) and a **buffer of recent inputs**.
- Output computation reads only the buffer, while the checkpoint is updated lazily.
- This separation eliminates three known problems:
  1. **State traffic** – the full state no longer moves every token.
  2. **Rollback for speculative decoding** – the buffer can be discarded without reverting a large state.
  3. **Error accumulation in a quantized state** – rounding errors no longer re‑enter the recurrence each step.

## ⚙️ Key details
- **Hybrid model examples** – NVIDIA Nemotron 3, Qwen 3.5 through 3.8, Kimi‑K3, and GLM‑5.3‑Flash all use this pattern, with Mamba‑2, Gated DeltaNet (GDN), or Kimi Delta Attention (KDA) as the SSM layer.
- **Decoding bottleneck** – at batch size 256 on a Blackwell Ultra B300 GPU, SSM layers dominate latency up to 100 K tokens of context (Figure 2, left). The model has five times as many SSM layers as attention layers.
- **State size comparison** – one SSM layer’s FP32 state is 4 MiB per sequence, while an FP8 KV entry is 0.5 KiB per token. Thus an SSM state equals an attention KV cache for roughly 8 K tokens.
- **Speculative decoding** – a drafter proposes *T* tokens, the target model verifies them, then rolls back to the last accepted token. Attention rolls back by moving a KV pointer; an SSM’s state has no cheap inverse, so engines store a full snapshot after each draft token. This costs one read and *T* writes per step and limits how many requests fit in GPU memory, making speculative decoding barely helpful for SSMs.
- **Quantization issue** – the quantized state is both the output and the next update’s input, so rounding error recurs at every step.

## 🚀 Availability
- The paper is on **arXiv** and the implementation is on **GitHub**.
- ReplaySSM is integrated into **NVIDIA TensorRT‑LLM**, **vLLM**, and **FlashInfer**.
- Production deployments include **GLM‑5.3‑Flash** and **Kimi‑K3**.

## 💡 Why it matters
By turning the SSM state into a cache of recent inputs rather than a constantly moved full tensor, ReplaySSM restores the speed advantages of attention‑only models for hybrid architectures. This enables existing speed‑up techniques—speculative decoding and low‑precision quantization—to be applied to models that heavily rely on SSM layers, broadening the practical utility of state‑space approaches in large‑scale inference.

## 📊 Model‑SSM mapping
| Model | SSM layer |
|-------|-----------|
| NVIDIA Nemotron 3 | Mamba‑2 |
| Qwen 3.5 – 3.8 | Mamba‑2, GDN, or KDA |
| Kimi‑K3 | KDA |
| GLM‑5.3‑Flash | Mamba‑2 / GDN / KDA |


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-1-4.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-2-4.webp)

#ReplaySSM #SSM #HybridModels #InferenceOptimization

---

*Source: [ReplaySSM: Rethinking State Storage for Faster Hybrid-Model Decoding | NVIDIA Technical Blog](https://developer.nvidia.com/blog/replayssm-rethinking-state-storage-for-faster-hybrid-model-decoding/)*
