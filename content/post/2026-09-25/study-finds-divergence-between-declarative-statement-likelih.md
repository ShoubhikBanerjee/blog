---
title: "Study Finds Divergence Between Declarative Statement Likelihood and Prompted LLM Answering"
slug: "study-finds-divergence-between-declarative-statement-likelihood-and-prompted-llm-answering"
description: "Researchers have identified a systematic divergence between how large language models (LLMs) perform when using prompted answering versus likelihood ranking of declarative statements."
date: 2026-09-25T12:04:19+05:30
tags: [LLM, Evaluation, MachineLearning, NaturalLanguageProcessing]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Model Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# Study Finds Divergence Between Declarative Statement Likelihood and Prompted LLM Answering

Researchers have identified a systematic divergence between how large language models (LLMs) perform when using prompted answering versus likelihood ranking of declarative statements.

## 🧩 How it works
LLM evaluation is typically conducted through two primary methods:
* Prompting models to produce answers.
* Scoring candidate outputs using likelihood-based metrics.

In multiple-choice QA, standard likelihood-based scoring is conditioned on the question and answer set. This study examined a complementary protocol based on the likelihood ranking of declarative statements constructed from those same question-answer pairs.

## ⚙️ Key details
The study analyzed the following:
* **Models:** 95 decoder-only models ranging from 0.1B to 104B parameters.
* **Datasets:** 10 MCQA datasets.

## 💡 Why it matters
The research revealed distinct behaviors based on the evaluation method:

| Method | Performance Trend |
| :--- | :--- |
| Statement-likelihood accuracy | Remains comparatively stable across scale |
| Prompted answering | Improves sharply with scale and instruction-tuning |

These results indicate that task-conditioned answer selection and likelihood preferences over controlled declarative alternatives probe different aspects of model behavior and should not be treated as interchangeable.

#LLM #Evaluation #MachineLearning #NaturalLanguageProcessing

---

*Source: [Likelihood Ranking doesn't Scale Like Prompting in LLMs](https://arxiv.org/abs/2609.29390v1)*
