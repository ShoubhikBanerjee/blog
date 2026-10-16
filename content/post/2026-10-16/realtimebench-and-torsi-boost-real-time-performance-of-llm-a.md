---
title: "RealtimeBench and TORSI Boost Real‑Time Performance of LLM Agents"
slug: "realtimebench-and-torsi-boost-realtime-performance-of-llm-agents"
description: "Large language model (LLM) agents can solve complex interactive tasks, yet reasoning and tool calls take time. In continuously changing environments, an otherwise correct action may arrive too late."
date: 2026-10-16T12:05:34+05:30
tags: [RealtimeBench, LLMAgents, SelfImprovement, AIResearch]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# RealtimeBench and TORSI Boost Real‑Time Performance of LLM Agents

Large language model (LLM) agents can solve complex interactive tasks, yet reasoning and tool calls take time. In continuously changing environments, an otherwise correct action may arrive too late.

## 🔍 Overview
- The need: evaluate agents while the world keeps moving, not just when it is paused.
- Goal: enable powerful LLM agents to remain effective in a continuously changing world by organizing deliberation, learning, and action across timescales.

## 🎮 RealtimeBench
- Introduced a benchmark called **RealtimeBench**.
- Contains **180 tasks** across **six game types**.
- Evaluation runs **while games continue** during inference, reflecting real‑time constraints.

## ⚙️ Two‑Timescale Offline Recursive Self‑Improvement (TORSI)
- **Slow teacher** studies failures and tests corrections in **paused games** between attempts.
- Teacher writes **reusable instructions** for a **fast student**.
- The student **acts without teacher calls** during gameplay.
- **Validation scores** determine which updates are adopted.

## 📈 Results
- Paired evaluations show that **GPT‑6.1‑sol** outperforms the faster **Jev** when games are paused, but falls behind when games keep running.
- Two rounds of TORSI raise **Jev**'s average test score from **13.51** to **24.19** on a 0‑100 progress scale, improving **all six game types**.
- The generated instructions also improve **average scores for three other models** without any retuning.
- These findings illustrate a path toward **real‑time intelligence** for LLM agents.

## 💡 Why it matters
- Real‑time constraints are common in interactive applications (games, robotics, live assistance).
- Organizing learning across **slow offline deliberation** and **fast online execution** allows agents to act promptly while still benefiting from deeper analysis.
- The approach demonstrates that **knowledge can be distilled into reusable instructions**, extending benefits to stronger models beyond the one directly trained.


#RealtimeBench #LLMAgents #SelfImprovement #AIResearch

---

*Source: [The World Won't Wait: Evaluating and Teaching Agents Under a Live Clock](https://arxiv.org/abs/2610.20665v1)*
*Source: [EvolvingBrain: An Adaptive Skill System for Multi-modal Agents Self-Evolution in Open Worlds](https://arxiv.org/abs/2610.20786v1)*
*Source: [A Self-Improving Agent that Grows its Own DSL: Oracle-Free Operator Induction for Exact Question Answering](https://arxiv.org/abs/2610.20809v1)*
*Source: [SkillNEO: Non-Elitist Evolutionary Optimization of Agent Skills](https://arxiv.org/abs/2610.20926v1)*
*Source: [Recursive Reward Improvement via Adversarial Meta-Prompt Evolution](https://arxiv.org/abs/2610.21040v1)*
