---
title: "FedFIbOS Introduces Fisher Information for Heterogeneous Federated Learning Submodelling"
slug: "fedfibos-introduces-fisher-information-for-heterogeneous-federated-learning-submodelling"
description: "Researchers have proposed FedFIbOS (Fisher Importance-based Optimal Submodelling), a new method for heterogeneous federated learning that uses Fisher Information to select submodel parameters for..."
date: 2026-09-18T22:02:10+05:30
tags: [FederatedLearning, FisherInformation, MachineLearning, Submodelling]
categories: ["AI", "Machine Learning", "Distributed Computing", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# FedFIbOS Introduces Fisher Information for Heterogeneous Federated Learning Submodelling

Researchers have proposed FedFIbOS (Fisher Importance-based Optimal Submodelling), a new method for heterogeneous federated learning that uses Fisher Information to select submodel parameters for clients with diverse computational capacities.

## 🔍 Overview
In heterogeneous federated learning, clients train capacity-constrained submodels to collaboratively train a global model. FedFIbOS addresses a fundamental gap in existing methods, which often rely on heuristic importance measures like parameter magnitude that lack theoretical justification for supporting convergence.

## 🧩 How it works
FedFIbOS implements a principled criterion derived from minimizing submodel masking error:

* **Theoretical Formulation**: Submodel selection is formulated through a Fisher-weighted quadratic masking surrogate.
* **Selection Rule**: The method uses a raw Fisher top-$k$ rule, which solves the surrogate under a Fisher-dominant ranking condition.
* **Convergence**: The approach retains the convergence structure of the underlying masked federated optimization bound.

## ⚙️ Key details
* **Estimation**: Fisher scores are efficiently estimated using squared gradients from empirical diagonal Fisher information.
* **Efficiency**: The process enables adaptive and stable parameter selection without additional optimization overhead.
* **Performance**: In experiments using CIFAR-10, CIFAR-100, and AGNews under Dirichlet non-IID and pathological settings, FedFIbOS achieved approximately 10% higher accuracy than the state of the art.
* **Heterogeneity**: Improvements became more pronounced as heterogeneity increased.

#FederatedLearning #FisherInformation #MachineLearning #Submodelling

---

*Source: [FedFIbOS: Fisher Importance based Optimal Submodelling for Heterogeneous Federated Learning](https://arxiv.org/abs/2609.19559v1)*
