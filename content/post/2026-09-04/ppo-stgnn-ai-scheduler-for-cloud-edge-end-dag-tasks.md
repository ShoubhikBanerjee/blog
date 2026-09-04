---
title: "PPO‑STGNN: AI Scheduler for Cloud‑Edge‑End DAG Tasks"
description: "A paper submitted on 3 Sep 2026 introduces **PPO‑STGNN**, a DAG task‑scheduling algorithm that combines proximal policy optimization (PPO) with spatio‑temporal graph neural networks (STGNNs) for..."
date: 2026-09-04T12:10:15+05:30
tags: [DAGScheduling, CloudEdgeComputing, GraphNeuralNetwork, ReinforcementLearning, AI]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# PPO‑STGNN: AI Scheduler for Cloud‑Edge‑End DAG Tasks

A paper submitted on 3 Sep 2026 introduces **PPO‑STGNN**, a DAG task‑scheduling algorithm that combines proximal policy optimization (PPO) with spatio‑temporal graph neural networks (STGNNs) for heterogeneous cloud‑edge‑end environments.

## 🔍 Overview
- The rapid growth of the Internet of Things has made computation‑intensive directed acyclic graph (DAG) tasks common across cloud, edge, and end devices.
- Heterogeneous computing capacity, network bandwidth, and energy consumption make efficient scheduling an NP‑hard problem.
- Traditional heuristics and conventional reinforcement‑learning methods often fail to capture the spatio‑temporal dynamics of system resources.

## 🧩 How it works
- An STGNN extracts features from both the DAG task topology and the physical cloud‑edge‑end resource graph.
- PPO optimizes the scheduling policy to minimize makespan and schedule length ratio (SLR) while improving CPU and memory load balancing.
- A multi‑teacher behavior‑cloning mechanism pre‑trains the model to accelerate convergence.

| Component | Role |
|----------|------|
| Proximal Policy Optimization (PPO) | Optimizes the scheduling policy for makespan, SLR, and load balancing |
| Spatio‑Temporal Graph Neural Network (STGNN) | Extracts features from task and resource graphs |
| Multi‑teacher behavior cloning | Pre‑training method to speed up learning |

## ⚙️ Key details
- Targets dynamic and heterogeneous cloud‑edge‑end DAG scheduling scenarios.
- Aims to minimize overall completion time (makespan) and improve resource utilization.
- Designed to handle complex task dependencies in a collaborative environment.

## 📈 Experimental results
- PPO‑STGNN significantly improves load balancing while maintaining a low completion time.
- The results indicate suitability for real‑world, dynamic heterogeneous environments.

## 💡 Why it matters
- Addresses the growing need for efficient DAG scheduling in IoT‑driven cloud‑edge‑end systems.
- Demonstrates how combining reinforcement learning with graph‑based representations can handle spatio‑temporal resource dynamics.
- Provides a foundation for future research on AI‑driven resource orchestration.


#DAGScheduling #CloudEdgeComputing #GraphNeuralNetwork #ReinforcementLearning #AI

---

*Source: [PPO-STGNN: A Proximal Policy Optimization Approach with Spatio-Temporal Graph Neural Networks for DAG Task Scheduling in Cloud-Edge-End Computing](https://arxiv.org/abs/2609.03503v1)*
