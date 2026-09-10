---
title: "Study Evaluates Retrieval-Based In-Context Learning for Detecting Defamatory Hate Speech"
slug: "study-evaluates-retrieval-based-in-context-learning-for-detecting-defamatory-hate-speech"
description: "With hate speech pervasive online, automatic detection of criminally relevant posts is essential. A new study examines retrieval‑based in‑context learning (RetICL) strategies for detecting defamatory..."
date: 2026-09-10T18:05:32+05:30
tags: [AI, HateSpeechDetection, InContextLearning, LegalAI]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Legal Technology", "AI Ethics"]
author: "Shoubhik Banerjee"
draft: false
---

# Study Evaluates Retrieval-Based In-Context Learning for Detecting Defamatory Hate Speech

With hate speech pervasive online, automatic detection of criminally relevant posts is essential. A new study examines retrieval‑based in‑context learning (RetICL) strategies for detecting defamatory offences under §§185‑187 StGB, the focus of GermEval 2026 Subtask 4.

## 🔍 Overview
- Hate speech is ubiquitous online; automatic detection is crucial for criminally relevant social‑media posts.
- The research targets defamatory offences defined in §§185‑187 StGB as part of GermEval 2026 Subtask 4.

## 🧩 Approach
- Evaluated a variety of retrieval‑based in‑context learning (RetICL) strategies.
- Compared prompting styles: zero‑shot, few‑shot, retrieval‑based demonstrations, and an optimized static set of demonstrations.
- Incorporated concrete legal knowledge into the inputs.

## ⚙️ Findings
- Few‑shot prompting beats zero‑shot.
- Retrieval‑based approaches provide only marginal gains over random demonstrations and fall behind an optimized static set of demonstrations.
- Supplying concrete legal knowledge helps, yet the choice of model outweighs every other system choice.
- Models over‑predict criminal relevance while missing 26‑57 % of criminally relevant posts, making them more suitable for triage rather than autonomous moderation.

| Prompting Strategy | Relative Performance |
|---|---|
| Zero‑shot | Baseline |
| Few‑shot | Beats zero‑shot |
| Retrieval‑based (random demos) | Marginal gain over zero‑shot |
| Optimized static demos | Outperforms retrieval‑based |

## 💡 Why it matters
- Automatic detection is vital given the prevalence of hate speech online.
- Recognizing the current models' tendency to over‑predict and miss a substantial share of relevant posts guides realistic expectations for their role in legal moderation pipelines.

#AI #HateSpeechDetection #InContextLearning #LegalAI

---

*Source: [MUCnoHARM@GermEval Shared Task 2026: Retrieval-based In-Context Learning for Defamatory Offences, and Where It Falls Short](https://arxiv.org/abs/2609.09791v1)*
