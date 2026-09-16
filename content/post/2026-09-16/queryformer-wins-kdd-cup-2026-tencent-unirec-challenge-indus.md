---
title: "QueryFormer Wins KDD Cup 2026 Tencent UniRec Challenge Industrial Track"
slug: "queryformer-wins-kdd-cup-2026-tencent-unirec-challenge-industrial-track"
description: "Researchers have introduced QueryFormer, a unified architecture designed for post-click conversion rate (pCVR) prediction that addresses the need to jointly model sequential user behaviors and..."
date: 2026-09-17T00:50:10+05:30
tags: [QueryFormer, KDDCup, pCVR, MachineLearning, TencentUniRec]
categories: ["AI", "Machine Learning", "Recommendation Systems", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# QueryFormer Wins KDD Cup 2026 Tencent UniRec Challenge Industrial Track

Researchers have introduced QueryFormer, a unified architecture designed for post-click conversion rate (pCVR) prediction that addresses the need to jointly model sequential user behaviors and feature interactions.

## 🧩 How it works
QueryFormer is built around a stackable unified field--sequence block that bridges behavioral sequences and non-sequential multi-field features. Key mechanisms include:

* **Query Generation**: The block generates queries through cross-attention.
* **Sequence Processing**: It packs sequence queries into shared-parameter attention.

## ⚙️ Key details
Performance and scaling metrics for QueryFormer include:

* **Competition Result**: Secured 1st place in the Industrial Track with an official test area under the ROC curve (AUC) of 0.83254.
* **Scale-up Performance**: A post-competition scale-up reached an AUC of 0.832713.
* **Scaling Effects**: Scaling the view width ($H$) improved validation AUC from 0.84540 to 0.84615 and outperformed HyFormer at comparable budgets.
* **Efficiency**: Packed shared-parameter cross-attention limits $H=8$ inference latency to 1.89x that of $H=1$.
* **Ablation Results**: Query generation was identified as the largest contributor to performance.

## 💡 Why it matters
Post-click conversion rate prediction requires a unified approach to handle both feature interactions and sequential user behaviors. QueryFormer provides an efficient, stackable block that maintains manageable inference latency while improving predictive accuracy.

#QueryFormer #KDDCup #pCVR #MachineLearning #TencentUniRec

---

*Source: [QueryFormer: Winning Solution for KDD Cup 2026 Tencent UniRec Challenge](https://arxiv.org/abs/2609.16548v1)*
