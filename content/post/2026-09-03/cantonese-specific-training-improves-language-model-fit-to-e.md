---
title: "Cantonese-Specific Training Improves Language Model Fit to Eye-Tracking Data"
description: "Information-theoretic measures derived from autoregressive language models are widely used to characterize the expectations that shape human reading, but whether language-variety-specific training..."
date: 2026-09-03T12:16:06+05:30
tags: [Cantonese, LanguageModels, EyeTracking, Surprisal]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Cantonese-Specific Training Improves Language Model Fit to Eye-Tracking Data

Information-theoretic measures derived from autoregressive language models are widely used to characterize the expectations that shape human reading, but whether language-variety-specific training improves such psycholinguistic alignment remains unclear.

This question is still open for Cantonese, where recent NLP evaluations reported mixed benefits from Cantonese-specific training relative to Mandarin-oriented or general-purpose models.

## 🔍 Overview
Information-theoretic measures derived from autoregressive language models are widely used to characterize the expectations that shape human reading, but whether language-variety-specific training improves such psycholinguistic alignment remains unclear.

This question is still open for Cantonese, where recent NLP evaluations reported mixed benefits from Cantonese-specific training relative to Mandarin-oriented or general-purpose models.

## 🧩 Method
Using naturalistic Cantonese eye-tracking data, we compare two within-family adaptation contrasts: CKIP GPT-2 Tiny versus its lightly Cantonese-adapted JED351 derivative, and Qwen2.5-7B versus CantoneseLLM-7B, which underwent substantially more extensive Cantonese continued pretraining and instruction tuning.

From each model, we derive lexical surprisal, POS surprisal, entropy before the target, and entropy reduction.

- lexical surprisal
- POS surprisal
- entropy before the target
- entropy reduction

| Model | Training adaptation |
|---|---|
| CKIP GPT-2 Tiny | CKIP GPT-2 Tiny |
| JED351 | its lightly Cantonese-adapted JED351 derivative |
| Qwen2.5-7B | Qwen2.5-7B |
| CantoneseLLM-7B | CantoneseLLM-7B, which underwent substantially more extensive Cantonese continued pretraining and instruction tuning |

## 📊 Findings
Lexical surprisal and the joint four-metric model consistently favor CantoneseLLM-7B, followed by Qwen2.5-7B, CKIP, and JED351, whereas entropy reduction favors CKIP.

These results suggest that more extensive Cantonese-specific training can be associated with stronger predictive fit, while model rankings also depend on the information-theoretic measure being evaluated.

## 💡 Why it matters
These results suggest that more extensive Cantonese-specific training can be associated with stronger predictive fit, while model rankings also depend on the information-theoretic measure being evaluated.

#Cantonese #LanguageModels #EyeTracking #Surprisal

---

*Source: [Do Cantonese-Adapted Language Models Better Predict Cantonese Reading? A Cross-Model Eye-Tracking Evaluation](https://arxiv.org/abs/2609.02163v1)*
