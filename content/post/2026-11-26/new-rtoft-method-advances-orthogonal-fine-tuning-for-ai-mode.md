---
title: "New RTOFT Method Advances Orthogonal Fine-Tuning for AI Models"
slug: "new-rtoft-method-advances-orthogonal-fine-tuning-for-ai-models"
description: "RTOFT (Restarted Tangent Orthogonal Fine-tuning) is a new approach to orthogonal fine-tuning that ensures exact orthogonality by using a polar decomposition only when the drift reaches a tolerance..."
date: 2026-11-26T12:19:42+05:30
tags: [AI, machinelearning, finetuning, orthogonaltransformation, RTOFT]
categories: ["AI", "Machine Learning", "AI Development", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# New RTOFT Method Advances Orthogonal Fine-Tuning for AI Models

## 🔍 Overview

RTOFT (Restarted Tangent Orthogonal Fine-tuning) is a new approach to orthogonal fine-tuning that ensures exact orthogonality by using a polar decomposition only when the drift reaches a tolerance threshold, rather than at every optimization step.

## 🧩 How it works

RTOFT uses the first-order update $W(I+S)$ of a weight $W$ with a skew-symmetric $S$, and restores exact orthogonality by a polar decomposition only when the drift $|S|_2$ reaches a tolerance $\tau$. The defect of $I+S$ is exactly $|S|_2^2$, so limiting the drift guarantees a defect of at most $\tau^2$ in every forward pass, independently of the loss, data, model, and optimizer.

## ⚙️ Key details

- RTOFT reduces training time of block-diagonal, subspace, and butterfly parameterizations from $1.10$-$1.58\times$ to $0.97$-$1.13\times$ that of LoRA
- Block-diagonal RTOFT version exceeds LoRA by $1.98\pm0.39$ points on the six-task average over five seeds
- At $\tau=0.10$, the largest drift stays between $0.10$ and $0.12$ across DeBERTaV3, Qwen, and diffusion models, whereas it ranges from $0.17$ to $1.65$ when restoring once per epoch
- In all seven settings of ablation, tangent update is worse without restoration than with it
- Restoring after every step yields no measurable accuracy gain over restoring at tolerance and costs $4.5$-$27.5\%$ more per step

## 💡 Why it matters

RTOFT provides a more efficient alternative to existing orthogonal fine-tuning methods by dynamically managing the orthogonality defect, achieving better performance with less computational overhead.

#AI #machinelearning #fine-tuning #orthogonaltransformation #RTOFT

---

*Source: [Amortizing Exact Orthogonality: Drift-Triggered Restoration for Orthogonal Fine-Tuning](https://arxiv.org/abs/2611.33589v1)*
