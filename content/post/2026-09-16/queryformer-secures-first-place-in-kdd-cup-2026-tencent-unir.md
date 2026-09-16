---
title: "QueryFormer Secures First Place in KDD Cup 2026 Tencent UniRec Industrial Track"
slug: "queryformer-secures-first-place-in-kdd-cup-2026-tencent-unirec-industrial-track"
description: "Researchers have developed QueryFormer, a new architecture designed for post-click conversion rate (pCVR) prediction, which secured first place in the Industrial Track of the KDD Cup 2026 Tencent..."
date: 2026-09-16T22:05:42+05:30
tags: [QueryFormer, KDDCup2026, TencentUniRec, pCVR, MachineLearning]
categories: ["AI", "Machine Learning", "Predictive Modeling", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# QueryFormer Secures First Place in KDD Cup 2026 Tencent UniRec Industrial Track

Researchers have developed QueryFormer, a new architecture designed for post-click conversion rate (pCVR) prediction, which secured first place in the Industrial Track of the KDD Cup 2026 Tencent UniRec Challenge.

## 🔍 Overview
Post-click conversion rate prediction requires the joint modeling of sequential user behaviors and feature interactions. The KDD Cup 2026 Tencent UniRec Challenge sought a unified architecture capable of addressing both requirements.

## 🧩 How it works
QueryFormer utilizes a stackable unified field-sequence block to bridge behavioral sequences and non-sequential multi-field features. Key technical aspects include:

* **Query Generation**: The model generates queries through cross-attention, addressing a limitation in existing unified architectures that often use projection-based multi-layer perceptrons (MLPs) without explicit token-to-query attention.
* **Sequence Handling**: Sequence queries are packed into shared-parameter attention.
* **Efficiency**: The use of packed shared-parameter cross-attention results in an inference latency for H=8 that is only 1.89x that of H=1.

## ⚙️ Key details
Performance metrics and scaling results for QueryFormer include:

| Metric | Value |
| :--- | :--- |
| Official test AUC | 0.83254 |
| Post-competition scale-up AUC | 0.832713 |
| Validation AUC (H-scaling) | Improved from 0.84540 to 0.84615 |

Additional findings from the development process:
* Ablation studies identified query generation as the largest contributor to performance.
* A latency-aware scaling study was conducted across model width, depth, data, compute, and view width ($H$).
* In scaling tests, QueryFormer beat HyFormer at comparable budgets.

#QueryFormer #KDDCup2026 #TencentUniRec #pCVR #MachineLearning

---

*Source: [QueryFormer: Winning Solution for KDD Cup 2026 Tencent UniRec Challenge](https://arxiv.org/abs/2609.16548v1)*
