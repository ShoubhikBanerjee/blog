---
title: "LLMs Enable Japanese SDRT Discourse Parsing with Performance Matching English"
slug: "llms-enable-japanese-sdrt-discourse-parsing-with-performance-matching-english"
description: "Discourse parsing based on Segmented Discourse Representation Theory (SDRT) has been extended to Japanese using large language models (LLMs). The work constructs a Japanese SDRT corpus by translating..."
date: 2026-10-28T18:02:11+05:30
tags: [JapaneseNLP, DiscourseParsing, SDRT, LLMs]
categories: ["AI", "Natural Language Processing", "Computational Linguistics", "Machine Learning", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# LLMs Enable Japanese SDRT Discourse Parsing with Performance Matching English

Discourse parsing based on Segmented Discourse Representation Theory (SDRT) has been extended to Japanese using large language models (LLMs). The work constructs a Japanese SDRT corpus by translating existing English SDRT corpora with an LLM and demonstrates comparable parsing performance across the two languages.

## 🔍 Overview
- **Paper title**: *Japanese Discourse Structure Analysis Based on Segmented Discourse Representation Theory Using LLMs*  
- **Submitted**: 27 Oct 2026 to arXiv Computer Science > Computation and Language.
- Goal: Address the lack of Japanese SDRT corpora and test cross‑lingual applicability of SDRT‑based discourse parsing.

## 🧩 How it works
- **Corpus creation**: Existing English SDRT corpora were translated into Japanese using an LLM, producing a Japanese SDRT corpus.
- **Model evaluation**: Both prompt‑based LLMs and fine‑tuned LLMs were evaluated on the English and Japanese datasets.

## 📊 Findings
- **Performance**: Models achieved comparable parsing performance between English and Japanese, indicating cross‑lingual applicability of SDRT‑based discourse parsing.
- **Ablation analysis**:
  - Most examined Japanese discourse markers had little impact on results.
  - Model predictions relied heavily on contextual discourse relations rather than the content of context clauses.
- **Interpretation**: The strong reliance on structural context may explain why performance remains similar despite substantial typological differences between English and Japanese.

## 💡 Why it matters
- Demonstrates that SDRT‑based discourse parsing can be transferred to typologically distant languages with minimal loss in accuracy.
- Highlights the role of contextual discourse relations over language‑specific markers in LLM‑driven parsing.
- Provides a new Japanese SDRT resource for future research in discourse analysis and multilingual NLP.

#JapaneseNLP #DiscourseParsing #SDRT #LLMs

---

*Source: [Japanese Discourse Structure Analysis Based on Segmented Discourse Representation Theory Using LLMs](https://arxiv.org/abs/2610.36667v1)*
