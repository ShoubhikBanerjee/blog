---
title: "Introducing T1: A 122B Mixture-of-Experts Model for Long-Horizon Terminal Tasks"
slug: "introducing-t1-a-122b-mixture-of-experts-model-for-long-horizon-terminal-tasks"
description: "As AI agent usage shifts toward long-horizon tasks such as coding and scientific discovery, terminal tasks have become especially important. To address this, researchers have introduced T1, a..."
date: 2026-09-11T18:06:00+05:30
tags: [MachineLearning, AIAgents, ReinforcementLearning, MoE]
categories: ["AI", "Machine Learning", "AI Agents", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Introducing T1: A 122B Mixture-of-Experts Model for Long-Horizon Terminal Tasks

As AI agent usage shifts toward long-horizon tasks such as coding and scientific discovery, terminal tasks have become especially important. To address this, researchers have introduced T1, a Mixture-of-Experts (MoE) model of 122B total trained with reinforcement learning. Built to operate a real shell in a cloud sandbox for up to 300+ tool-call turns per task, the model is rewarded by executing each task's own verifier, marking a major update in long-horizon agent capabilities.

## 🔍 Overview
The T1 model is designed to tackle complex terminal tasks. Unlike standard agents, T1 runs directly inside a cloud sandbox shell and uses a unique reinforcement learning pipeline to maximize the number of passing verifiers per task.

## 🧩 How it works
The training recipe for T1 relies on three key pillars:
* **Warm-Started Actor-Critic Training:** The pipeline is aggressively warm-started to stabilize actor-critic training, using a dense process reward that scores trajectories by the absolute number of passing verifiers.
* **Stable Optimization via TITO and R3:**
    * *TITO Construction:* The model is trained on the exact sampled token identifiers with drift repair at turn boundaries.
    * *Rollout Routing Replay (R3):* The pipeline records the sampler's per-token expert choices at every MoE layer and replays them during training.
    * *Combined Impact:* Together, TITO and R3 cut the training-to-inference log-probability difference from 0.021 to 0.013, yielding exactly aligned zero token drift in the loss region.
* **Out-of-Distribution Training Corpus:** The use of isolated seeds and synthesized tasks disjoint from Terminal-Bench 2.1 ensures that performance gains reflect genuine capability transfer rather than benchmark overfitting.

## 📊 Benchmark Results
The post-training pipeline significantly improves terminal task execution, outperforming established baselines.

| Benchmark | Model | Score / Resolution Rate |
| :--- | :--- | :--- |
| Terminal-Bench 2.1 | Initial Base Model | 43.8% |
| Terminal-Bench 2.1 | T1 | 64.0% |
| Long-Horizon Terminal Bench | T1 | 27.9% |
| Long-Horizon Terminal Bench | GPT-5.4 | Surpassed by T1 |
| Long-Horizon Terminal Bench | GLM-5.1 | Surpassed by T1 |

#MachineLearning #AIAgents #ReinforcementLearning #MoE

---

*Source: [From Connectivity to Rewards: Dense Reward Learning with Directed State Graphs](https://arxiv.org/abs/2609.10781v1)*
*Source: [Topological Necessities: Mechanism-Invariant Strategic Subgoals for Cross-Embodiment Goal-Conditioned Control](https://arxiv.org/abs/2609.11014v1)*
*Source: [T1: Terminal Agent Reinforcement Learning for Long-Horizon Tasks](https://arxiv.org/abs/2609.11042v1)*
