---
title: "AI Grading Performance and Sensitivity to Prompt Personas in Academic Exams"
slug: "ai-grading-performance-and-sensitivity-to-prompt-personas-in-academic-exams"
description: "Researchers have evaluated the performance of closed and open-weights models in grading Computer Vision and Machine Learning exams, discovering that specific prompt instructions can significantly..."
date: 2026-09-25T18:03:21+05:30
tags: [ComputerVision, MachineLearning, LLM, LoRA, AIgrading]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Educational Technology"]
author: "Shoubhik Banerjee"
draft: false
---

# AI Grading Performance and Sensitivity to Prompt Personas in Academic Exams

Researchers have evaluated the performance of closed and open-weights models in grading Computer Vision and Machine Learning exams, discovering that specific prompt instructions can significantly degrade model accuracy.

## ⚙️ Key details

Testing involved two independent exams:
* **Computer Vision exam:** 570 dual-graded students across 171 configurations.
* **Machine Learning exam:** 1,038 dual-graded students across 162 configurations.

Findings regarding accuracy include:
* The best performing configuration reached a mean absolute error (MAE) of 1.64/35.
* This outperforms the 2.61/35 MAE achieved between two human graders.

## 🔍 Vulnerabilities

The use of a short "strict grader" preamble impacted models differently:
* **Open-weights models:** 14 of 17 models were driven out of the graded band (MAE $\ge 8$), and three stopped grading entirely.
* **Closed flagship models:** Three vendors' models shifted calibration but remained within the graded band.
* **ML exam results:** The preamble worsened ten models (three collapsed and one refused), though it improved seven models that previously over-marked with neutral prompts.

Analysis of the preamble revealed:
* Damage was traced to two credit-withholding sentences rather than model scale or tone.
* The specific instruction "never give partial credit" alone caused two of three probed models to stop grading.

## 🧩 Improvements

Light LoRA fine-tuning was used to repair these vulnerabilities:
* One adapter trained on pooled $\sim 3,900$ graded examples brought five small open models to parity or better than a human grader.
* Sensitivity to the three harsh personas was reduced to $\le 0.32$ MAE.

## 🚀 Availability

The following resources have been released:
* Anonymised dataset
* Full ablation grid
* Grading, fine-tuning, and analysis pipelines

#ComputerVision #MachineLearning #LLM #LoRA #AIgrading

---

*Source: [Where LLM Graders Succeed and Break: Evidence from Two Computer-Science Exams](https://arxiv.org/abs/2609.29333v1)*
