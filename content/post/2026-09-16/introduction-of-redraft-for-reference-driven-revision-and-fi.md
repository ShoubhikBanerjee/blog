---
title: "Introduction of ReDraft for Reference-Driven Revision and Fine-Tuning"
slug: "introduction-of-redraft-for-reference-driven-revision-and-fine-tuning"
description: "Researchers have introduced ReDraft (Reference-Driven Revision and Fine-Tuning), a method that leverages a model's own failures to improve performance through self-revision and fine-tuning."
date: 2026-09-17T00:45:10+05:30
tags: [ReDraft, FineTuning, Qwen25VL, MachineLearning]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Model Optimization"]
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of ReDraft for Reference-Driven Revision and Fine-Tuning

Researchers have introduced ReDraft (Reference-Driven Revision and Fine-Tuning), a method that leverages a model's own failures to improve performance through self-revision and fine-tuning.

## 🧩 How it works

ReDraft utilizes the following process to generate training data:
* The model produces an incorrect rollout.
* An expert response is used only as a reference for the model to revise its own incorrect output.
* A verifier evaluates the revision; only those accepted by the verifier are kept.
* The model is fine-tuned on the surviving revisions.

## ⚙️ Key details

Analysis of the data and parameter space indicates that revised targets are more probable under the base model. The resulting updates stay compact and follow the direction of Supervised Fine-Tuning (SFT) more closely than On-Policy SFT with Distillation (OPSD).

## 💡 Why it matters

By repairing the model's own output instead of replacing it with an expert's, the method allows one objective to achieve multiple goals. Testing on Qwen2.5-VL-3B/7B across Counting, Clock Reading, and Jigsaw tasks showed the following results:

| Metric | ReDraft | SFT | OPSD |
| :--- | :--- | :--- | :--- |
| Target Task Gain | 56.9 points | 52.9 points | 19.3 gain |
| Prior-Task Loss | 1.5 points | 16.6 points | 6.2 loss |

#ReDraft #FineTuning #Qwen2.5-VL #MachineLearning

---

*Source: [ReDraft, Don't Just Distill: Reference-Driven Revision for Continual VLLM Post-Training](https://arxiv.org/abs/2609.16639v1)*
