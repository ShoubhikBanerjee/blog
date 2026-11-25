---
title: "POISE: Curvature-Aware Critic Regularization for Smooth Actor-Critic Control"
slug: "poise-curvature-aware-critic-regularization-for-smooth-actor-critic-control"
description: "PAV inger-critic methods achieve high returns in robotic control, yet trained actors exhibit high-frequency action oscillations. Most smoothness methods constrain the actor, whereas PAVE regularizes..."
date: 2026-11-25T12:10:39+05:30
tags: [AI, ActorCritic, Robotics, CurvatureRegularization]
categories: ["AI", "Machine Learning", "Robotics", "Control Systems", "Reinforcement Learning"]
author: "Shoubhik Banerjee"
draft: false
---

# POISE: Curvature-Aware Critic Regularization for Smooth Actor-Critic Control

## 🎯 Overview
PAV inger-critic methods achieve high returns in robotic control, yet trained actors exhibit high-frequency action oscillations. Most smoothness methods constrain the actor, whereas PAVE regularizes the critic by separately penalizing action-gradient variation and encouraging negative action curvature.

## 🧩 How it works
The same gradient change, however, moves the critic's preferred action farther where the critic is flat, and separate penalties do not measure this motion. We characterize this motion through the greedy shift, which approximates greedy-action displacement across state transitions to first order under local concavity. Since displacement alone does not reflect its critic-value consequences, the analysis further shows that the shift's curvature-weighted energy approximates the value lost by retaining the previous greedy action to second order. Based on this relationship, POISE regularizes the curvature-weighted energy along temporal and spatial state displacements. It employs a saddle-free curvature metric and reward-scale-consistent scaling while leaving the actor unchanged.

## ⚙️ Key details
- On six continuous control tasks with TD3, POISE reduces the smoothness score on every task by 5.9× on average (4.5× geometric mean), compared with 2.2× (1.9×) for the strongest baseline, and achieves the lowest score on five tasks.
- Paired return intervals include zero on four tasks, with a 14% increase on Ant and an 11% decrease on Hopper.

[Submitted on 24 Nov 2026]
Title:POISE: Curvature-Aware Critic Regularization for Smooth Actor-Critic Control

#AI #ActorCritic #Robotics #CurvatureRegularization

---

*Source: [POISE: Curvature-Aware Critic Regularization for Smooth Actor-Critic Control](https://arxiv.org/abs/2611.31835v1)*
