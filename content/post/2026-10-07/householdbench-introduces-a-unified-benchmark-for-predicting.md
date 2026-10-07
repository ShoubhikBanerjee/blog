---
title: "HouseholdBench Introduces a Unified Benchmark for Predicting Household Economic Behavior"
slug: "householdbench-introduces-a-unified-benchmark-for-predicting-household-economic-behavior"
description: "A new benchmark called **HouseholdBench** has been released to evaluate large language models (LLMs) as predictors of household economic decisions across a range of settings."
date: 2026-10-07T18:06:06+05:30
tags: [LLM, HouseholdEconomics, Benchmark, PolicyResponse]
categories: ["AI", "Machine Learning", "Economics", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# HouseholdBench Introduces a Unified Benchmark for Predicting Household Economic Behavior

A new benchmark called **HouseholdBench** has been released to evaluate large language models (LLMs) as predictors of household economic decisions across a range of settings.

## 🔍 Overview
- LLMs are seen as a possible tool for building quantitative models of household decision‑making.
- Prior evaluations covered few surveys and did not examine how households respond to shifting economic conditions.

## 🗂️ HouseholdBench Dataset
- Unites **6 U.S. household surveys**.
- Contains **32 prediction tasks** covering numeric, categorical, and probabilistic outcomes.
- Targets domains such as **consumption, income, labor, expectations, and housing**.
- Tasks use past behavior, demographics, and macroeconomic conditions to test whether models can predict behavior and policy responses.

## ⚙️ Evaluation Setup
- **13 proprietary and open‑weight LLMs** were evaluated.
- Baselines: a **no‑change baseline** and a **gradient‑boosted tree model**.
- All models were tested on the full set of prediction tasks, including those that measure adjustment to policy changes.

## 📈 Results
- Most LLMs outperformed the no‑change baseline, even on policy‑response tasks.
- The best model reduced error on numeric outcomes by **12.2 %**.
- Across most tasks, **gradient‑boosted trees ranked first**.
- Leading proprietary LLMs approached the performance of gradient‑boosted trees, while open‑weight models lagged.
- Systematic over‑ and under‑prediction patterns were observed across different tasks.

| Model Type                | Relative Ranking | Performance Note                                 |
|---------------------------|------------------|--------------------------------------------------|
| Gradient‑Boosted Trees   | 1st              | Highest overall performance across tasks        |
| Leading Proprietary LLMs | 2nd (close)      | Approach tree performance; outperform baseline   |
| Open‑Weight LLMs          | 3rd (lag)        | Trail behind proprietary models in most tasks  |

## 🛠️ Methods to Boost Open‑Weight Models
- **Fine‑tuning** a 4 billion‑parameter open‑weight model enabled performance matching that of proprietary LLMs.
- **Aggregating 16 predictions per observation** further improved results.
- These improvements also generalized to policy‑response tasks, which were **not** part of the fine‑tuning set.

## 🚀 Availability
- The **datasets, code, and leaderboard** are publicly released on the authors’ website.
- The work was submitted on **6 Oct 2026** under the Computer Science > Computation and Language category.


#LLM #HouseholdEconomics #Benchmark #PolicyResponse

---

*Source: [HouseholdBench: Evaluating Large Language Models as Predictors of Household Economic Behavior](https://arxiv.org/abs/2610.07563v1)*
