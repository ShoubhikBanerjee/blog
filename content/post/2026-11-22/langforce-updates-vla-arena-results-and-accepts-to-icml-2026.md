---
title: "LangForce updates VLA-Arena results and accepts to ICML 2026"
slug: "langforce-updates-vla-arena-results-and-accepts-to-icml-2026"
description: "LangForce has released updated performance metrics on the VLA-Arena benchmark and received acceptance to ICML 2026. The framework addresses a specific pathology in Vision-Language-Action (VLA) model..."
date: 2026-11-22T18:07:49+05:30
tags: [LangForce, VLA, Robotics, ICML2026, StarVLA]
categories: ["AI", "Machine Learning", "Computer Vision", "Robotics", "Large Language Models"]
image: "https://avatars.githubusercontent.com/u/250105273?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LangForce updates VLA-Arena results and accepts to ICML 2026

LangForce has released updated performance metrics on the VLA-Arena benchmark and received acceptance to ICML 2026. The framework addresses a specific pathology in Vision-Language-Action (VLA) model training known as Information Collapse, where models degenerate into vision-only policies by ignoring language constraints.

## 🧩 How it works
LangForce tackles the Vision Shortcut problem by forcing models to ground actions in language rather than relying solely on visual observations. It employs a dual-branch architecture and Bayesian decomposition to optimize policies. 

- **Bayesian Decomposition**: The model explicitly estimates a vision-only prior $p(a \mid v)$ and a language-conditioned posterior $\pi(a \mid v, \ell)$.
- **Latent Action Queries**: Learnable queries are used to decouple vision-only and language-conditioned action distributions.
- **Optimization Objective**: The policy maximizes the conditional Pointwise Mutual Information (PMI) between actions and instructions, effectively penalizing vision shortcuts and rewarding language-grounded actions.

## 📊 Updated Performance
The team has updated LangForce results on VLA-Arena, achieving average success rates of:

| Benchmark Level | Success Rate |
| :--- | :--- |
| L0 | 84.2% |
| L1 | 38.8% |
| L2 | 24.1% |

Additional experiments on SimplerEnv and RoboCasa demonstrated an 11.3% improvement on the out-of-distribution (OOD) SimplerEnv benchmark using the exact same datasets as baselines. This approach also helps prevent the catastrophic forgetting of general multimodal reasoning capabilities common in standard VLA fine-tuning.

## 🚀 Availability
Model weights and checkpoints are publicly accessible for researchers and developers:

- **Hugging Face Collection**: LangForce checkpoints are available in the Hugging Face collection.
- **starVLA Integration**: LangForce has been integrated into starVLA, allowing for direct end-to-end training and evaluation on benchmarks such as LIBERO, SimplerEnv, and RoboCasa.
- **ICML 2026**: The work has been accepted to ICML 2026.
- **Media Coverage**: The work was covered by Xinzhiyuan (New Intelligence) and Tencent News.

#LangForce #VLA #Robotics #ICML2026 #StarVLA

---

*Source: [ZGC-EmbodyAI/LangForce](https://github.com/ZGC-EmbodyAI/LangForce)*
