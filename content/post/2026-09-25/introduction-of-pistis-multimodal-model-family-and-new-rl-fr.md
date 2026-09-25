---
title: "Introduction of Pistis Multimodal Model Family and New RL Frameworks"
slug: "introduction-of-pistis-multimodal-model-family-and-new-rl-frameworks"
description: "Recent developments in multimodal large language models have led to the introduction of the Pistis model family and several new reinforcement learning (RL) optimization frameworks designed to improve..."
date: 2026-09-25T12:04:19+05:30
tags: [MLLM, ReinforcementLearning, Pistis, AIagents]
categories: ["AI", "Machine Learning", "Multimodal AI", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# Introduction of Pistis Multimodal Model Family and New RL Frameworks

Recent developments in multimodal large language models have led to the introduction of the Pistis model family and several new reinforcement learning (RL) optimization frameworks designed to improve reasoning, reduce hallucinations, and enhance agentic performance.

## 🔍 Overview
The Pistis model family consists of multimodal large language models built on Qwen3.5 and Qwen3.6. These models are developed using a scalable post-training framework that begins with large-scale multimodal supervised fine-tuning (SFT). 

| Model Variant | Base Architecture | Primary Purpose |
| :--- | :--- | :--- |
| Pistis-9B | Qwen3.5 | General multimodal capabilities |
| Pistis-27B | Qwen3.6 | General multimodal capabilities |
| Pistis-Thinking | Varies | Strengthening deep multimodal reasoning |
| Pistis-Agentic | Varies | Long-horizon planning, iterative reasoning, and tool use |

## 🧩 How it Works
To improve these models, several novel training paradigms and systems have been introduced:

* **Interleaved Distillation and Reinforcement Learning (IDRL):** A paradigm that integrates on-policy distillation and reinforcement learning in a single loop. By alternating between objectives, it aims for more effective knowledge transfer and precise credit assignment for agentic trajectories.
* **Dual-Entropy Enhanced Policy Optimization (DEEPO):** This dual-stage enhancement combines signal variance regularization and gradient preconditioning to reduce hallucinations while preserving accuracy.
* **Pistis-Auto-Harnessing (PAH):** A system-level method that iteratively optimizes the agent's inference harness without updating model parameters or increasing the interaction budget.
* **Graph-based Faithful sTep-level credit-assignment (GRAFT):** A framework that grafts rollout trajectories into a graph to recover node state-values via Bellman iteration, reducing bias in step-level advantage estimation.
* **SLCA-GRPO:** A framework using Segment-Locked Credit Assignment to decouple advantage estimation at the structural segment level, preventing gradient noise from summary generation from leaking into tool-decision tokens.

## ⚙️ Key Details
Researchers have also explored RLVR (Reinforcement Learning with Verifiable Rewards) and other specific algorithmic tasks:

* **Small Model RLVR:** Testing on Qwen3.5-0.8B showed a 3.8-fold gain in average exact match (0.352 vs 0.092) using a reason-over-search recipe with Wikipedia-search tools, though sparse exact-match rewards were found to be ineffective for models of this size.
* **MI-SARSA:** An on-policy temporal-difference algorithm incorporating mutual-information regularization. It produces a reward-complexity tradeoff where stronger penalties lead to simpler policies and faster reaction times.
* **Optimization Landscape:** Study of RLVR on algorithmic tasks suggests the landscape is benign with no local minima for certain models, meaning difficulties stem from diffusive barriers and gradient-estimation error rather than a rugged landscape.

#MLLM #ReinforcementLearning #Pistis #AIagents

---

*Source: [Pistis Technical Report](https://arxiv.org/abs/2609.28554v1)*
*Source: [DEEPO: Dual-Entropy Enhanced Policy Optimization for Hallucination in MLLMs](https://arxiv.org/abs/2609.28570v1)*
*Source: [Reinforcement Learning with Verifiable Rewards for Small Search Agents](https://arxiv.org/abs/2609.28765v1)*
*Source: [Back to the Definition: Estimating Step-Level Advantages via Trajectory Graphs for Agentic Reinforcement Learning](https://arxiv.org/abs/2609.28963v1)*
*Source: [SLCA-GRPO: Resolving Cross-Segment Credit Misattribution in Tool-Calling RL](https://arxiv.org/abs/2609.29050v1)*
*Source: [RLVR landscapes for iterated multiplications can be benign: Insights from spin-glass theory](https://arxiv.org/abs/2609.28625v1)*
*Source: [Policy Complexity, Reaction Time, and Bounded Rationality in Reinforcement Learning](https://arxiv.org/abs/2609.28737v1)*
