---
title: "Research on LLM Output Diversity and Supervised Fine-Tuning"
slug: "research-on-llm-output-diversity-and-supervised-fine-tuning"
description: "New research examines the phenomenon of mode collapse in large language models (LLMs), where model outputs are under-diverse and resemble one another more often than responses from the population..."
date: 2026-09-17T00:45:10+05:30
tags: [LLM, SFT, MachineLearning, ModeCollapse]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Research on LLM Output Diversity and Supervised Fine-Tuning

New research examines the phenomenon of mode collapse in large language models (LLMs), where model outputs are under-diverse and resemble one another more often than responses from the population they represent.

## 🔍 Overview
Recent work by Doshi and Hauser (2024), Bisbee et al. (2024), and Xie et al. (2026) raised concerns regarding mode collapse. However, this new work demonstrates that whether mode collapse, or its opposite, occurs depends on the specific dataset and model used.

## 🧩 How it works
To compare model diversity against a target distribution, researchers used the following methods:
* Measuring the probability that two independently sampled responses from the same fixed prompt collide (coincide).
* Measuring the expected similarity of responses under a kernel.
* Applying a bias-variance decomposition of the expected gap between the model's and target's collision probabilities.

## ⚙️ Key details
Theoretical and experimental findings include:
* **SFT Impact**: Supervised fine-tuning (SFT) is not inherently biased toward mode collapse or its opposite; finite-sample SFT can leave a model under- or over-dispersed.
* **Convergence**: With sufficient SFT data, LLM output diversity converges toward that of the target distribution from which the data are sampled.
* **Diversity Bound**: The absolute gap is bounded by the square root of the Kullback-Leibler (KL) divergence from the target distribution to the model. A model sufficiently close to optimal under population cross-entropy cannot exhibit arbitrarily miscalibrated diversity.

## 💡 Why it matters
Experiments across three different setups confirmed that more target data moves model diversity toward the human or synthetic target level:

| Experiment Type | Dataset/Model Used |
| :--- | :--- |
| Synthetic | Small transformers on synthetic languages |
| Human Surveys | Four LLMs fine-tuned on human surveys |
| Human Code | LLMs fine-tuned on CodeNet (human code solutions) |

These results indicate that diversity miscalibration can arise from finite-sample error and shrinks as SFT better approximates the target distribution.

#LLM #SFT #MachineLearning #ModeCollapse

---

*Source: [Fine-Tuning Fixes Mode Collapse and Over-Dispersion in LLMs](https://arxiv.org/abs/2609.16454v1)*
