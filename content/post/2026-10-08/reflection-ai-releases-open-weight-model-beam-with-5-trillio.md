---
title: "Reflection AI releases open‑weight model Beam with 5 trillion parameters"
slug: "reflection-ai-releases-openweight-model-beam-with-5-trillion-parameters"
description: "Reflection AI announced its first open‑weight base model, **Beam**, on 5 October 2026 (U.S. time)."
date: 2026-10-08T12:07:03+05:30
tags: [ReflectionAI, OpenWeight, MoE, AIFactory, AutonomousCoding]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Open Source AI", "AI Startup"]
image: "https://assets.st-note.com/production/uploads/images/321675942/rectangle_large_type_2_b1e2bcae21ea76227f9af7f8841e8c88.png?fit=bounds&quality=85&width=1280"
author: "Shoubhik Banerjee"
draft: false
---

# Reflection AI releases open‑weight model Beam with 5 trillion parameters

Reflection AI announced its first open‑weight base model, **Beam**, on 5 October 2026 (U.S. time).

## 🔍 Overview
- Beam is the inaugural open‑weight model from the NVIDIA‑backed U.S. AI startup Reflection AI.
- The release came more than six months later than the company’s original target of early 2026.
- At the time of launch the company’s valuation had risen from $8 billion to $250 billion pre‑money, despite the model not having been released earlier.
- In the global landscape, Chinese models such as DeepSeek V4.1 Flash, Kimi K3, GLM‑5.3 and Qwen 3.8‑Max dominate the open‑weight segment, while U.S. closed‑model leaders remain OpenAI, Anthropic and Google.

## 🧩 How it works
- Beam uses a **Sparse Mixture‑of‑Experts (MoE)** architecture. Although the total parameter count is 5 010 billion, only **230 billion active parameters** are used per token.
- Pre‑training consumed **23.8 trillion tokens**.
- Training relied on NVIDIA GB300 hardware: **6 144 units** for pre‑training and **10 500 units** for reinforcement learning (RL) over four weeks, generating **over 100 million rollouts**.
- Scoring and learning were performed on a sandbox of approximately **1.3 billion** entries, with **nearly 1 million RL environments** prepared.

## ⚙️ Key details
| Attribute | Value |
|---|---|
| Total parameters | 5 010 billion |
| Active parameters per token | 230 billion |
| Pre‑training data | 23.8 trillion tokens |
| Pre‑training compute | 6 144 NVIDIA GB300 units |
| RL compute | 10 500 NVIDIA GB300 units (4 weeks) |
| Rollouts generated | >100 million |
| Sandbox size | ~1.3 billion |
| RL environments prepared | ~1 million |

## 💡 Why it matters
- Beam offers **inference quality comparable to GLM‑5.2** while requiring **one‑quarter to one‑third of the inference compute** thanks to its 23 billion‑active‑parameter design.
- The model does not claim superiority over current Chinese top models; the company itself notes that models such as Kimi K3 still lead in raw capability.
- Reflection AI’s broader goal is to provide an **“AI Factory”** that lets enterprises and governments train proprietary agents using their own data and GPU resources, rather than selling the model itself.
- The startup was founded in March 2024, is based in Brooklyn, NY, and is expanding hiring across New York, San Francisco, London and Washington DC.
- Founders **Misha Laskin** (CEO) and **Ioannis Antonoglou** (CTO), both former Google DeepMind staff, initially positioned the company around **Autonomous Coding** – AI that can independently understand, design, modify, test and improve software.
- In June 2026, during London Tech Week, UK Prime Minister Keir Starmer announced Reflection’s UK expansion plan: over 100 high‑skill hires in the next 12 months and a target of more than 1 000 employees in the UK within three years.


![figure](https://assets.st-note.com/production/uploads/images/321675942/rectangle_large_type_2_b1e2bcae21ea76227f9af7f8841e8c88.png?width=1200)

#ReflectionAI #OpenWeight #MoE #AIFactory #AutonomousCoding

---

*Source: [NVIDIAが賭ける「米国版DeepSeek」―Reflection AI初の自社オープンウェイト基盤モデル「Beam」の衝撃｜香川友志](https://note.com/kagawatomo/n/na7884bbda512)*
