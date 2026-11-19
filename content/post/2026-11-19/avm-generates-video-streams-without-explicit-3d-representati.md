---
title: "AVM Generates Video Streams Without Explicit 3D Representations"
slug: "avm-generates-video-streams-without-explicit-3d-representations"
description: "Researchers have presented the Autoregressive View Model (AVM), a framework that generates scenes as a stream of views without constructing an explicit 3D representation."
date: 2026-11-19T22:12:49+05:30
tags: [ComputerVision, VideoGeneration, DiffusionModels, AIResearch, GenerativeAI]
categories: ["AI", "Computer Vision", "Generative AI", "Machine Learning", "Video Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# AVM Generates Video Streams Without Explicit 3D Representations

Researchers have presented the Autoregressive View Model (AVM), a framework that generates scenes as a stream of views without constructing an explicit 3D representation. 

## 🧩 How it works
AVM uses a unified in-context interface to condition on images or videos, generating short clips along a requested camera path. Visual context grounds reconstruction and interpolation, while a learned prior enables extrapolation into unseen regions. 

## ⚙️ Key details
- The model retrieves relevant views from inputs and generated history to form a bounded active context.
- A pretrained bidirectional video diffusion transformer was fine-tuned with flow matching in an N-in-1-out formulation.
- A causal model was subsequently tuned on its own rollouts to improve photorealism, reduce denoising steps, and limit long-horizon drift.
- Training was scaled to approximately 8 million scenes and video clips.
- Evaluation covers benchmarks for camera control, text control, visual quality, dynamics, sparse and 4D reconstruction, and long-horizon consistency.

## 💡 Why it matters
The results demonstrate that AVM adapts to diverse input and output settings through a single in-context interface. Additionally, the broader field is addressing variable-length data through frameworks like Variable Length Diffuse Everything (VL-DE), which handles variable length via an insertion-based mechanism rather than padding, allowing for generation on arbitrary state spaces such as layout and molecule generation.

#ComputerVision #VideoGeneration #DiffusionModels #AIResearch #GenerativeAI

---

*Source: [Autoregressive View Model](https://arxiv.org/abs/2611.23417v1)*
*Source: [Variable Length Diffuse Everything: Arbitrary Length Generative Modeling on Arbitrary State Spaces](https://arxiv.org/abs/2611.23684v1)*
