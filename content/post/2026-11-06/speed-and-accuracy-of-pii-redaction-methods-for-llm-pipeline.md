---
title: "Speed and Accuracy of PII Redaction Methods for LLM Pipelines"
slug: "speed-and-accuracy-of-pii-redaction-methods-for-llm-pipelines"
description: "Enterprises are increasingly sending free‑text inputs that contain personally identifiable information (PII) – names, phone numbers, email addresses, home addresses and dates of birth – to large..."
date: 2026-11-06T18:03:32+05:30
tags: [PII, LLM, Redaction, Privacy]
categories: ["AI", "Machine Learning", "Data Privacy", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Speed and Accuracy of PII Redaction Methods for LLM Pipelines

Enterprises are increasingly sending free‑text inputs that contain personally identifiable information (PII) – names, phone numbers, email addresses, home addresses and dates of birth – to large language models (LLMs). Once a prompt is sent, the raw text is copied into provider systems, application logs and observability traces. Redacting PII before the call is an obvious control, but teams have lacked concrete numbers on latency impact and coverage.

## 🔍 Overview
- Enterprise projects often include PII in free‑text prompts to LLMs.
- Unredacted prompts are stored in provider systems, logs, and observability traces.
- The new paper provides the first quantitative comparison of redaction approaches for LLM pipelines.

## ⚙️ Redaction Designs Compared
The study evaluates four designs that can be dropped into any LLM pipeline:
1. **Pure regular‑expression (regex) redactor**
2. **Microsoft Presidio** running on a spaCy model
3. **Hybrid** – Presidio finds person names, regex handles structured identifiers
4. **Fast hybrid** – calls spaCy’s named‑entity component directly

All designs share a *known‑entity* rule that removes the person already being handled and use a consistent placeholder scheme so the LLM can still distinguish individuals after redaction.

| Design | PII coverage | Business terms retained | Median latency (ms) |
|--------|--------------|------------------------|---------------------|
| Regex | 88.9% | N/A | 0.20 |
| Presidio | 100% | 100% | 37.59 |
| Hybrid | 100% | 100% | 30.23 |
| Fast hybrid | 100% | 100% | 13.48 |

## 📊 Evaluation Setup
- **Workflow:** ProfileAssist, which converts resumes into structured profiles.
- **Data:** 100 synthetic resumes (average 523 characters) containing **900 PII values** and **600 business terms** that must survive redaction.
- **Baseline:** Median LLM call latency of **9,120 ms**.

## 🚀 Results
- Regex is fastest (0.20 ms) but misses 11.1 % of PII because it cannot discover unknown names.
- Presidio, hybrid, and fast hybrid achieve **100 % PII removal** while preserving **100 % of business terms**.
- Their latencies range from **13.48 ms** (fast hybrid) to **37.59 ms** (Presidio).
- Compared with the 9,120 ms LLM request, even the slowest option adds only **0.41 %** overhead.

## 💡 Recommendation
- Adopt the **fast hybrid** design as the default redaction layer for LLM pipelines handling personal data.
- Keep a pure regex redactor as a **safety net**, not as the sole control.

*Submitted on 5 Nov 2026.*

#PII #LLM #Redaction #Privacy

---

*Source: [Redacting Personal Data: A Speed and Accuracy Comparison of Regex, Presidio and Hybrid Designs](https://arxiv.org/abs/2611.07633v1)*
