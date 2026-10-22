---
title: "NVIDIA Kumo Relational Foundation Model Beats Traditional Pipelines on Enterprise Databases"
slug: "nvidia-kumo-relational-foundation-model-beats-traditional-pipelines-on-enterprise-databases"
description: "NVIDIA introduced Kumo Relational, a pre‑trained relational foundation model that predicts directly on enterprise databases without task‑specific training or feature engineering."
date: 2026-10-22T18:03:17+05:30
tags: [NVIDIA, RelationalAI, MachineLearning, EnterpriseAI]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Data Engineering", "Enterprise Software"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6ad8e88370f69967fafc8703/i-Flass3NMPRmc6lVfwO_.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Kumo Relational Foundation Model Beats Traditional Pipelines on Enterprise Databases

NVIDIA introduced Kumo Relational, a pre‑trained relational foundation model that predicts directly on enterprise databases without task‑specific training or feature engineering.

## 🔍 Overview
- Operates on the database itself, respecting tables, foreign keys, and timestamps.
- Accepts a **Predictive Query Language (PQL)** statement that describes *what* to predict rather than *how*.
- Returns predictions in a single forward pass after gathering up to 10,000 historical examples as context.

## 🧩 How it Works
- **Pre‑training**: Trained once on synthetic relational data that mirrors real‑world datasets.
- **In‑context learning**: At inference time the model reads up to 10,000 context examples, each consisting of a local subgraph around an entity and its ground‑truth target (e.g., churn, demand, fraud).
- **Temporal handling**: For time‑based tasks the model replays historical database states, sampling entity‑centric subgraphs up to an anchor timestamp and using only data from before that point to avoid leakage.
- **Architecture**: A lightweight network processes each table independently, alternating column attention (relating values within a column) and row attention (relating features within a row). The model learns which columns and rows matter for the current prediction.
- **Agent integration**: Built to be called by agents; the PQL interface provides a simple way for agents to ask predictive questions.

## ⚙️ Performance
| Benchmark | Metric | Improvement over baseline |
|-----------|--------|---------------------------|
| RelBench V1 classification | AUROC | +~4 points vs. gradient‑boosted trees on expert‑engineered features |
| SAP SALT (out‑of‑the‑box) | MRR | +7 points vs. XGBoost on engineered features |
| SAP SALT (fine‑tuned) | MRR | +13 points vs. XGBoost |
| 41 tasks on 15 databases (overall) | MRR | +8% vs. AutoGluon ensembles |

Across 41 tasks on 15 databases, Kumo Relational beats supervised relational deep‑learning models, expert‑engineered gradient‑boosted tree pipelines, and AutoGluon ensembles. It also outperforms gradient‑boosted trees on RelBench V1 by nearly 4 AUROC points on average.

## 🚀 Availability
- Accessible through NVIDIA’s open‑source, GPU‑native **structured‑data‑models** library.
- Also offered as an NVIDIA **NIM** (NVIDIA Inference Model).
- Scales to databases with **500 B+ rows** and works for both humans and agents.
- Paper: https://arxiv.org/abs/2604.12596
- Documentation: https://docs.nvidia.com/sdgm/rfm/overview

## 💡 Why it Matters
- Eliminates weeks of feature engineering, task‑specific training, and pipeline tuning traditionally required for relational data.
- A single pre‑trained model replaces separate pipelines for individual tasks, turning a new prediction into a query rather than a full project.
- Demonstrates that foundation models for structured data can outperform the best supervised models, simplifying production deployment and enabling broader use of predictive analytics across organizations.


![figure](https://cdn-uploads.huggingface.co/production/uploads/6ad8e88370f69967fafc8703/FY-lkWrNmBYRFrosRD2Le.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6ad8e88370f69967fafc8703/OFX2a7xwBTfUEcbedTsfe.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6ad8e88370f69967fafc8703/9ITlubGvqGVnoy7j_NZDi.png)

#NVIDIA #RelationalAI #MachineLearning #EnterpriseAI

---

*Source: [NVIDIA Kumo Relational Outperforms Supervised Machine Learning on Relational Data, No Training Required](https://huggingface.co/blog/nvidia/kumo-relational)*
