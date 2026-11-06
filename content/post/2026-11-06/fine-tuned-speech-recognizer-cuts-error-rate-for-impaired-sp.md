---
title: "Fine‑tuned speech recognizer cuts error rate for impaired speech in SAPC2"
slug: "finetuned-speech-recognizer-cuts-error-rate-for-impaired-speech-in-sapc2"
description: "Speech recognition still works poorly for many people whose speech is affected by conditions such as ALS, Parkinson's disease, cerebral palsy, Down syndrome or stroke. In response, a team entered the..."
date: 2026-11-06T12:11:11+05:30
tags: [speechrecognition, accessibility, AI, machinelearning]
categories: ["AI", "Machine Learning", "Speech Technology", "Accessibility", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Fine‑tuned speech recognizer cuts error rate for impaired speech in SAPC2

Speech recognition still works poorly for many people whose speech is affected by conditions such as ALS, Parkinson's disease, cerebral palsy, Down syndrome or stroke. In response, a team entered the Speech Accessibility Project Challenge 2 (SAPC2) with a public speech recognizer that they fine‑tuned on the challenge data.

## 🔍 Overview
- The challenge focuses on improving automatic speech recognition (ASR) for speakers with speech impairments.
- The team’s submission was submitted on 5 Nov 2026.

## ⚙️ Approach
- Used a public transducer‑based speech recognizer.
- Fine‑tuned the model on the SAPC2 challenge data.

## 📊 Results
- **Best entry** achieved **7.81 % character error rate (CER)** on Test1, the first of two hidden test sets.
- The official baseline for the same set is **15.26 % CER**.
- Live entries executed on CPUs with a **combined median latency of about 0.9 seconds** and error rates of **7.96 %–8.07 %**.
- **Speaker adaptation:** On new speakers, fine‑tuning reduced errors most for those that an off‑the‑shelf recognizer finds hardest to understand.
- **Sentence familiarity:** Sentences already seen in training had far lower error rates (**2.58 %**) than new sentences (**6.42 %**), a larger difference than being a familiar speaker.

## 🧪 Evaluation Insights
- The authors close with lessons for evaluating such systems, emphasizing the impact of speaker difficulty and sentence familiarity on error rates.

## 📅 Timeline
- Submission date: **5 Nov 2026**.

*All figures and additional resources are available in the accompanying PDF/HTML versions of the paper.*

#speechrecognition #accessibility #AI #machinelearning

---

*Source: [Fine-Tuning a Transducer for Impaired Speech: Where the Gains Appear and What They Mean for Evaluation](https://arxiv.org/abs/2611.07587v1)*
