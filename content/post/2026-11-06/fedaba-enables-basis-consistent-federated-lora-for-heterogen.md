---
title: "FedAbA Enables Basis-Consistent Federated LoRA for Heterogeneous Ranks"
slug: "fedaba-enables-basis-consistent-federated-lora-for-heterogeneous-ranks"
description: "A new arXiv preprint titled **'Align Before Aggregation: Basis-Consistent Federated LoRA under Heterogeneous Ranks'** (submitted 5 Nov 2026) proposes a novel aggregation framework—FedAbA—that..."
date: 2026-11-06T12:11:11+05:30
tags: [FederatedLearning, LoRA, LLM, RankHeterogeneity]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Distributed Computing"]
author: "Shoubhik Banerjee"
draft: false
---

# FedAbA Enables Basis-Consistent Federated LoRA for Heterogeneous Ranks

A new arXiv preprint titled **"Align Before Aggregation: Basis-Consistent Federated LoRA under Heterogeneous Ranks"** (submitted 5 Nov 2026) proposes a novel aggregation framework—FedAbA—that addresses basis inconsistency when federating low‑rank adaptations of large language models across clients with different capacity limits.

## 📖 Overview
- Federated fine‑tuning of LLMs is increasingly important for environments where client devices have heterogeneous computational resources.
- Low‑rank adaptation (LoRA) with heterogeneous ranks makes such federated fine‑tuning practical, but existing server‑side aggregators operate on matrix updates that may be generated from client‑specific local bases.
- Basis inconsistency can destabilize the rank‑prefix dispatched to lower‑rank clients after server‑side refactorization.
- FedAbA is introduced as a **basis‑consistent** aggregation framework designed for heterogeneous ranks.

## 🧩 How it works
1. **Extract local basis** – Each client’s LoRA factors are used to recover its local basis.
2. **Align to global basis** – The local basis is aligned with the corresponding prefix of a global reference basis.
3. **Reconstruction** – A basis‑consistent reconstruction of each client’s matrix update \(\Delta W_i\) is built before aggregation.
4. **Weighted aggregation** – Reconstructions are aggregated with weights that combine client data size and a consistency score.
5. **Exact coefficient‑space SVD** – After aggregation, an exact SVD refactorization and gauge fixing are performed.
6. **Rank‑prefix dispatch** – The final, consistent low‑rank factors are dispatched back to clients.

## ⚙️ Key details
- The method operates in the weight space \(\mathbb{R}^{m\times n}\) where updates can be averaged, but the crucial step is ensuring the underlying bases match before averaging.
- Theoretical analysis clarifies why basis consistency matters and validates the consistency‑aware aggregation mechanism.
- FedAbA integrates both data‑size weighting and a *consistency score* to balance contributions from heterogeneous clients.

## 📊 Results
- Extensive experiments demonstrate that FedAbA **outperforms representative federated LoRA baselines**.
- The **largest gains** are observed under the **strongest rank heterogeneity**, confirming the method’s effectiveness when client capacities differ markedly.

## 💡 Why it matters
- Enables stable and accurate federated fine‑tuning of LLMs across a diverse set of devices, broadening the applicability of privacy‑preserving AI.
- Provides a systematic way to reconcile heterogeneous low‑rank representations, a common obstacle in real‑world federated deployments.
- The approach can be adopted in existing federated learning pipelines that already use LoRA, requiring only the additional basis‑alignment steps.


#FederatedLearning #LoRA #LLM #RankHeterogeneity

---

*Source: [Align Before Aggregation: Basis-Consistent Federated LoRA under Heterogeneous Ranks](https://arxiv.org/abs/2611.07598v1)*
