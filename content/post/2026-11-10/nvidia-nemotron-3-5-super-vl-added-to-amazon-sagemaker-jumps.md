---
title: "NVIDIA Nemotron 3.5 Super VL Added to Amazon SageMaker JumpStart"
slug: "nvidia-nemotron-3-5-super-vl-added-to-amazon-sagemaker-jumpstart"
description: "Today NVIDIA announced that the Nemotron 3.5 Super VL vision‑language model is now available through Amazon SageMaker JumpStart. The model can be deployed in SageMaker Studio with a few steps or with..."
date: 2026-11-10T22:09:41+05:30
tags: [NVIDIA, SageMaker, VisionLanguage, AIagents]
categories: ["AI", "Machine Learning", "Computer Vision", "AI Agents", "Natural Language Processing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22096-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Nemotron 3.5 Super VL Added to Amazon SageMaker JumpStart

Today NVIDIA announced that the Nemotron 3.5 Super VL vision‑language model is now available through Amazon SageMaker JumpStart. The model can be deployed in SageMaker Studio with a few steps or with a few lines of the SageMaker Python SDK.

## 🔍 Overview
- Super VL is the vision‑language model (VLM) in the NVIDIA Nemotron 3.5 family.
- Inputs: images, video, and text.
- Output: generated text.
- Designed for document intelligence, GUI understanding for computer‑use agents, video question answering, and multimodal agentic applications.

## 🧩 Architecture
- **Language backbone**: 120 B‑parameter hybrid Mixture‑of‑Experts (MoE) model with 12 B active parameters per token.
  - 88 layers interleaving Mamba‑2 and MoE layers (512 routed experts, 22 active per token) plus 8 attention layers.
  - Initialized from Nemotron 3 Super Base and distilled from Nemotron 3 Ultra Base.
- **Vision encoder**: C‑RADIO encoder that processes images and sampled video frames.
- **Vision‑language connector**: Maps encoder outputs into the language backbone’s embedding space.
- Both encoder and connector remain in BF16 for all variants.
- Supports context lengths up to 1 million tokens and includes a built‑in Multi‑Token Prediction (MTP) head for speculative decoding (not enabled in the default JumpStart serving configuration for NVFP4).

## ⚙️ Key Details
- **Reasoning**: Enabled by default; can be toggled per request with `enable_thinking`.
- **Languages supported**: English, French, German, Italian, Japanese, Spanish, Chinese.
- **Outputs**: Tool calling, JSON schema output, configurable reasoning.
- **License**: OpenMDW License Agreement, version 1.1.
- **Training pipeline**:
  - Continued pre‑training → long‑context & software‑engineering mid‑training → vision‑language training.
  - Two‑stage multimodal supervised fine‑tuning on vision, reasoning, code, tool, chat, safety, and long‑context data.
  - Reinforcement learning with verifiable rewards and human feedback (NeMo RL, NeMo Gym), multi‑teacher on‑policy distillation, and final MTP‑head training.

## 📦 Variants
| Variant | Precision | Checkpoint Size | Quantization |
|---|---|---|---|
| NVFP4 | 4‑bit weights & activations (W4A4) on Blackwell GPUs; vision encoder, connector, Mamba convolutions, embeddings in BF16; MoE router in FP32 | ~75 GB | Quantized from BF16 with quantization‑aware distillation |
| BF16 | Full‑precision BF16 weights | ~249 GB | Reference weights |

## 🚀 Availability
- **Deployment**: One‑click launch from SageMaker JumpStart; deployable via SageMaker Studio UI or SageMaker Python SDK.
- **Instance types**:
| Instance | Recommended for |
|---|---|
| ml.g7.24xlarge | Default |
| ml.g7.48xlarge | NVFP4 variant |
| ml.p5en.48xlarge | BF16 variant |

## 💡 Why It Matters
- Targets agentic workloads that must both see and read.
- Enables vision‑language agents that combine reasoning, coding, tool use, document understanding, and video understanding.
- Provides large‑context (up to 1 M tokens) and built‑in speculative decoding to accelerate generation.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22096-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22096-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-22096-3.png)

#NVIDIA #SageMaker #VisionLanguage #AIagents

---

*Source: [NVIDIA Nemotron 3.5 Super VL is now available in Amazon SageMaker JumpStart | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/nvidia-nemotron-3-5-super-vl-is-now-available-in-amazon-sagemaker-jumpstart/)*
