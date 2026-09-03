---
title: "New Method Audits Source-Free Unlearning to Recover Forgotten Classes"
description: "Class unlearning aims to remove a model's ability to recognize designated forget classes while preserving performance on retain classes. However, low forget accuracy after unlearning does not..."
date: 2026-09-03T22:06:46+05:30
tags: [MachineLearning, Unlearning, ModelAuditing, CIFAR, ComputerVision]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# New Method Audits Source-Free Unlearning to Recover Forgotten Classes

Class unlearning aims to remove a model's ability to recognize designated forget classes while preserving performance on retain classes. However, low forget accuracy after unlearning does not necessarily mean the class structure has been erased. Approximate unlearning methods can alter classifier decision boundaries while leaving recoverable structure in the representation. Prior work has shown that forget classes can be recovered, but existing approaches require real forget or retain samples, auxiliary data, or reference checkpoints. This study investigates class relearning in a strictly source-free setting, asking whether a forget class can be recovered through a classifier-head update using only the unlearned model.

## 🔍 Overview
The research addresses the gap between low forget accuracy and the actual erasure of class structure. It proposes a theoretical framework to determine if a single gradient step on a synthetic probe set can increase the expected logit margin of a forget class. The approach introduces a white-box audit method to quantify this recoverability without needing access to the original training data or checkpoints.

## 🧩 How it works
The proposed approach rests on a theoretical analysis establishing a sufficient alignment condition under which a single gradient step on a synthetic probe set increases the expected logit margin of the forget class. Building on this, the method proposes a white-box Source-Free Relearning Audit (SFRA). This process generates candidate embeddings in representation space and uses model-guided confidence filtering to construct high-confidence retain probes and low-confidence boundary-adjacent probes that are relabelled as the forget class. Gaussian sampling and Softmax confidence are used by default, while ablations with alternative proposal distributions and uncertainty criteria show that recoverability is not specific to these choices.

## ⚙️ Key details
To quantify recoverability, the study introduces the Relearning Score (RS), which jointly measures forget-class recovery and retain-accuracy preservation. The researchers report class-matched ΔRS relative to a retrained reference.

### Experimental Setup
The following models and datasets were used in the experiments:

| Dataset | Models |
| :--- | :--- |
| CIFAR-10, CIFAR-100, TinyImageNet | ResNet-18, ViT-B/16, Swin-T |

## 📊 Findings
Experiments on the datasets and models listed above show that several unlearning methods exhibit substantial source-free recoverability. Furthermore, for a subset of methods, this recoverability exceeds the matched retrained reference.

#MachineLearning #Unlearning #ModelAuditing #CIFAR #ComputerVision

---

*Source: [Source-Free Class Relearning: Diagnosing Forgetting in Class Unlearning](https://arxiv.org/abs/2609.02018v1)*
