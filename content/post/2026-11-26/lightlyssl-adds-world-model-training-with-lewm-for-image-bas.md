---
title: "LightlySSL Adds World Model Training with LeWM for Image-based Agents"
slug: "lightlyssl-adds-world-model-training-with-lewm-for-image-based-agents"
description: "LightlySSL, a Python library and computer vision framework for self-supervised learning and latent world models on images, has introduced new world model training capabilities. The update allows the..."
date: 2026-11-26T18:08:23+05:30
tags: [LightlySSL, SelfSupervisedLearning, WorldModels, ComputerVision, LeWM]
categories: ["AI", "Machine Learning", "Computer Vision", "AI Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/50146475?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LightlySSL Adds World Model Training with LeWM for Image-based Agents

LightlySSL, a Python library and computer vision framework for self-supervised learning and latent world models on images, has introduced new world model training capabilities. The update allows the system to learn how a scene responds to actions using the LeWM architecture, enabling planning in its own embedding space.

## 🧩 How it works

The new LeWM component learns from raw frames and actions without requiring rewards, labels, or a map of the environment. It trains through random play. Once trained, the model plans by imagining the outcome of each move within its embedding space. This allows agents to find paths to goals, such as navigating through a door to a target location, based solely on a picture of that goal.

## ⚙️ Key details

LightlySSL is built with a modular framework that exposes low-level building blocks, including loss functions and model heads. It is written in a PyTorch-like style and supports custom backbone models for self-supervised pre-training. The framework also supports distributed training using PyTorch Lightning.

Users can access the functionality by installing the library with PyTorch version 2.0 or later.

| Component | Description |
| :--- | :--- |
| LeWM | Learns scene responses to actions from raw frames and plans via imagined outcomes |
| LeJEPA | Self-supervised learning support added in May 2026 |
| LightlyStudio | Open-source project for visualizing, annotating, and managing data |
| LightlyTrain | New project making SSL and distillation pretraining accessible in a few lines of code |

## 🚀 Availability

The library is available for installation via pip. A commercial version is offered with additional features, including Docker support and pretraining models for embedding, classification, detection, and segmentation tasks. This commercial version also includes a platform with active learning and data curation features.

#LightlySSL #SelfSupervisedLearning #WorldModels #ComputerVision #LeWM

---

*Source: [lightly-ai/lightly](https://github.com/lightly-ai/lightly)*
*Source: [thu-ml/tianshou](https://github.com/thu-ml/tianshou)*
