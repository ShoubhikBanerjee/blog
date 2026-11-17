---
title: "NVIDIA Presents Motus2: A Self-Evolving General World Model for Dexterous Manipulation"
slug: "nvidia-presents-motus2-a-self-evolving-general-world-model-for-dexterous-manipulation"
description: "NVIDIA has introduced Motus2, a self-evolving general world model designed for dexterous manipulation. This new AI development advances world modeling through both model scaling and data scaling,..."
date: 2026-11-17T18:10:30+05:30
tags: [AIagents, MachineLearning, Robotics, ComputerVision, DexterousManipulation]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Robotics", "Computer Vision"]
image: "https://avatars.githubusercontent.com/u/133188292?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Presents Motus2: A Self-Evolving General World Model for Dexterous Manipulation

NVIDIA has introduced Motus2, a self-evolving general world model designed for dexterous manipulation. This new AI development advances world modeling through both model scaling and data scaling, forming a closed decision-and-learning loop for policy improvement.

## 🧩 How it Works

Motus2 exposes three control interfaces through a single model with shared weights:

- A policy (world–action model)
- A simulator (action-conditioned world model)
- An evaluator (value model)

The system operates by proposing candidate action chunks, predicting their visual consequences through simulation, and assessing the predicted outcomes to enable policy improvement.

## ⚙️ Key Details

Motus2 progresses through multiple stages of data scaling:

- Large-scale monocular egocentric data
- Synchronized stereo egocentric data
- Robot-domain adaptation with robot trajectories and supplementary human–robot alignment data

The model incorporates additional features including global-autoregressive and hybrid-memory extensions, tactile feedback for contact-aware control, and is implemented on a biomimetic platform with stereo vision, dual arms, and dexterous hands.

The closed-loop formulation leverages curated expert demonstrations for action learning while using failed and suboptimal interactions to improve dynamics modeling and value learning.

## 🚀 Availability

Stage 1 pretraining checkpoints and code are released for:

- Video pretraining
- Video–action pretraining
- Supervised fine-tuning
- Memory training/inference

The code is available at: ```
git clone https://github.com/shengshu-ai/Motus2.git
cd Motus2
```

Each training stage includes installation, data preparation, and training instructions. Policy server and client examples are provided in the Stage 2, SFT, and Memory guides.

#AIagents #MachineLearning #Robotics #ComputerVision #DexterousManipulation

---

*Source: [shengshu-ai/Motus2](https://github.com/shengshu-ai/Motus2)*
