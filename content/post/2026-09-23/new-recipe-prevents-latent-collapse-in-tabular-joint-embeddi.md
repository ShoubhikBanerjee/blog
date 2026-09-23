---
title: "New Recipe Prevents Latent Collapse in Tabular Joint-Embedding Predictive Architectures"
slug: "new-recipe-prevents-latent-collapse-in-tabular-joint-embedding-predictive-architectures"
description: "Researchers have developed a new training recipe that prevents the latent term of a joint-embedding predictive architecture (JEPA) from collapsing when applied to a tabular foundation-model prior. In..."
date: 2026-09-23T12:05:26+05:30
tags: [MachineLearning, JEPA, TabularModels]
categories: ["AI", "Machine Learning", "Deep Learning", "AI Research"]
author: "Shoubhik Banerjee"
draft: false
---

# New Recipe Prevents Latent Collapse in Tabular Joint-Embedding Predictive Architectures

Researchers have developed a new training recipe that prevents the latent term of a joint-embedding predictive architecture (JEPA) from collapsing when applied to a tabular foundation-model prior. In previous attempts, the latent term collapsed and reduced the encoder to a constant map, but the new approach allows the latent term to survive to convergence beside the value objective.

## 🧩 How it works

Tabular foundation models traditionally learn to predict cell values in context, whereas world-model self-supervision relies on prediction in representation space. To prevent the latent term of the JEPA from collapsing, the new recipe adjusts how the model elements interact:

* The value head reads the encoder field directly rather than reading the predictor.
* The target is set as an exponential moving average (EMA) difference.

## ⚙️ Key details

To ensure a fair cost comparison, researchers evaluated both the JEPA arm and a value-only arm using a plateau rule to stop training, rather than a fixed step budget. This setup avoids confounding a training slowdown with a performance ceiling, as the value-only arm was observed to continue improving well past standard budgets.

At convergence, testing across 147 real datasets in one run per arm showed that the JEPA arm trailed the value-only arm:

* **Classification:** The JEPA arm recorded 32 wins to 70 losses against the value-only arm (or 29 wins to 63 losses when restricted to one entry per dataset name). The margin of difference on classification was small.
* **Regression:** The JEPA arm recorded 8 wins to 24 losses, with a wider margin of difference.
* **Consistency:** The win-loss count leaned in the same direction within each stratum and each benchmark.

In terms of training efficiency, the JEPA arm required more resources to reach its plateau compared to the value-only arm:

* **Steps:** The JEPA arm needed 1.42 times as many steps.
* **Time:** The JEPA arm required 1.66 times the wall-clock time.

#MachineLearning #JEPA #TabularModels

---

*Source: [A JEPA Recipe for Tabular Foundation Models](https://arxiv.org/abs/2609.25541v1)*
