---
title: "NVIDIA Releases Kumo Tabular Open Foundation Model for Tabular Data"
slug: "nvidia-releases-kumo-tabular-open-foundation-model-for-tabular-data"
description: "NVIDIA has released Kumo Tabular, an open foundation model for tabular classification and regression. Part of the NVIDIA Kumo Structured model collection, the model is available on Hugging Face and..."
date: 2026-09-29T22:02:51+05:30
tags: [NVIDIA, KumoTabular, TabularData, OpenSource, MachineLearning]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Data Science"]
image: "https://cdn-uploads.huggingface.co/production/uploads/684040a5de1ad7f4fcec9508/HyVlq-3d7EVj_M-m_TfHJ.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Kumo Tabular Open Foundation Model for Tabular Data

NVIDIA has released Kumo Tabular, an open foundation model for tabular classification and regression. Part of the NVIDIA Kumo Structured model collection, the model is available on Hugging Face and GitHub.

## 🔍 Overview
Kumo Tabular is designed to predict labels for new rows in a single forward pass given a table of labeled rows. It operates with the following characteristics:

* **No prerequisites:** Requires no training, no tuning, and no feature engineering.
* **Versatility:** Supports both classification and regression tasks.
* **Performance:** Ranks first on the TabArena, BeyondArena, TALENT, and ScoringBench benchmarks.
* **Data Handling:** Missing values are treated specially and require no imputation.

## 🧩 How it works
Kumo Tabular is a Transformer utilizing column, row, and in-context attention based on TabICL and TabPFN. The architecture processes data through several stages:

| Component | Function |
| :--- | :--- |
| Fourier features | Process numerical and categorical values using sines and cosines of learned frequencies with separate weights. |
| Column attention | Uses induced self-attention to learn the meaning of a value within its column distribution. |
| Row attention | Uses rotary positions to distinguish columns and learn how features interact. |
| [CLS] tokens | Four learnable tokens per row that act as the final readout for row compression. |
| Final Transformer | Operates on row embeddings where context rows attend to each other and query rows attend only to context rows. |
| Prediction Head | Converts query rows into class probabilities for classification or 999 quantiles for regression to provide point predictions and uncertainty estimates. |

To optimize performance, the model employs Test-GQA to shrink the cache for predictions and scales every query by a temperature that grows with the logarithm of the number of keys.

## ⚙️ Key details
Kumo Tabular was pretrained entirely on artificial tables sampled from a Structural Causal Model (SCM). The training process involves:
1. Drawing a configuration for table size, task, mechanisms, and missingness.
2. Linking hidden variables via a random causal graph using functions such as linear maps, small neural networks, trees, or Gaussian processes.
3. Designating some nodes as numerical or categorical columns and one as the target.
4. Post-processing to correlate columns, clip outliers, and inject missing values, followed by a tree-ensemble check to ensure a learnable signal exists.

## 🚀 Availability
* **Model Sizes:** Available in three sizes ranging from 28M to 215M parameters.
* **License:** Released under the OpenMDW-1.1 license for commercial use.
* **Implementation:** Runs through an open-source library.

#NVIDIA #KumoTabular #TabularData #OpenSource #MachineLearning

---

*Source: [NVIDIA Kumo Tabular Sets a New Accuracy-Efficiency Frontier for Tabular Prediction](https://huggingface.co/blog/nvidia/kumo-tabular)*
