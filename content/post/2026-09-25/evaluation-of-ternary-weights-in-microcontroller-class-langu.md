---
title: "Evaluation of Ternary Weights in Microcontroller-Class Language Models"
slug: "evaluation-of-ternary-weights-in-microcontroller-class-language-models"
description: "Recent research has re-evaluated the performance of ternary (1.58-bit) weights in small-scale language models, specifically examining the claims regarding routed ternary blocks versus full-precision..."
date: 2026-09-25T22:04:20+05:30
tags: [LanguageModels, TernaryWeights, ModelQuantization, SSM]
categories: ["AI", "Machine Learning", "Model Optimization", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# Evaluation of Ternary Weights in Microcontroller-Class Language Models

Recent research has re-evaluated the performance of ternary (1.58-bit) weights in small-scale language models, specifically examining the claims regarding routed ternary blocks versus full-precision transformers.

## 🔍 Overview
Researchers conducted 98 byte-level runs on a single laptop using a fixed recipe and three seeds per cell to test model performance across different memory budgets.

## ⚙️ Key details
Findings regarding model architecture and performance include:

* **Small Budget (16M bytes):** Parameter-matched transformers showed a 22.6% span in validation loss based solely on depth and width choice. The best-shaped transformer tied with the routed model, suggesting previous reported margins were partly due to baseline-shape effects.
* **Large Budget (130M bytes):** The routed model outperformed three evaluated transformer shapes by 22.2-24.0%. However, a plain gated diagonal-SSM block outperformed the routed model by an additional 9.1%.
* **Routing Analysis:** The routed model's router placed most weight on its recurrent pathway, indicating that routing is not required for the observed gains.
* **Ternary Penalty:** The penalty for using ternary weights varied by architecture at the larger budget:
    * Best transformer: +5.3%
    * Routed model: +19.5%
    * Gated SSM: +28.1%

## 🧩 How it works
Certain technical constraints and training observations were noted:

* **Precision:** The evaluated transformers maintained learned positional embeddings in full precision (11-22% of parameters), making them less quantized than the models they were compared against.
* **Training Schedules:** A 90/10 full-precision-then-ternary schedule outperformed all-ternary training, but only when using a stage-2 learning rate approximately 10x the pretraining peak. At a conventional fine-tuning rate, this approach performed 15.3% worse.
* **Baselines:** The from-scratch baseline was not tuned for learning rate.

#LanguageModels #TernaryWeights #ModelQuantization #SSM

---

*Source: [Baseline Shape Decides the Verdict: A Controlled Re-Examination of Ternary Language Models at 60K Parameters](https://arxiv.org/abs/2609.29397v1)*
