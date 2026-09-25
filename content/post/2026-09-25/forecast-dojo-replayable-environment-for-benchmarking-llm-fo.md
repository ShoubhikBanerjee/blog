---
title: "Forecast-Dojo: Replayable Environment for Benchmarking LLM Forecasting Agents"
slug: "forecast-dojo-replayable-environment-for-benchmarking-llm-forecasting-agents"
description: "A new replayable environment called Forecast-Dojo has been released for benchmarking and training large‑language‑model (LLM) forecasting agents."
date: 2026-09-25T18:03:21+05:30
tags: [Forecasting, LLM, Benchmark, AIResearch]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Natural Language Processing", "AI Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# Forecast-Dojo: Replayable Environment for Benchmarking LLM Forecasting Agents

A new replayable environment called Forecast-Dojo has been released for benchmarking and training large‑language‑model (LLM) forecasting agents.

## 🔍 Overview
- Forecast-Dojo combines resolved prediction‑market questions with dated news, letting agents research an event and revisit their predictions at successive historical dates.
- The same tasks and tools support repeated evaluation, collection of training interactions, and feedback from recorded outcomes without waiting for new events to resolve.

## 🧩 How it works
- Contains **1,568 Polymarket events**, split by time into training and evaluation periods.
- Includes **18.8 M dated news articles** that agents can use as evidence.
- Agents make forecasts, then step forward in time as new evidence becomes available, allowing forecasts to be updated.

| Component | Count |
|---|---|
| Polymarket events | 1,568 |
| Dated news articles | 18.8 M |

## 📊 Evaluation
- Evaluated 12 models; research tools lowered the Brier score for all 12.
- Forecasts improve as events unfold, with the largest gains at steps where more newly dated evidence is recorded.
- Every model still trails historical market forecasts in both Brier score and accuracy.
- A belief notebook carried between dates lowers research cost but does not consistently improve forecast quality.

## ⚙️ Key details
- Beyond evaluation, Forecast-Dojo provides interaction trajectories and outcome feedback for agent learning.
- Supervised fine‑tuning is demonstrated as a proof of concept for improving forecasting agents.


#Forecasting #LLM #Benchmark #AIResearch

---

*Source: [Forecast-Dojo: Replayable Environments for Benchmarking and Training LLM Forecasting Agents](https://arxiv.org/abs/2609.28876v1)*
