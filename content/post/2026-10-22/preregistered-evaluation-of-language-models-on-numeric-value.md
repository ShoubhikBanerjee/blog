---
title: "Preregistered Evaluation of Language Models on Numeric Values in Norwegian Law"
slug: "preregistered-evaluation-of-language-models-on-numeric-values-in-norwegian-law"
description: "A preregistered study evaluated language models on extracting numeric values from Norwegian statutes, regulations, and parliamentary decisions."
date: 2026-10-22T22:11:45+05:30
tags: [AIEvaluation, LanguageModels, NorwegianLaw, Preregistration]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Evaluation", "Legal Tech"]
author: "Shoubhik Banerjee"
draft: false
---

# Preregistered Evaluation of Language Models on Numeric Values in Norwegian Law

A preregistered study evaluated language models on extracting numeric values from Norwegian statutes, regulations, and parliamentary decisions.

## 🔍 Overview
- 916 items were extracted mechanically from Lovdata's open data, each carrying the dated history of its provision.
- The task asked language models for numeric values (NOK amounts, percentages, multiples of the National Insurance basic amount (G), and age limits) at a stated date.
- Each answer can be classified as correct, outdated, wrong, or uninterpretable.

## ⚙️ Study Design
- Two preregistered runs were performed on the same items.
- **First run**: involved five models (names listed publicly only after local analysis). Hypothesis H1 (outdated answers more frequent for values after a model's cutoff) could not be tested in substance; H2 and H3 were inconclusive.
- **Second run**: preregistered and published before any calls, analysing eight models.

## 📊 Results
- The pooled primary test of H1 in the second run supported the hypothesis (d = 17.8 percentage points, 95 % CI [7.7, 28.9], p = 0.0001).
- In preregistered sensitivity analysis S8 (outdated counted only for the most recent differing value), d = 3.9 [-3.6, 12.7] (p = 0.1754), an interval that contains 0, so support for H1 is not robust.
- H1 was supported in every other preregistered sensitivity analysis, but S8 is the only one giving both groups a single target value.
- Share of outdated answers equal to the most recent value (H2) was 56.1 % [46.6, 65.0], an interval that contains 0.5.
- The pooled test of a lower share correct in Nynorsk than in Bokmål (H3) was inconclusive.

### Model Performance (Correct on Primary Items)
| Model | Correct % |
|-------|-----------|
| Opus 5.5 | 46.7 % |
| Sonnet 4.6 | 40.2 % |

- Several models, among them Haiku 4.5, gave mostly uninterpretable answers.

## 📁 Data Availability
- Items and keys are withheld.
- Item IDs, per‑answer classes, code, and results are available on Zenodo.


#AIEvaluation #LanguageModels #NorwegianLaw #Preregistration

---

*Source: [norregel: a preregistered benchmark of dated numeric values in Norwegian law](https://arxiv.org/abs/2610.29207v1)*
