---
title: "New 11‑Hour Video Series Shows How to Build Reasoning Models from Scratch"
slug: "new-11hour-video-series-shows-how-to-build-reasoning-models-from-scratch"
description: "A fresh set of eight coding videos (totaling about 11 hours) has been released that walks through building a reasoning model from a small pre‑trained Qwen3 LLM using Python and PyTorch. The series is..."
date: 2026-10-24T18:02:39+05:30
tags: [ReasoningModels, LLM, PyTorch, AIAgents]
categories: ["AI", "Machine Learning", "AI Agents", "Deep Learning", "Natural Language Processing"]
image: "https://substackcdn.com/image/fetch/$s_!1SoS!,w_1200,h_675,c_fill,f_jpg,q_auto:good,fl_progressive:steep,g_auto/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F519db120-1320-411b-adec-a88865345f2c_4083x2916.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# New 11‑Hour Video Series Shows How to Build Reasoning Models from Scratch

A fresh set of eight coding videos (totaling about 11 hours) has been released that walks through building a reasoning model from a small pre‑trained Qwen3 LLM using Python and PyTorch. The series is positioned as a sequel to the earlier *Coding LLMs from the Ground Up* course but can be followed without that prerequisite.

## 🔍 Overview
- The author recorded eight "reasoning model‑from‑scratch" lectures in the past few months and made them publicly available.
- Each video starts with a pre‑trained LLM and then adds evaluation, inference‑time scaling, reinforcement learning, and distillation methods.
- The material is presented as standalone content; prior articles on building LLMs from scratch are recommended but not required.

## 🧩 What the videos cover
- Setting up the Python/PyTorch environment and hardware recommendations (first video).
- Loading a small pre‑trained Qwen3 model.
- Implementing reasoning‑model techniques such as:
  - Evaluation metrics for text generation.
  - Inference‑time scaling methods.
  - Post‑training with reinforcement learning and verifiable rewards.
  - Model distillation.
- Demonstrations of the reasoning model functioning as the "engine" inside an agent harness.

## ⚙️ Technical details
- **Prerequisites:** comfortable with Python and PyTorch.
- **Compute:** early text‑generation and evaluation can run on a CPU; later training experiments benefit from a GPU.
- **Model focus:** a small pre‑trained Qwen3 model is used to keep the experiments approachable.
- **Repository:** includes hardware and environment recommendations, plus code for all eight videos.

| Figure | Description |
|--------|-------------|
| Figure 1 | Engine analogy for conventional LLMs, reasoning models, and agent harnesses (from *Components of a Coding Agent*). |
| Figure 2 | Overview of the topics covered in the video series. |

## 🚀 Availability
- All eight videos (≈ 11 hours) are now online and can be watched independently of prior courses.
- The accompanying repository contains the full code, data, and setup instructions.
- The author notes a short break but promises more LLM research roundups next month.

## 💡 Why it matters
- Reasoning models remain central to modern LLM agents; most current‑generation LLMs are already reasoning models or offer a reasoning mode.
- Adding post‑training via reinforcement learning makes the models capable of tackling harder problems such as math, code, and broader domains.
- In the agent‑harness architecture, the reasoning model acts as the engine, while the harness provides sophisticated context management and tool access.
- Understanding and building reasoning models from scratch is presented as an effective way to grasp how these systems work.


![figure](https://substackcdn.com/image/fetch/$s_!0A8p!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Ff0fa0f45-5efe-4937-a0e9-970b6f65ed8e_1868x986.png)

![figure](https://substackcdn.com/image/fetch/$s_!xQp0!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F67d8d671-53cc-4111-a3df-80ed733af3b5_1868x622.png)

![figure](https://substackcdn.com/image/fetch/$s_!GRkU!,w_1456,c_limit,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fa32da890-2402-4704-a90b-b46b4f64b95c_1544x864.png)

#ReasoningModels #LLM #PyTorch #AIAgents

---

*Source: [Build Your Own Reasoning Model: A Full Video Course](https://magazine.sebastianraschka.com/p/building-reasoning-models)*
