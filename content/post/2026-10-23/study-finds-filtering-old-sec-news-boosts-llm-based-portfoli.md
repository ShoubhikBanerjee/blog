---
title: "Study Finds Filtering Old SEC News Boosts LLM‑Based Portfolio Returns"
slug: "study-finds-filtering-old-sec-news-boosts-llmbased-portfolio-returns"
description: "Financial news continues to affect investment decisions even after it is published. A new analysis compares how reinforcement‑learning (RL) policies and a large language model (LLM) handle aging news..."
date: 2026-10-23T22:04:00+05:30
tags: [FinanceAI, ReinforcementLearning, LargeLanguageModels, PortfolioManagement]
categories: ["AI", "Finance", "Machine Learning", "Artificial Intelligence", "Investment Strategies"]
author: "Shoubhik Banerjee"
draft: false
---

# Study Finds Filtering Old SEC News Boosts LLM‑Based Portfolio Returns

Financial news continues to affect investment decisions even after it is published. A new analysis compares how reinforcement‑learning (RL) policies and a large language model (LLM) handle aging news when building portfolios.

## 🔍 Overview
- Financial news can influence decisions long after publication.
- Timely news may reach investors before prices fully adjust; older news may already be reflected in prices.
- The study evaluates two approaches to aging signals: keep the signals and give timing information to a portfolio policy, or filter the signals out before selection.

## 🧩 How it works
- A fixed LLM extracts signals from public SEC disclosures.
- These signals are fed either to RL policies or directly to the LLM, which then chooses portfolios.
- Historical tests covering 2023‑2025 include trading‑cost adjustments.

## 📊 Results
- **RL policies**: In a controlled test, RL choices responded to timing information, but historical returns showed no consistent benefit from adding timing data.
- **LLM‑based selection**: Filtering out old news produced the highest average net return, **18.43 % per year** when news delivery was delayed by four weeks.
- The LLM’s filtered‑news return exceeded the returns of all RL strategies that used news.

## 📈 Why it matters
- Filtering aging news can improve net returns for LLM‑driven portfolio allocation.
- The result suggests that, for this data set, older news may add noise rather than value when included in RL‑based strategies.

#FinanceAI #ReinforcementLearning #LargeLanguageModels #PortfolioManagement

---

*Source: [When News Gets Old: Portfolio Allocation with Reinforcement Learning and Large Language Models](https://arxiv.org/abs/2610.30564v1)*
