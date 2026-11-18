---
title: "LLaVA-OneVision-2.5-4B-Instruct Released with Unified Video and Streaming Support"
slug: "llava-onevision-2-5-4b-instruct-released-with-unified-video-and-streaming-support"
description: "On November 18, 2026, LLaVA-OneVision-2.5-4B-Instruct was released as the latest entry in the LLaVA-OneVision family. This release is a 4B model designed for single-image, multi-image, and video..."
date: 2026-11-18T22:09:17+05:30
tags: [LLaVAOneVision, MultimodalAI, VideoUnderstanding, OpenSource, SpatialReasoning]
categories: ["AI", "Machine Learning", "Computer Vision", "Natural Language Processing", "Open Source Software"]
image: "https://avatars.githubusercontent.com/u/154951679?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LLaVA-OneVision-2.5-4B-Instruct Released with Unified Video and Streaming Support

## 🔍 Overview
On November 18, 2026, LLaVA-OneVision-2.5-4B-Instruct was released as the latest entry in the LLaVA-OneVision family. This release is a 4B model designed for single-image, multi-image, and video input that is also trained for streaming video. The release includes the training code alongside the model weights.

## 🧩 How it works
The model architecture supports two distinct video processing modes:
- **Long video**: Enables multi-frame reasoning with efficient codec-aligned inference.
- **Streaming video**: Frames arrive one at a time, and the model decides at every step whether to stay silent or speak.

The same weights and the same chat template serve both offline and streaming modes. Additionally, the model supports 3D-aware spatial reasoning, including depth, layout, and object relations. The design operates at native resolution without task-specific adapters.

## ⚙️ Key details
- **Model Size**: 4B parameters.
- **Input Modalities**: Single-image, multi-image, video, and 3D spatial data.
- **Training Efficiency**: A tool named ResearchBoost-Agent made LLaVA-OneVision-2-4B SFT 2.2–3.0× faster.
- **Context**: The underlying OneVision-Encoder uses HEVC-style vision transformers that add a codec-stream input mode. This approach selects motion- and residual-rich patches, allowing for dramatically longer temporal coverage under the same token budget compared to prior ViT backbones.

## 📦 Datasets
Four datasets ship with the LLaVA-OneVision family, including two new ones for LLaVA-OneVision-2 and two carried forward from 1.5:

| Dataset Name | Description |
| :--- | :--- |
| LLaVA-OneVision-2-VideoCaption | Extremely dense video captions |
| LLaVA-OneVision-2-Spatial | 3D-aware spatial reasoning |
| LLaVA-OneVision-1.5-Mid-Training-85M | 85M concept-balanced mid-training corpus |
| LLaVA-OneVision-1.5-Instruct | Full instruction-tuning mixture |

## 💡 Why it matters
The LLaVA-OneVision-2 release was noted as a next-generation multimodal model with a fully open pipeline where encoder weights, training code, configs, and full training logs are released end-to-end. This commitment to transparency allows for detailed analysis of the training processes and architectural choices, such as the integration of codec-aligned vision encoders.

#LLaVA-OneVision #MultimodalAI #VideoUnderstanding #OpenSource #SpatialReasoning

---

*Source: [EvolvingLMMs-Lab/LLaVA-OneVision-2.5](https://github.com/EvolvingLMMs-Lab/LLaVA-OneVision-2.5)*
