---
title: "Compact Open Models Bring Local Multi-Step Reasoning to NVIDIA Jetson Hardware"
description: "Until recently, models capable of multi-step reasoning were too large to run locally on edge hardware. Developers building agents have had to route inference through a data center, which added..."
date: 2026-09-04T22:05:53+05:30
tags: [EdgeAI, NVIDIAJetson, LLM, AIagents, Quantization]
categories: [AI]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/image2-3-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# Compact Open Models Bring Local Multi-Step Reasoning to NVIDIA Jetson Hardware

Until recently, models capable of multi-step reasoning were too large to run locally on edge hardware. Developers building agents have had to route inference through a data center, which added network dependency, increased costs, and exposed data that may need to stay on device. 

Several model families released throughout the summer have collectively marked a turning point for edge AI. This new generation of compact open models now delivers reasoning and agentic capabilities that required large data center systems only a few months ago, and NVIDIA Jetson can run them today.

## ⚙️ Model Architecture and Target Workflows

These compact open models feature high-quality quantized checkpoints and optimized deployment options across popular inference engines. Developers can use Nemotron 3.5 Lightning and Qwen3.8-27B as examples of these different architectural approaches:

| Model | Architecture | Total Parameters | Active Parameters (Per Token) | Best Fit Workflow |
| :--- | :--- | :--- | :--- | :--- |
| **Nemotron 3.5 Lightning** | Mixture-of-experts (MoE) | 30 billion | 3 billion | Response-heavy workflows, where faster token generation can shorten the overall process. |
| **Qwen3.8-27B** | Dense | 27 billion | 27 billion | Tasks that require fewer, harder decisions and allow the agent to spend more time generating each response. |

*Note: Distillation transfers some of Nemotron 3 Ultra’s capabilities into the smaller Nemotron 3.5 Lightning model.*

## 🚀 Hardware and Deployment Options

Developers can deploy these models locally through popular frameworks, including vLLM and llama.cpp, ensuring the reasoning loop does not depend entirely on the data center. Deployment recommendations vary by hardware capability:

*   **Jetson Orin Nano**: Gemma 4 E4B is a strong starting point.
*   **Jetson AGX Orin & Jetson AGX Thor**: Nemotron 3.5 Lightning and Qwen3.8-27B are strong options.

## 🛠️ Performance Optimization Techniques

Two complementary techniques can be used to improve inference performance on Jetson hardware:

*   **NVFP4 Quantization**: Reduces the work and memory required for model operations. This format improves generation speed and reduces memory use while keeping quality close to BF16.
*   **Speculative Decoding**: A smaller draft model proposes several tokens, and the main model verifies them together. This process generates multiple accepted tokens per verification step.

These two optimizations complement each other: NVFP4 reduces the cost of each pass, while speculative decoding increases the number of accepted tokens produced from each pass. Combined, they improve performance.

Below, Figure 2 compares both models in BF16 (which provides the baseline), NVFP4 (adding quantization), and NVFP4 combined with the fastest speculative decoding configuration tested for each model.

![Figure 2](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/techblog-5673-figure-2.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/techblog-5673-figure-2.webp)

#EdgeAI #NVIDIAJetson #LLM #AIagents #Quantization

---

*Source: [Frontier Reasoning Reaches the Edge: How to Deploy and Optimize Models on NVIDIA Jetson | NVIDIA Technical Blog](https://developer.nvidia.com/blog/frontier-reasoning-reaches-the-edge-how-to-deploy-and-optimize-models-on-nvidia-jetson/)*
