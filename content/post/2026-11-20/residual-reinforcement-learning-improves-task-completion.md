---
title: "Residual reinforcement learning improves task completion"
slug: "residual-reinforcement-learning-improves-task-completion"
description: "Residual reinforcement learning corrects an imitation-trained base policy using a limited budget of environment interaction. This approach is particularly effective in tasks with multiple phases,..."
date: 2026-11-20T12:08:10+05:30
tags: [ResidualRL, ReinforcementLearning, Robotics, AI]
categories: ["AI", "Machine Learning", "Robotics", "AI Agents", "Automation"]
author: "Shoubhik Banerjee"
draft: false
---

# Residual reinforcement learning improves task completion

Residual reinforcement learning corrects an imitation-trained base policy using a limited budget of environment interaction. This approach is particularly effective in tasks with multiple phases, where the budget must be divided among them.

## 🔍 Overview
- Residual reinforcement learning improves task completion by correcting an imitation-trained base policy.
- The method is applied to tasks with several phases, requiring the budget of environment interaction to be divided among these phases.

## 🧩 How it works
- The completion gain is formalized as the change in full-task completion probability when a state-feedback controller replaces selected components of the base policy's action during a single phase.
- The completion gain is decomposed into the probability of reaching the phase and the conditional improvement in completion from the start of the phase.
- Positive estimates of the completion gain determine which action components the residual policy corrects and how training episodes are distributed across phases.

## ⚙️ Key details
- In stochastic point-mass docking experiments, most failures occurred in the final docking phase, but the largest completion gain occurred in the preceding channel phase.
- Gain-based allocation improved completion over allocation proportional to failure counts and, in a variant with a longer approach, over uniform allocation at half of the budget.
- In simulated bimanual robotic assembly, the completion-gain estimates were positive only for insertion and release, although few failures occurred during release.
- In a second assembly configuration, a residual policy trained in the release phase improved completion from held-out states at the start of release by 16.9%.

#ResidualRL #ReinforcementLearning #Robotics #AI

---

*Source: [Improving Imitation Policies for Multi-Phase Tasks through Residual Learning Allocation](https://arxiv.org/abs/2611.25320v1)*
