---
title: "Replication study reveals limitations in Hindi extractive summarization methods"
slug: "replication-study-reveals-limitations-in-hindi-extractive-summarization-methods"
description: "Researchers have adapted the distributional-semantics extractive summarization method by Mohd, Jan and Shah (2020) for the Hindi language, utilizing Devanagari-appropriate components. Evaluation..."
date: 2026-09-25T22:04:20+05:30
tags: [NLP, Hindi, Summarization, Benchmarking]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Replication study reveals limitations in Hindi extractive summarization methods

Researchers have adapted the distributional-semantics extractive summarization method by Mohd, Jan and Shah (2020) for the Hindi language, utilizing Devanagari-appropriate components. Evaluation indicates that current Hindi benchmarking resources do not effectively reward non-lead content selection.

## ⚙️ Key details

The system was evaluated using the following corpora under a Devanagari-aware ROUGE implementation:

| Corpus | Evaluation Metric |
| :--- | :--- |
| XL-Sum (Hindi portion) | ROUGE-1 |
| FIRE ILSUM 2.0 Hindi | ROUGE-1 |

## 💡 Why it matters

* The replicated system performed significantly worse than a three-sentence lead baseline (Lead-3) on both corpora.
* A feature ablation study revealed that sentence position is the only contributing feature; other features incorrectly steer extraction toward long, entity-dense body sentences.
* Because human references tend to reuse the article lead, Hindi benchmarks are currently unable to reward models that extract non-lead content.
* TextRank exhibited identical failures, indicating these results are class-level rather than implementation-specific.

#NLP #Hindi #Summarization #Benchmarking

---

*Source: [Can Classical Semantic-Extractive Summarization Be Evaluated in Hindi? A Replication Study](https://arxiv.org/abs/2609.29090v1)*
