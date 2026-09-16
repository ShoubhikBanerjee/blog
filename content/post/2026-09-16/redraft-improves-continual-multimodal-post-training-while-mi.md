---
title: "ReDraft Improves Continual Multimodal Post-Training While Minimizing Knowledge Forgetting"
slug: "redraft-improves-continual-multimodal-post-training-while-minimizing-knowledge-forgetting"
description: "On September 15, 2026, researchers introduced ReDraft (Reference-Driven Revision and Fine-Tuning), a new method designed for the continual post-training of large multimodal models (VLLMs). Continual..."
date: 2026-09-16T12:08:47+05:30
tags: [VLLM, FineTuning, ReDraft, MachineLearning]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Model Training"]
author: "Shoubhik Banerjee"
draft: false
---

# ReDraft Improves Continual Multimodal Post-Training While Minimizing Knowledge Forgetting

On September 15, 2026, researchers introduced ReDraft (Reference-Driven Revision and Fine-Tuning), a new method designed for the continual post-training of large multimodal models (VLLMs). Continual post-training aims to add new capabilities to models while preserving pre-existing skills, but these goals typically pull in opposite directions. ReDraft solves this tension by having the model repair its own incorrect outputs using expert references, keeping the resulting training targets close to the model's current policy.

## 🔍 Overview

Traditional continual post-training approaches struggle to balance learning new tasks with maintaining prior knowledge:
* **Supervised Fine-Tuning (SFT):** Provides explicit target supervision that can successfully teach a task from near-zero accuracy. However, its off-policy targets move the model far enough to cause forgetting of prior capabilities.
* **On-Policy Methods:** Techniques like RLVR and self-distillation preserve policy proximity, but they provide very little learning signal when the model's policy cannot yet solve the task.

ReDraft overcomes these limitations by obtaining explicit, policy-proximate targets from the model's own failures.

## 🧩 How it works

Instead of replacing incorrect outputs with expert answers, ReDraft focuses on repairing the model's own output:
* **Rollout Revision:** When the model produces an incorrect rollout, it revises its own output using an expert response solely as a reference.
* **Verification:** A verifier evaluates the revised rollout, keeping the revision only if it is accepted.
* **Fine-Tuning:** The model is fine-tuned exclusively on the surviving accepted revisions.

This design ensures that each target remains explicit enough to provide a learning signal, yet highly probable under the base model. Data- and parameter-space analyses show that the resulting updates remain compact and follow SFT's learning direction more closely than alternative methods like OPSD.

## ⚙️ Key details

ReDraft was evaluated across Counting, Clock Reading, and Jigsaw tasks using Qwen2.5-VL-3B and Qwen2.5-VL-7B models, starting from near-zero accuracy on two of these tasks. Performance comparisons against other methods show a significant reduction in forgetting:

| Method | Target Task Gain (Points) | Prior-Task Loss (Points) |
| :--- | :--- | :--- |
| **ReDraft** | 56.9 | 1.5 |
| **SFT** | 52.9 | 16.6 |
| **OPSD** | 19.3 | 6.2 |

By reducing prior-task loss from 16.6 points (SFT) to 1.5 points, ReDraft achieves 11.3x less forgetting than standard Supervised Fine-Tuning while also outperforming OPSD along both measured axes.

#VLLM #FineTuning #ReDraft #MachineLearning

---

*Source: [ReDraft, Don't Just Distill: Reference-Driven Revision for Continual VLLM Post-Training](https://arxiv.org/abs/2609.16639v1)*
