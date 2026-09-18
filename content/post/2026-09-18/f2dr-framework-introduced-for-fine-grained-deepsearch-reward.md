---
title: "F2DR Framework Introduced for Fine-Grained DeepSearch Reward Evaluation"
slug: "f2dr-framework-introduced-for-fine-grained-deepsearch-reward-evaluation"
description: "Researchers have proposed F2DR, a fine-grained full-pipeline reward framework designed to evaluate DeepSearch workflows used by Large Language Models (LLMs) to resolve complex user queries."
date: 2026-09-18T22:02:10+05:30
tags: [LLM, DeepSearch, RewardModels, AIEvaluation]
categories: ["AI", "Machine Learning", "Large Language Models", "AI Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# F2DR Framework Introduced for Fine-Grained DeepSearch Reward Evaluation

Researchers have proposed F2DR, a fine-grained full-pipeline reward framework designed to evaluate DeepSearch workflows used by Large Language Models (LLMs) to resolve complex user queries.

## 🔍 Overview
DeepSearch typically utilizes an iterative closed-loop workflow consisting of:
* Planning and reflection
* Information retrieval
* Answer generation

Existing reward models (RMs) and evaluation benchmarks often fail to capture the complexity of these full-pipeline workflows because they are primarily designed for static single-turn tasks.

## 🧩 How it works
F2DR addresses previous limitations by assessing DeepSearch workflows across three specific dimensions:
* Content
* Trajectory
* Answer

## ⚙️ Key details
Along with the framework, researchers constructed DeepSearch RM-Bench, a dedicated benchmark for evaluating RMs in DeepSearch scenarios. Experiments indicate that:
* F2DR achieves significantly higher evaluation consistency than self-evaluation-based baselines.
* DeepSearch RM-Bench shows strong discriminative capability across existing open-source RMs.

## 🚀 Availability
The complete DeepSearch RM-Bench dataset will be released publicly soon.

#LLM #DeepSearch #RewardModels #AIEvaluation

---

*Source: [F$^{2}$DR: A Fine-Grained Full-Pipeline Reward Framework for DeepSearch Workflows](https://arxiv.org/abs/2609.19827v1)*
