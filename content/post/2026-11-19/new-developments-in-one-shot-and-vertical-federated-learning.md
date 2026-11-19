---
title: "New Developments in One-Shot and Vertical Federated Learning Frameworks"
slug: "new-developments-in-one-shot-and-vertical-federated-learning-frameworks"
description: "Federated learning enables collaborative model training without sharing datasets. Recent updates introduce two new frameworks to address existing limitations in multi-round communication and..."
date: 2026-11-19T22:12:49+05:30
tags: [FederatedLearning, AutonomousDriving, MachineLearning, PrivacyPreserving]
categories: ["AI", "Machine Learning", "Autonomous Vehicles", "AI Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# New Developments in One-Shot and Vertical Federated Learning Frameworks

Federated learning enables collaborative model training without sharing datasets. Recent updates introduce two new frameworks to address existing limitations in multi-round communication and centralized raw-data pooling: \method, a one-shot federated learning method for end-to-end autonomous driving, and VAFL, a Vertical Analytic Federated Learning framework.

## 🔍 Overview
Existing federated learning methods for autonomous driving typically require multi-round communication and lack closed-loop evaluation, while prior one-shot methods have mainly focused on perception tasks. To resolve these challenges, \method enables collaborative model training for end-to-end autonomous driving. Meanwhile, VAFL provides a Vertical Analytic Federated Learning framework for organizations holding complementary information, allowing them to collaborate without centralized raw-data pooling.

## 🧩 How it works
Both frameworks implement unique strategies to optimize collaborative learning:

* **\method Architecture:** It comprises multi-client calibration, anchor-based feature alignment, and token-wise consensus distillation to distill knowledge from heterogeneous models.
* **VAFL Architecture:** This framework fits classification and regression heads on fixed local representations through regularized least squares. It features an agent-assisted protected-computation workflow that supports two-party and multi-party collaboration.
* **VAFL Optimization:** To reduce fitting overhead, VAFL uses a full-dimensional equivalent solve that applies block factors directly to the target matrix, avoiding the construction of the full inverse. It also offers two width-reduction strategies:
  * *Local spectral projection with coefficient lifting*, which compresses the prediction space.
  * *Full-dimensional local fitting with low-rank cross-party correction*, which retains local components outside the collaboration subspace.

## ⚙️ Key details
Empirical evaluations demonstrate the effectiveness of both methods on standard benchmarks:

* **\method performance on Bench2Drive:** Closed-loop evaluation shows that in the one-shot setting, it achieves a Driving Score of 55.85 (4.07 points higher than prior work). In the multi-round setting, it reaches 60.35 after five communication rounds, marking the best performance among compared methods under the same number of communication rounds.
* **VAFL evaluation:** Experiments on five benchmarks demonstrated the accuracy-cost tradeoffs of the width-reduction strategies as well as their compatibility with diverse frozen backbones. The analysis of predictive performance and training time identified useful operating points and the limits of compression.

#FederatedLearning #AutonomousDriving #MachineLearning #PrivacyPreserving

---

*Source: [FedE2E: One-Shot Federated Learning for End-to-End Autonomous Driving with Closed-Loop Evaluation](https://arxiv.org/abs/2611.24254v1)*
*Source: [VAFL: A Vertical Analytic Federated Learning Mechanism for Efficient Crowdsourced Services via Closed-Form Solutions](https://arxiv.org/abs/2611.24367v1)*
