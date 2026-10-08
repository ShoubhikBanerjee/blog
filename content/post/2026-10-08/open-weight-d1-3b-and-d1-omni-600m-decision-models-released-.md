---
title: "Open-weight d1‑3B and d1‑omni‑600M decision models released with multimodal fast inference"
slug: "open-weight-d13b-and-d1omni600m-decision-models-released-with-multimodal-fast-inference"
description: "A new family of open‑weight decision models, d1‑3B and d1‑omni‑600M, is now available on Hugging Face. They are built on Liquid Foundation Models and are designed for fast, structured decisions with..."
date: 2026-10-08T22:04:21+05:30
tags: [DecisionModels, MultimodalAI, EdgeInference, OpenSource]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Computer Vision", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/hLsllw4zhC04cVGiV69v0.png"
author: "Shoubhik Banerjee"
draft: false
---

# Open-weight d1‑3B and d1‑omni‑600M decision models released with multimodal fast inference

A new family of open‑weight decision models, d1‑3B and d1‑omni‑600M, is now available on Hugging Face. They are built on Liquid Foundation Models and are designed for fast, structured decisions with multimodal inputs.

## 🔍 Overview
- d1‑3B scores **48.57** on Decision Index 0.2.1, the highest among models under 10 B parameters.
- d1‑omni‑600M, an early research release, supports **text + image** or **text + audio** inputs.
- Both models are open‑weight and can be downloaded from Hugging Face.

## 🧩 How it works
- **Backbones**
  - d1‑3B is trained from **LFM2.5‑VL‑3B**, a decoder‑only visual‑language model.
  - d1‑omni‑600M is trained from **LFM2.5‑Encoder‑350M**, a bidirectional encoder that adds vision and audio encoders.
- **Decision‑only architecture** – unlike generative models, these models answer in a single forward pass and do not produce tokens.
- **Multimodal support**
  - d1‑3B: text + image.
  - d1‑omni‑600M: text + image **or** text + audio.

## ⚙️ Key details
| Model | Parameters (≈) | Input modalities | Backbone | Notable strength |
|-------|----------------|------------------|----------|------------------|
| d1‑3B | 3 B | Text, Image | LFM2.5‑VL‑3B (decoder‑only) | Highest decision quality under 10 B; edge inference < 50 ms |
| d1‑omni‑600M | 600 M | Text + Image **or** Text + Audio | LFM2.5‑Encoder‑350M (bidirectional) | Good performance with a quarter of the parameters of a 2 B baseline |

- **Benchmark performance**
  - d1‑3B achieves a mean score of **82.9**, the highest in the benchmark table and above Decider 4B.
  - d1‑omni‑600M scores **78.4**, surpassing Decider 2B (77.1) with only a quarter of the parameters.
  - Benchmarked on seven public datasets covering reading comprehension, toxicity detection, intent classification, medical QA, and cross‑lingual understanding.
- **Speed**
  - Edge inference (NVIDIA Jetson): 16 ms (AGX Thor), 26 ms (AGX Orin), 50 ms (Orin Nano) per question; under 50 ms on all measured devices.
  - Three questions take only 1.3× the time of one (AGX Thor: 16 ms → 20 ms).
  - GPU inference (GeForce RTX 4090, Jetson AGX Orin): under 10 ms per question; 384 px image processed in under 18 ms.
  - No speed numbers reported for d1‑omni‑600M in this release.
- Vision capability of d1‑3B validated on standard vision benchmarks; d1‑omni‑600M handles all three modalities, though private vision and audio decision benchmarks are not reported.

## 🚀 Availability
- Both models are **open‑weight** and can be downloaded from Hugging Face:
  - `d1‑3B`
  - `d1‑omni‑600M`
- Demo space: **System One Arcade** on Hugging Face.
- d1‑omni‑600M model card provides usage instructions.

## 💡 Why it matters
- d1‑3B delivers the **highest decision quality** for its size, making it suitable when accuracy is paramount.
- d1‑omni‑600M offers strong performance with a **small footprint**, ideal for resource‑constrained environments.
- Fast single‑pass inference enables real‑time structured decision making on edge devices.


![figure](https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/WgfT8N8Xyb6lBxSif7XLO.gif)

![figure](https://cdn-uploads.huggingface.co/production/uploads/644249b08443bce4c9890a0f/ZMoThfdqzAz8cbxweVQfO.gif)

#DecisionModels #MultimodalAI #EdgeInference #OpenSource

---

*Source: [Multimodal open d1 decision models for the edge](https://huggingface.co/blog/LiquidAI/open-d1)*
