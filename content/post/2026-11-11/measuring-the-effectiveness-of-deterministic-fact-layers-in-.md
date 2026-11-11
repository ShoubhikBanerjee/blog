---
title: "Measuring the effectiveness of deterministic fact layers in rule-governed domains"
slug: "measuring-the-effectiveness-of-deterministic-fact-layers-in-rule-governed-domains"
description: "Researchers have evaluated the effectiveness of deterministic fact layers in language-model systems within rule-governed domains. The study focused on the Chinese sexagenary system used in BaZi chart..."
date: 2026-11-11T12:17:01+05:30
tags: [LLM, BaZi, AIResearch, MachineLearning]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Measuring the effectiveness of deterministic fact layers in rule-governed domains

Researchers have evaluated the effectiveness of deterministic fact layers in language-model systems within rule-governed domains. The study focused on the Chinese sexagenary system used in BaZi chart analysis to measure how models handle specific factual data.

## 🔍 Overview
The research examined how supplying various levels of facts affects model performance in rule-governed domains. The evaluation was conducted using the Chinese sexagenary system underlying BaZi chart analysis.

## ⚙️ Key details
The study parameters included:
* 682 items across twelve fact categories.
* 160 transit--natal collision items.
* Testing conducted closed-book, with a reference table, and with computed facts at increasing levels.

## 📊 Performance Results
Performance varied significantly depending on whether models answered directly or utilized a query-filtered layer.

In eleven open-weight models answering directly:
* Errors concentrated where attributes must be combined.
* No model achieved more than 4% accuracy for sexagenary days or 1% for collisions.
* Static attributes had no consistent effect.
* Most models remained near zero even when a complete relation list was provided.

Models using a query-filtered (exploratory) layer or proprietary reasoning:

| Model or Layer Type | Accuracy |
| :--- | :--- |
| Qwen3-8B and Qwen3-32B (query-filtered) | 78–92% |
| Four further models (query-filtered) | 96–100% |
| Three proprietary reasoning models | 68–95% of collisions (unaided) |

## 💡 Why it matters
* On chess positions, under predictions locked in advance, attributes do not substitute for relations and listed distractors are misattributed.
* The fact layer must supply computed interactions; how they are presented depends on the model and the domain.

#LLM #BaZi #AIResearch #MachineLearning

---

*Source: [Compute the Interactions, Not the Attributes: What a Fact Layer Must Supply in the Chinese Sexagenary System](https://arxiv.org/abs/2611.13597v1)*
