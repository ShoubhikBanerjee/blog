---
title: "Self‑rewriting 27B language model improves accuracy without training"
slug: "selfrewriting-27b-language-model-improves-accuracy-without-training"
description: "The 27B language model was shown to rewrite its own weights, improving performance without a new training run."
date: 2026-11-18T22:09:17+05:30
tags: [SelfImprovingAI, LanguageModels, AIResearch]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Self‑rewriting 27B language model improves accuracy without training

The 27B language model was shown to rewrite its own weights, improving performance without a new training run.

## 🔍 Overview
- Traditional language models are trained once, frozen, and deployed; inference does not modify weights.
- A frontier model can edit the weights of a much smaller model.

## 🧩 How it works
- Given its weights, graded answers, and the ability to run itself, the 27B model diagnoses its failure and edits the weights behind it.
- The edit is performed without gradients or a separate training run, guided solely by the model’s own reasoning.
- Edits are applied only when the model’s internal tests support them, and each new edit replaces the previous one.

## ⚙️ Key results
- A single self‑edit raised accuracy on a fixed set of 490 unseen problems by 6.6 points.
- Across eight self‑editing sessions, accuracy continued to rise.
- The improvement resides in the weights, adding no extra computation per answer.
- The model repaired a corrupted copy of itself, lifting its performance on six unseen image benchmarks from 7 % to 70 % (83 % of the undamaged model).
- Scale matters: the 2B model made no edit, the 4B and 9B models broke themselves, and only the 27B model succeeded as a human would.

## 💡 Why it matters
- Model improvement can occur through a conversation‑style interaction rather than costly retraining.
- Persistent upgrades are possible without additional training infrastructure.
- The work blurs the line between training and inference, similar to how humans learn.

#SelfImprovingAI #LanguageModels #AIResearch

---

*Source: [Language Models Can Rewrite Their Own Weights](https://arxiv.org/abs/2611.21885v1)*
*Source: [What Does an Agent Need? Bundle-Aware Agent Resource Composition](https://arxiv.org/abs/2611.22030v1)*
*Source: [DeltaHarness: Self-Evolving Harnesses for Resource-Adaptive Tool Execution](https://arxiv.org/abs/2611.21688v1)*
