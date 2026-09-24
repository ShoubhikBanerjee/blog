---
title: "DSpark Draft Model for LFM2.5-VL-3B Improves Vision-Language Inference Speed"
slug: "dspark-draft-model-for-lfm2-5-vl-3b-improves-vision-language-inference-speed"
description: "An update to the LFM2.5-VL-3B model introduces a DSpark draft model designed to accelerate inference through speculative decoding."
date: 2026-09-24T22:03:57+05:30
tags: [LFM25, SpeculativeDecoding, VLM, InferenceOptimization]
categories: ["AI", "Machine Learning", "Computer Vision", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/WgfT8N8Xyb6lBxSif7XLO.gif"
author: "Shoubhik Banerjee"
draft: false
---

# DSpark Draft Model for LFM2.5-VL-3B Improves Vision-Language Inference Speed

An update to the LFM2.5-VL-3B model introduces a DSpark draft model designed to accelerate inference through speculative decoding.

## 🧩 How it works

The vision drafter uses the same architecture as the text LFM2.5-DSpark drafters. Key technical details include:
* **Architecture**: A simplified attention-only drafter with 4 layers and a block size of 9.
* **Mechanism**: It captures the target model's hidden states at a fixed set of tapped layers and conditions on them to draft a block of k candidate tokens.
* **Modality Handling**: Image patches and text tokens are projected into a shared representation before the layers, allowing the drafter to operate on hidden-state vectors of identical dimensionality regardless of input modality.
* **Verification**: Speculative decoding is exact, as the target verifies every proposed token, ensuring greedy output equals the target alone.

## ⚙️ Key details
* **Parameter Count**: Approximately 280M parameters, increasing the deployed model’s parameter count by 8.9%.
* **Training**: The model was trained for 10 epochs on a mixture of vision-language SFT data weighted toward expected workloads.
* **Hardware Recommendation**: A block size of 8 or 9 is recommended depending on the hardware.

## 🚀 Availability

The DSpark draft model is available on Hugging Face in Safetensors and GGUF formats. It ships with day-one support for:

| Integration | Requirement |
| :--- | :--- |
| llama.cpp | Respective build (PR#29339) |
| MLX-VLM | Respective build (PR#2280) |
| SGLang | Build with DSpark support for LFM2 targets (PR #40651) |

## 💡 Why it matters

Speculative decoding accelerates the decode stage of inference, though it does not speed up vision encoding or prefill. Because prefill is compute-bound and grows (sub)quadratically with prompt length, it can occupy a significant portion of end-to-end latency, particularly on edge devices. This follows Amdahl's law, where overall speedup is capped by the non-accelerated parts of the workload.

Performance measurements across six diverse vision-based tasks (including general VQA, text VQA, image captioning, chart VQA, complex reasoning, and multi-turn conversation) show the following gains using a block size of 8:

* **MLX (M5 Max)**: Decoding speedups of 2.30x to 3.13x; end-to-end latency improvements of 1.56x to 2.62x.
* **llama.cpp (M3 Ultra)**: Decoding improvements of 1.57x to 2.14x; end-to-end improvements of 1.30x to 1.77x.
* **H100 GPU**: Decoding speedups of 20.4x to 2.66x; end-to-end improvements of 1.64x to 2.27x.

#LFM2.5 #SpeculativeDecoding #VLM #InferenceOptimization

---

*Source: [Accelerating vision-language models with LFM2.5-VL-DSpark](https://huggingface.co/blog/LiquidAI/lfm2-5-vl-dspark)*
