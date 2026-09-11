---
title: "New Evaluation Framework for Unsupervised Narrative Label Generation"
slug: "new-evaluation-framework-for-unsupervised-narrative-label-generation"
description: "Researchers have introduced a three-tier evaluation framework designed for unsupervised narrative label generation and tested it across seven disinformation datasets."
date: 2026-09-11T12:15:38+05:30
tags: [Disinformation, NarrativeLabeling, UnsupervisedLearning, DataEvaluation]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Information Security"]
author: "Shoubhik Banerjee"
draft: false
---

# New Evaluation Framework for Unsupervised Narrative Label Generation

Researchers have introduced a three-tier evaluation framework designed for unsupervised narrative label generation and tested it across seven disinformation datasets.

## 🧩 How it works
The evaluation framework consists of three tiers:

| Tier | Purpose |
| :--- | :--- |
| Recovery | Evaluation against a corpus's own taxonomy |
| Mining | Evaluation against external label sets |
| Discovery | Evaluation without predefined labels |

## ⚙️ Key details
The study compared clustering-based and graph-community-based pipelines, finding the following:

* **Balance:** In a corpus with two prominent topics, clustering can reduce one topic to 2% of generated labels, whereas graph-based pipelines remain balanced.
* **Singletons:** Graph outputs produced singletons (narrative labels derived from single claims) in 30-62% of cases; clustering cannot produce these.
* **Validation:** Human validation of discovery labels confirmed many singletons as recognizable disinformation narratives.

## 🚀 Availability
Human-validated narrative candidate labels have been released for the following datasets to support dataset extension and taxonomy development:

* Climate Obstruction
* PolyNarrative

#Disinformation #NarrativeLabeling #UnsupervisedLearning #DataEvaluation

---

*Source: [From Repetition to Recognition: Inductive Discovery of Disinformation Narratives](https://arxiv.org/abs/2609.11128v1)*
