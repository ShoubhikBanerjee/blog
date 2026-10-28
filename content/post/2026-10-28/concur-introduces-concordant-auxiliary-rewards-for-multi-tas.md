---
title: "CONCUR Introduces Concordant Auxiliary Rewards for Multi‑Task RL"
slug: "concur-introduces-concordant-auxiliary-rewards-for-multitask-rl"
description: "When a Large Language Model (LLM) is trained with Reinforcement Learning (RL) on multiple tasks, the primary reward can gate auxiliary rewards such as a length reward. Existing group‑relative..."
date: 2026-10-28T22:03:50+05:30
tags: [ReinforcementLearning, MultiTaskLearning, LanguageModels, AIResearch]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Reinforcement Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# CONCUR Introduces Concordant Auxiliary Rewards for Multi‑Task RL

When a Large Language Model (LLM) is trained with Reinforcement Learning (RL) on multiple tasks, the primary reward can gate auxiliary rewards such as a length reward. Existing group‑relative advantage estimators may treat a gated auxiliary like any other component, which can reverse the primary’s ordering and allow auxiliaries to dominate at the primary’s ceiling. Keeping gated auxiliaries harms some tasks, while dropping them harms others.

## 🔍 Overview
- Paper title: **CONCUR: Concordant Auxiliary Rewards for Multi‑Task, Multi‑Reward Reinforcement Learning**
- Submitted to *Computer Science > Computation and Language* on 27 Oct 2026.
- Goal: Align auxiliary rewards with the primary reward so that they never contradict the primary ordering.

## 🧩 How it works
- CONCUR replaces each gated auxiliary’s standardized score with the nearest score that satisfies two conditions:
  1. Responses with higher primary rewards cannot receive lower scores.
  2. Responses that have reached the primary’s ceiling receive equal scores.
- Two variants are defined:
  * **CONCUR‑T** – enforces both conditions continuously throughout training.
  * **CONCUR‑A** – relaxes the second condition for an auxiliary when it agrees with the primary’s order more often than it reverses it among passing responses.

## ⚙️ Variants & Features
- **CONCUR‑T**: strict monotonicity and ceiling equality.
- **CONCUR‑A**: conditional lifting of the ceiling‑equality rule based on agreement frequency.
- Applies to any gated auxiliary reward in multi‑task RL settings.

## 📈 Results
- Evaluated on three models from two families across four task types:
  * Mathematics
  * Code generation
  * Instruction following
  * Writing
- Both CONCUR‑T and CONCUR‑A achieve higher average scores than all baselines and higher than the configuration where all gated auxiliaries are dropped.

## 💡 Why it matters
- Provides a systematic way to keep auxiliary rewards concordant with the primary objective, improving performance across diverse downstream tasks without sacrificing any specific task.


#ReinforcementLearning #MultiTaskLearning #LanguageModels #AIResearch

---

*Source: [CONCUR: Concordant Auxiliary Rewards for Multi-Task, Multi-Reward Reinforcement Learning](https://arxiv.org/abs/2610.36437v1)*
