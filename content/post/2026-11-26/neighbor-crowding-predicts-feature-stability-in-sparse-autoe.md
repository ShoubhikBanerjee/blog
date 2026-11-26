---
title: "Neighbor Crowding Predicts Feature Stability in Sparse Autoencoders"
slug: "neighbor-crowding-predicts-feature-stability-in-sparse-autoencoders"
description: "Researchers have introduced a method to predict feature stability in TopK Sparse Autoencoders (SAEs) using computationally inexpensive statistics derived from a single training run, addressing the..."
date: 2026-11-26T12:19:42+05:30
tags: [SparseAutoencoders, FeatureStability, TopK, RepresentationLearning, ComputationalEfficiency]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Representation Learning", "Neural Networks"]
author: "Shoubhik Banerjee"
draft: false
---

# Neighbor Crowding Predicts Feature Stability in Sparse Autoencoders

## 📚 Introduction

Researchers have introduced a method to predict feature stability in TopK Sparse Autoencoders (SAEs) using computationally inexpensive statistics derived from a single training run, addressing the challenge of identifying stable features without costly multi-seed training.

## 🔍 Overview

Sparse Autoencoders (SAEs) break apart polysemantic features into more sparse, interpretable ones, but distinguishing truly stable features from initialization artifacts has been difficult. Traditionally, this required training multiple SAE seeds and comparing learned features across seeds—a process that is computationally expensive.

## 🧩 How it Works

The new approach examines cross-seed feature stability across varying training token levels and demonstrates that stability in TopK SAEs can be highly predictably identified using six low-cost statistics extracted from a single training run.

## ⚙️ Key Details

- Among the six predictors, **neighbor crowding**—a geometric property of the dictionary—is the strongest single indicator.
- Features located in dense regions of the unit sphere are more likely to be stable compared to isolated ones.

| Statistic | Role |
|-----------|------|
| Neighbor Crowding | Strongest predictor of feature stability |

## 🚀 Availability

The work was submitted on 25 Oct 2026. A PDF and HTML (experimental) version are available for viewing.

## 💡 Why It Matters

This innovation offers a cost-effective alternative to multi-seed training by leveraging geometric properties of feature dictionaries to identify stable representations, making SAE analysis more efficient and accessible.

#SparseAutoencoders #FeatureStability #TopK #RepresentationLearning #ComputationalEfficiency

---

*Source: [Neighbor Crowding Predicts Feature Stability in Sparse Autoencoders](https://arxiv.org/abs/2611.33182v1)*
*Source: [Sparse-to-Sparse Feature Learning for Cross-Layer Analysis and Steering](https://arxiv.org/abs/2611.33640v1)*
