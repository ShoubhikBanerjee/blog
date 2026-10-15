---
title: "Research explores the development and evaluation of in-context learning in language models"
slug: "research-explores-the-development-and-evaluation-of-in-context-learning-in-language-models"
description: "A study titled 'From Copying to Composition: How Language Models Develop In-Context Learning,' submitted on 13 October 2026, investigates how language models acquire and improve the ability to adapt..."
date: 2026-10-15T22:04:06+05:30
tags: [MachineLearning, LanguageModels, InContextLearning, AIResearch]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Research explores the development and evaluation of in-context learning in language models

A study titled "From Copying to Composition: How Language Models Develop In-Context Learning," submitted on 13 October 2026, investigates how language models acquire and improve the ability to adapt behavior based on prompts. The research indicates that in-context learning (ICL) does not develop as a uniform capability but follows distinct trajectories for prompt control, answer preference, and composition.

## 🔍 Overview
Researchers utilized a controlled diagnostic to distinguish between models that simply copy nearby demonstrations and those that integrate information across a prompt. Results across 17 models show:

* Approximately one-third prefer the copied answer.
* A small number of models remain undecided.
* The remainder favor rule-consistent answers, which correlates with higher accuracy.

## 🧩 How it works
Checkpoint analyses reveal that models begin prioritizing task-relevant tokens over conflicting examples long before their overall accuracy improves beyond chance. The research also explored training methods to influence these behaviors:

* Synthetic documents defining endings shift models toward compositional responses.
* Fine-tuning on definition exercises improves accuracy when prompts reassign label meanings.

## 💡 Why it matters
The study suggests that evaluation setups for ICL are complex. Investigators identified 8 aspects, such as task formulation and the number of in-context examples, to better measure model performance. Their findings yield concrete recommendations:

| Recommendation | Observation |
| :--- | :--- |
| Multiple Prompts | Consistently useful across models |
| Task Formulation | Depends on model scale |

Furthermore, the research confirms that gain over "no document" baselines does not necessarily establish that a model requires specific passage retrieval, highlighting the need for precise comparison models and conditions in future evaluations.

#MachineLearning #LanguageModels #InContextLearning #AIResearch

---

*Source: [From Copying to Composition: How Language Models Develop In-Context Learning](https://arxiv.org/abs/2610.19113v1)*
*Source: [How to Evaluate When You Don't Know How to Evaluate? Choosing Reliable Setups for Base Language Model Benchmarking](https://arxiv.org/abs/2610.19185v1)*
*Source: [Weighted Ensemble Sampling for Rare-Event Estimation in Language Models](https://arxiv.org/abs/2610.19202v1)*
*Source: [Whose Data, Whose Benchmark? A User-Centric Framework for Auditing Evaluation Resources](https://arxiv.org/abs/2610.19268v1)*
*Source: [Evaluating Compressed Memory: Dependence, Utility, and Content Benefit](https://arxiv.org/abs/2610.19373v1)*
