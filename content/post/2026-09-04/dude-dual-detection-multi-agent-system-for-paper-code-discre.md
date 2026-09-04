---
title: "Dude: Dual-Detection Multi-Agent System for Paper-Code Discrepancy Detection"
description: "LLM‑empowered paper‑code discrepancy detection has received growing concern because the scaling of research submissions exceeds the manual review capability. In this paper, the authors propose Dude,..."
date: 2026-09-04T18:05:55+05:30
tags: [papercode, AIagents, discrepancydetection, LLM, research]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Dude: Dual-Detection Multi-Agent System for Paper-Code Discrepancy Detection

LLM‑empowered paper‑code discrepancy detection has received growing concern because the scaling of research submissions exceeds the manual review capability. In this paper, the authors propose Dude, the first Dual‑Detection Multi‑Agent System for paper‑code discrepancy detection.

## 🔍 Overview
- LLM‑empowered paper‑code discrepancy detection is under growing concern as submission volume outpaces manual review.
- Dude is presented as the first Dual‑Detection Multi‑Agent System targeting this problem.

## 🛠️ How it works
- The system tackles granularity asymmetry between paper‑language and code‑language, which introduces over‑interpretation and over‑reporting challenges that increase false positives.
- Two mechanisms are introduced to prevent false reporting:

| Component | Purpose |
|---|---|
| Granularity‑aligned negotiation | Aligns the granularity of paper‑language and code‑language to avoid over‑interpretation |
| Two‑stage salience‑filtering | Filters salient information to stop agents from falsely reporting discrepancies |

## 📈 Results
- Experimental results on real‑world paper‑code discrepancy datasets show Dude improves recall and precision by up to **22.8 %** and raises the F1 score by up to **18.7 %** compared to baseline methods.

## 💡 Why it matters
- By reducing false positives and improving detection accuracy, Dude helps alleviate the manual workload caused by the scaling of research submissions.

#papercode #AIagents #discrepancydetection #LLM #research

---

*Source: [Dude: A Dual-Detection Multi-Agent System for Paper-Code Discrepancy Detection](https://arxiv.org/abs/2609.03416v1)*
