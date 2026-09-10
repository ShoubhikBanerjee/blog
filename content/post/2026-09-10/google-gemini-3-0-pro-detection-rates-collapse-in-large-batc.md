---
title: "Google Gemini 3.0 Pro Detection Rates Collapse in Large Batch Processing"
slug: "google-gemini-3-0-pro-detection-rates-collapse-in-large-batch-processing"
description: "Researchers tested the ability of Google Gemini 3.0 Pro to recover known contaminants from a corpus of 150 academic papers in the fields of medical research and supply chain management."
date: 2026-09-10T18:05:32+05:30
tags: [GoogleGemini, LLM, AIEvaluation, DataContamination]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Google Gemini 3.0 Pro Detection Rates Collapse in Large Batch Processing

Researchers tested the ability of Google Gemini 3.0 Pro to recover known contaminants from a corpus of 150 academic papers in the fields of medical research and supply chain management.

## ⚙️ Key details
The study used a contaminated corpus containing 450 injected contaminants of three types:

| Contaminant Type | Recovery Rate (Completed Evaluations) |
| :--- | :--- |
| Absurd out-of-context insertion | 75% |
| Semantic reversal | 50% |
| Typographical corruption | 50% |

## 🔍 Overview
Google Gemini 3.0 Pro was evaluated on its ability to recover a 180-contaminant answer-key subset across 60 documents. Performance varied based on the scale of the prompting regime:

* **Single document:** 50% recovery
* **Small batch:** 60% recovery
* **Large batch:** 2.8% recovery

## 💡 Why it matters
Detection performance collapses at scale, with the model failing via fabrication rather than abstention. In large batches, the model produced confident findings and invented contaminants that mimicked the style of planted material—such as "quantum-powered toaster" and "telepathic squirrel"—which did not appear in any document. Additionally, plausible corruptions most likely to occur in the wild are the ones most often missed.

#GoogleGemini #LLM #AIEvaluation #DataContamination

---

*Source: [When Auditors Fabricate: Batch-Size Degradation and Confident Hallucination in LLM Detection of Planted Document Contamination](https://arxiv.org/abs/2609.09696v1)*
