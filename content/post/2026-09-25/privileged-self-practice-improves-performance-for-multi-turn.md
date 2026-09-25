---
title: "Privileged Self-Practice Improves Performance for Multi-Turn LLM Agents"
slug: "privileged-self-practice-improves-performance-for-multi-turn-llm-agents"
description: "Researchers have introduced Privileged Self-Practice (PSP), a new method for post-training multi-turn LLM agents that addresses the shortcomings of on-policy self-distillation (OPSD)."
date: 2026-09-25T22:04:20+05:30
tags: [LLM, AIagents, PostTraining, MachineLearning]
categories: ["AI", "Machine Learning", "AI Agents", "Large Language Models"]
author: "Shoubhik Banerjee"
draft: false
---

# Privileged Self-Practice Improves Performance for Multi-Turn LLM Agents

Researchers have introduced Privileged Self-Practice (PSP), a new method for post-training multi-turn LLM agents that addresses the shortcomings of on-policy self-distillation (OPSD).

## 🔍 Overview
On-policy self-distillation (OPSD) is a popular recipe for post-training agents that supervises a student model at the token level using a stronger teacher view conditioned on privileged information (PI). However, in multi-turn agents, this paradigm can teach the student to act with confidence without the underlying information, leading to performance that falls short of plain RL and, in some cases, below the untrained base model.

## 🧩 How it works
Privileged Self-Practice (PSP) modifies the use of privileged information by moving it from the loss to the sampler. The process operates as follows:

* When student rollouts on a task mostly fail, an analyzer model writes a short per-task instruction.
* This instruction is injected as privileged information in the context.
* The task is sampled again with the instruction.
* The model is trained on the result using an unchanged GRPO objective.
* The privileged information remains in the prompt and never enters the loss.

## 💡 Why it matters
PSP consistently outperforms plain GRPO across different student models. The following table details the improvements in task completion:

| Benchmark | Result |
| :--- | :--- |
| AppWorld | Task-goal completion improved by up to 65% |
| SWE-bench Verified | Resolved rate improved by up to 61% |

#LLM #AIagents #PostTraining #MachineLearning

---

*Source: [From Self-Distillation to Self-Practice: Privileged Information for Multi-Turn Agents](https://arxiv.org/abs/2609.29051v1)*
*Source: [Post-Training Leaves Behavioral Shadows on Unrelated Decisions](https://arxiv.org/abs/2609.29233v1)*
