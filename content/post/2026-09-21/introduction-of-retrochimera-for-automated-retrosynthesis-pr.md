---
title: "Introduction of RetroChimera for Automated Retrosynthesis Prediction"
slug: "introduction-of-retrochimera-for-automated-retrosynthesis-prediction"
description: "A new framework for retrosynthesis prediction called RetroChimera has been presented in a recent publication in the journal Nature. The model automatically proposes high-quality synthesis routes by..."
date: 2026-09-21T22:03:11+05:30
tags: [RetroChimera, retrosynthesis, chemistry, machinelearning]
categories: ["AI", "Machine Learning", "Chemistry", "Artificial Intelligence"]
image: "https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/RetroChimera-TWLIFB-1200x627-1.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of RetroChimera for Automated Retrosynthesis Prediction

A new framework for retrosynthesis prediction called RetroChimera has been presented in a recent publication in the journal Nature. The model automatically proposes high-quality synthesis routes by combining two models with complementary strengths.

## 🧩 How it works

RetroChimera utilizes a learned ensembling strategy to combine the ranked predictions of two sub-models. Each model assigns a learned, rank-dependent vote to predicted reactant sets, and votes are added when both models propose the same reaction. This allows the framework to leverage the strengths of both components:

| Model | Architecture | Strength |
| :--- | :--- | :--- |
| R-SMILES 2 | Transformer-based de-novo model | Reactions involving large changes over the course of the reaction |
| NeuralLoc | Graph neural network (GNN) based model | Reactions of low precedence and those involving more localized changes |

## ⚙️ Key details

Validation studies on RetroChimera include:
* The ability to recall rare reaction types.
* Successful fine-tuning on proprietary datasets.
* Successful zero-shot transfer.

In blind tests, PhD-level and expert chemists preferred RetroChimera’s individual reaction predictions and disconnections of complex molecules over those from its constituent sub-models, preceding models, recorded literature reactions, and the test set itself.

## 🚀 Availability

RetroChimera is open-source to help researchers accelerate the development of advanced materials and new medicinally relevant molecules. It is available via:
* GitHub (MIT license)
* Microsoft Foundry

![Architecture Diagram](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/FIG-2_retrochimera-figure-1c-scaled.png)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/FIG-2_retrochimera-figure-1c-scaled.png)

#RetroChimera #retrosynthesis #chemistry #machinelearning

---

*Source: [Improving synthesis prediction of small molecules at scale with RetroChimera - Microsoft Research](https://www.microsoft.com/en-us/research/blog/improving-synthesis-prediction-of-small-molecules-at-scale-with-retrochimera/)*
