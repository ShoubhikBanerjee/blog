---
title: "Benchmarking Transformer Models for Bangla Political Rhetoric Detection"
slug: "benchmarking-transformer-models-for-bangla-political-rhetoric-detection"
description: "A new benchmark study titled **BanglaRhet** was submitted on 7 Oct 2026, evaluating transformer‑based models on rhetorical and persuasion detection in Bangla political speech."
date: 2026-10-08T12:07:03+05:30
tags: [BanglaNLP, RhetoricalAnalysis, TransformerBenchmarks]
categories: ["AI", "Natural Language Processing", "Machine Learning", "Computational Linguistics"]
author: "Shoubhik Banerjee"
draft: false
---

# Benchmarking Transformer Models for Bangla Political Rhetoric Detection

A new benchmark study titled **BanglaRhet** was submitted on 7 Oct 2026, evaluating transformer‑based models on rhetorical and persuasion detection in Bangla political speech.

## 🔍 Overview
- Political discourse often uses rhetorical and persuasive language to frame narratives, influence public opinion, and mobilize audiences.
- Bangla NLP has progressed in sentiment analysis and opinion mining, but systematic benchmarking of transformer models for fine‑grained rhetorical and persuasion technique detection has been largely underexplored.

## 📚 Dataset – BanglaRhet
- Manually annotated corpus of **30,289** Bangla political speech segments.
- Collected from publicly available political news sources.

## 🎯 Tasks
- **Rhetorical technique detection** (single‑label):
  - contrast, repetition, exaggeration, metaphor, rhetorical questions
- **Persuasion technique detection** (single‑label):
  - blame assignment, call to action, unity call, moral, emotional, logical appeals

## ⚙️ Models Evaluated
- Four transformer‑based models:
  - BanglaBERT
  - BanglaBERT‑Base
  - SahajBERT
  - XLM‑RoBERTa‑Base
- Classical TF‑IDF baselines for comparison.

## 📈 Results
| Model | Rhetorical Technique Macro‑F1 | Persuasion Technique Macro‑F1 |
|-------|------------------------------|-------------------------------|
| BanglaBERT | 65.40% | 66.46% |
| BanglaBERT‑Base | – | – |
| SahajBERT | – | – |
| XLM‑RoBERTa‑Base | – | – |
| Classical TF‑IDF baseline (best tuned) | 46.20%* | 52.66%* |
*Derived from reported improvement: BanglaBERT outperforms baseline by 19.2 and 13.8 macro‑F1 points respectively.

- BanglaBERT achieves the highest performance on both tasks.
- Errors are mainly associated with semantic overlap among labels, figurative language, and class imbalance.

## 💡 Why It Matters
- Provides initial benchmark baselines for Bangla rhetorical and persuasion‑aware political discourse analysis.
- Highlights the need for context‑aware and multi‑label modeling approaches in future work.

## 🗒️ Next Steps Suggested by Authors
- Address label overlap and figurative language challenges.
- Explore multi‑label setups to capture multiple techniques within a single segment.
- Mitigate class imbalance through data augmentation or re‑sampling strategies.

#BanglaNLP #RhetoricalAnalysis #TransformerBenchmarks

---

*Source: [BanglaRhet: Benchmarking Classical and Transformer Models for Rhetorical and Persuasion Detection in Bangla Political Speech](https://arxiv.org/abs/2610.09464v1)*
