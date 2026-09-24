---
title: "AraGenre Shared Task for Hierarchical Arabic Genre Classification"
slug: "aragenre-shared-task-for-hierarchical-arabic-genre-classification"
description: "The AraGenre shared task was developed to address the limited availability of annotated data for Arabic and other low-resource languages through hierarchical, definition-guided genre classification."
date: 2026-09-24T22:03:57+05:30
tags: [AraGenre, ArabicNLP, GenreClassification, ZeroShotLearning]
categories: ["AI", "Natural Language Processing", "Machine Learning", "Arabic Language Technology"]
author: "Shoubhik Banerjee"
draft: false
---

# AraGenre Shared Task for Hierarchical Arabic Genre Classification

The AraGenre shared task was developed to address the limited availability of annotated data for Arabic and other low-resource languages through hierarchical, definition-guided genre classification.

## 🔍 Overview
Systems were required to assign two levels of classification to Arabic text segments:
* A broad communicative genre
* A fine-grained specific genre

## ⚙️ Key details
* **Data Composition**: Training and development sets consisted of limited, primarily synthetic and controlled examples. The final hidden benchmark utilized noisier, naturally occurring text including Classical Arabic, Modern Standard Arabic, and multiple dialects.
* **Zero-Shot Setting**: Participants were provided with natural-language definitions for 74 previously unseen specific genres, requiring systems to infer class semantics instead of memorizing fixed label-feature associations.
* **Participation**: The task saw 46 registrations and 373 submissions, with 17 teams completing the final evaluation.

## 📊 Results
While results indicated strong broad-genre recognition, a substantial gap remained in fine-grained classification under domain and linguistic variation.

| Team | Hierarchical Macro F1 |
| :--- | :--- |
| Thakaa | 0.7352 |
| HoangPhong (HP) | 0.7169 |
| NAMAA | 0.7013 |

#AraGenre #ArabicNLP #GenreClassification #ZeroShotLearning

---

*Source: [AraGenre 2026: A Hierarchical Definition-Guided Arabic Genre Classification Shared Task](https://arxiv.org/abs/2609.27387v1)*
