---
title: "New Wake-up System and TACT Benchmark for Spoken Dialogue Models"
slug: "new-wake-up-system-and-tact-benchmark-for-spoken-dialogue-models"
description: "Recent developments in intelligent assistant technologies introduce a novel wake-up system for contextual trigger detection and a new benchmark called TACT for evaluating full-duplex spoken dialogue..."
date: 2026-09-24T12:10:10+05:30
tags: [SpokenDialogue, AIAssistants, MachineLearning, NLP]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Speech Technology"]
author: "Shoubhik Banerjee"
draft: false
---

# New Wake-up System and TACT Benchmark for Spoken Dialogue Models

Recent developments in intelligent assistant technologies introduce a novel wake-up system for contextual trigger detection and a new benchmark called TACT for evaluating full-duplex spoken dialogue models.

## 🧩 How it works
The new wake-up system extends traditional direct keyword detection. After an initial wake word activation, the system utilizes reasoning to distinguish between unrelated speech and user commands to ensure context-aware engagement.

## ⚙️ Key details
To support these advancements, a data generation architecture was used to produce a 62.3-hour corpus of multi-speaker conversations featuring:
* Direct invocations
* Contextual follow-ups
* Non-addressed speech

Additionally, the TACT benchmark has been introduced with the following specifications:
* Scale: 9,728 episodes and 73.2 hours from five dyadic corpora
* Data: Each episode includes dialogue history, a per-speaker memory profile, and an annotator-derived posterior over six intent classes
* Scoring: Replaces binary fixed-window rules with a threshold-weighted continuous ranked probability score using intent-conditioned timing kernels fitted to human floor-transfer-offset distributions

## 💡 Why it matters
Traditional benchmarks for full-duplex models use binary fixed-window rules that reward silence or immediate response based on the completeness of the prior turn. TACT addresses this by recognizing that response offset appropriateness is conditional on the speaker's latent intent.

Performance and validation data include:
* Human topline score: 0.86
* Best model score (across eleven systems): 0.47
* Human judgment agreement: TACT shows a Spearman 0.81, compared to 0.46 for binary metrics
* Consistency: The system is nearly invariant to speaker profiles

## 🚀 Availability
The code, dataset, and trained models have been released to promote reproducibility and further advancements.

#SpokenDialogue #AIAssistants #MachineLearning #NLP

---

*Source: [Training Intelligent Voice Assistant Wakeup with Controllable Synthetic Conversations](https://arxiv.org/abs/2609.27037v1)*
*Source: [Neither Silence nor Overlap Is Failure: Intent-Conditioned Evaluation of Turn-Taking in Full-Duplex Spoken Dialogue Models](https://arxiv.org/abs/2609.27372v1)*
