---
title: "Silent Evidence Loss Detector (SELD) spots hidden context deletions in LLMs"
slug: "silent-evidence-loss-detector-seld-spots-hidden-context-deletions-in-llms"
description: "Context compression is now routine for language models with long inputs, but a compressed context is useful only if it keeps the evidence for the answer."
date: 2026-11-11T18:02:06+05:30
tags: [LLM, ContextCompression, Evaluation]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# Silent Evidence Loss Detector (SELD) spots hidden context deletions in LLMs

Context compression is now routine for language models with long inputs, but a compressed context is useful only if it keeps the evidence for the answer.

## 🔍 Overview
- Existing checks compare the reader model's answer or its most likely words, and thus miss a frequent failure, silent evidence loss.
- Silent evidence loss occurs when key evidence is removed while the answer stays the same, leaving the answer unsupported and risky for other models that reuse the context.

## 🧩 How it works
- SELD (Silent Evidence Loss Detector) needs no training and no labels.
- Its principle is that when evidence is lost, a reader model's preferences among the answers it leaves unsaid shift even if its answer does not.
- By comparing these preferences before and after compression, SELD reveals losses that answer checks cannot see.

## ⚙️ Benchmark (SEL‑Pairs)
- SEL‑Pairs is a benchmark of length‑matched evidence and control deletions from three question‑answering datasets.

## 🚀 Results
- Quantitative and qualitative experiments with five reader models show that SELD consistently outperforms strong and recent baselines across compressors, compression rates and models.
- SELD identifies the evidence‑removing edit in **83%** of matched pairs with unchanged answers, against **70%** for the strongest baseline.
- These results show that evidence loss in compressed contexts can be detected even when the answer is unchanged.

## 💡 Why it matters
- Detecting silent evidence loss prevents unsupported answers from being propagated to downstream models.
- A training‑free detector can be applied to any compressor without additional data collection.

*Submitted on 14 Oct 2026*

#LLM #ContextCompression #Evaluation

---

*Source: [SELD: Detecting Silent Evidence Loss in Context Compression beyond the Answer](https://arxiv.org/abs/2611.12903v1)*
*Source: [Brasilidade: Measuring Brazilian Identity for Large Language Models](https://arxiv.org/abs/2611.12906v1)*
*Source: [How Post-Training Influences Verbalized Algorithmic Computation in Language Models](https://arxiv.org/abs/2611.13552v1)*
*Source: [IFRS Compliance Verification: An Open Multi-LLM Benchmark and Content-Conditioned Ensemble Classifier](https://arxiv.org/abs/2611.13595v1)*
