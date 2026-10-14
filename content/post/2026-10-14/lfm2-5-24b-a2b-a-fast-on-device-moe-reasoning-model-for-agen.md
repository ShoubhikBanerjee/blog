---
title: "LFM2.5-24B-A2B: A Fast On-Device MoE Reasoning Model for Agentic Tasks"
slug: "lfm2-5-24b-a2b-a-fast-on-device-moe-reasoning-model-for-agentic-tasks"
description: "LFM2.5-24B-A2B is a new reasoning-only model designed for fast, private agentic workflows on-device. Building upon the LFM2-24B-A2B architecture, this update introduces scaled training, expanded..."
date: 2026-10-14T22:09:38+05:30
tags: [AIagents, EdgeAI, MoE, LiquidFoundationModel]
categories: ["AI", "Machine Learning", "AI Agents", "Edge Computing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/YxGx9U6yV6_mumklCyMsE.png"
author: "Shoubhik Banerjee"
draft: false
---

# LFM2.5-24B-A2B: A Fast On-Device MoE Reasoning Model for Agentic Tasks

LFM2.5-24B-A2B is a new reasoning-only model designed for fast, private agentic workflows on-device. Building upon the LFM2-24B-A2B architecture, this update introduces scaled training, expanded context windows, and explicit chain-of-thought reasoning to provide competitive performance against significantly larger models.

## 🔍 Overview
LFM2.5-24B-A2B is a Mixture of Experts (MoE) model that always produces an explicit chain of thought before providing a final answer. While it is the smallest model in its evaluation group, it is competitive with models like Qwen3.6-35B-A3B, which has ~50% more total and active parameters. Its primary strengths are tool use and instruction following.

## 🧩 How it works
The model retains its predecessor's architecture while scaling training and context capabilities:
* **Architecture**: 40 layers with 64 experts per MoE block and top-4 routing.
* **Hybrid Design**: Uses a combination of gated short convolutions and Grouped Query Attention (GQA).
* **Training Scale**: Pre-training was scaled from ~17T to ~33T tokens. Mid-training added 2.3T tokens across 32K and 131K context lengths, emphasizing reasoning, math, and long-context data.
* **Tokenizer**: An in-place expansion doubled the vocabulary from 65K to 128K tokens for improved non-Latin tokenization.

## ⚙️ Key details
| Feature | Specification |
| :--- | :--- |
| Total Parameters | 24 Billion |
| Active Parameters | 2 Billion per token |
| Context Window | 131,000 tokens |
| Vocabulary Size | 128,000 tokens |

In benchmark testing, the model leads or matches competition on five of eight tool-use and agentic benchmarks. On LiveClaw, it scored 48.09 compared to 38.19 for Qwen3.6-35B-A3B. On AutomationBench, it scored more than three times the next-best model.

## 🚀 Availability
LFM2.5-24B-A2B includes day-one support for several inference ecosystems:
* llama.cpp
* MLX
* vLLM
* SGLang
* ONNX

## 💡 Why it matters
This model is optimized for high-speed edge and GPU inference. It decodes at 184 tokens/s on an Apple M5 Max and 114 tokens/s on a Ryzen AI Max+ 395, making it up to 1.7x faster than the next-best compared model while using the least memory. On a single NVIDIA B300 GPU, it can reach over 21,000 output tokens per second. For knowledge-heavy workloads, users are encouraged to pair the model with retrieval or web search, as larger models maintain an edge on benchmarks like GPQA Diamond and SWE-Bench.

![figure](https://huggingface.co/LiquidAI/LFM2.5-24B-A2B/resolve/main/figures/LFM2.5-24B-A2B-benchmark.png)

![figure](https://huggingface.co/LiquidAI/LFM2.5-24B-A2B/resolve/main/figures/LFM2.5-24B-A2B-edge-inference.png)

![figure](https://huggingface.co/LiquidAI/LFM2.5-24B-A2B/resolve/main/figures/LFM2.5-24B-A2B-gpu-inference.png)

#AIagents #EdgeAI #MoE #LiquidFoundationModel

---

*Source: [Run fast, private agents on-device with LFM2.5-24B-A2B](https://huggingface.co/blog/LiquidAI/lfm25-24b-a2b)*
