---
title: "CHIME Improves Long-Horizon Agent Planning Using Credit-Aware Memory Evolution"
description: "Researchers have introduced Credit-Aware Hierarchical Memory Evolution (CHIME), a framework designed to enhance agentic planning capabilities without requiring parameter updates."
date: 2026-09-03T18:04:33+05:30
tags: [AI, MachineLearning, LLM, AgenticAI]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# CHIME Improves Long-Horizon Agent Planning Using Credit-Aware Memory Evolution

Researchers have introduced Credit-Aware Hierarchical Memory Evolution (CHIME), a framework designed to enhance agentic planning capabilities without requiring parameter updates.

## 🔍 Overview
Planning allows agents to decompose complex tasks into manageable steps, but existing methods often face high inference costs or the credit assignment problem, where noisy outcomes conflate plan quality with environmental factors.

## 🧩 How it works
CHIME utilizes an attribute-before-memorize principle to ensure that only relevant experience is stored in its external memory bank. The system operates as follows:

* Maintains separate banks: A dedicated planning bank and an execution bank.
* Attribution process: Each task outcome is attributed to the plan, the execution, both, or neither.
* Selective updating: Only the specific bank corresponding to the identified source of success or failure is updated.

## ⚙️ Key details
Experimental results on four long-horizon agent benchmarks demonstrate that CHIME outperforms existing state-of-the-art training-based and self-evolving memory baselines.

| Capability | Feature Outcome |
| :--- | :--- |
| Memory efficiency | Accumulates effective memory with far fewer items |
| Performance | Learned memory values faithfully reflect downstream utility |
| Memory priority | High-quality planning memories are more valuable than execution memories |
| Transferability | Memory effectively transfers across backbone models |

## 🚀 Availability
Code for CHIME will be released via a future link.

#AI #MachineLearning #LLM #AgenticAI

---

*Source: [CHIME: Credit-Aware Hierarchical Memory Evolution for Long-Horizon Agentic Planning](https://arxiv.org/abs/2609.02074v1)*
*Source: [MASkills: Continual Skills Optimization for Multi-Agent LLM Systems](https://arxiv.org/abs/2609.02094v1)*
*Source: [WMLLM: Self-Evolving Optimization Agents via Predict-Then-Act World Modeling](https://arxiv.org/abs/2609.01608v1)*
