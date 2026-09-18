---
title: "Updating Federated Learning for Smart-City Water-Metering with Hegselmann-Krause Coalition Formation"
slug: "updating-federated-learning-for-smart-city-water-metering-with-hegselmann-krause-coalition-formation"
description: "Researchers have updated weight-driven coalition-formation schemes in federated learning (FL) to address statistical heterogeneity in Internet-of-Things (IoT) deployments, such as smart-city..."
date: 2026-09-18T18:02:43+05:30
tags: [FederatedLearning, IoT, SmartCities, MachineLearning]
categories: ["AI", "Machine Learning", "Internet Of Things", "Smart Cities"]
author: "Shoubhik Banerjee"
draft: false
---

# Updating Federated Learning for Smart-City Water-Metering with Hegselmann-Krause Coalition Formation

Researchers have updated weight-driven coalition-formation schemes in federated learning (FL) to address statistical heterogeneity in Internet-of-Things (IoT) deployments, such as smart-city water-metering networks. By modeling coalition formation as a Hegselmann-Krause (HK) bounded-confidence opinion-dynamics process, the new framework improves short-term water-consumption forecasting without increasing client-side computational or communication overhead.

## 🔍 Overview
In smart-city water-metering networks, each smart meter observes a household-specific consumption time series. Under this statistical heterogeneity, standard Federated Averaging (FedAvg) averages dissimilar local models into a single global model. This standard approach can fail to capture client-specific patterns. This updated framework addresses the limitation by forming client coalitions directly in the local-weight space and aggregating at the coalition level.

## 🧩 How it works
The framework builds on prior methods to structure on-device training:
* **Opinion-Dynamics Modeling:** Coalition formation is modeled as a Hegselmann-Krause (HK) bounded-confidence opinion-dynamics process acting directly on local weights.
* **Confidence Criteria Variants:** The system utilizes variants of the HK interaction based on Euclidean-distance and cosine-similarity confidence criteria.
* **Local Modeling:** The framework is applied to short-term water-consumption forecasting using local Long Short-Term Memory (LSTM) models.

## ⚙️ Key details
The proposed framework was evaluated on a real smart-metering dataset of water consumption against FedAvg, Per-FedAvg, FedProx, and FedAvg with Euclidean-distance or cosine-similarity coalition formation. 

| Metric | Achievement / Comparison |
| :--- | :--- |
| **Global Accuracy** | Highest overall, reaching 83-85% |
| **MAE vs. FedAvg** | Reduced average MAE by up to 54% |
| **MAE vs. FedProx** | Reduced average MAE by up to 39% |
| **MAE vs. Per-FedAvg** | Reduced average MAE by up to 24% |
| **Convergence** | Produces stable, endogenous coalition structures within at most ten inner iterations |
| **Overhead** | Incurs no additional client-side computation or communication compared to FedAvg |

#FederatedLearning #IoT #SmartCities #MachineLearning

---

*Source: [Opinion Dynamics-based Coalition Formation for Federated Learning in Heterogeneous IoT Systems](https://arxiv.org/abs/2609.19695v1)*
