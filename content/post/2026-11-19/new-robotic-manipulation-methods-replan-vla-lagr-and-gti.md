---
title: "New Robotic Manipulation Methods: RePlan-VLA, LAGR, and GTI"
slug: "new-robotic-manipulation-methods-replan-vla-lagr-and-gti"
description: "Three new approaches address distinct challenges in robotic manipulation: managing long-horizon task execution, selecting task-oriented grasps, and maintaining semantic intent over multiple stages...."
date: 2026-11-19T18:06:46+05:30
tags: [Robotics, VLA, Manipulation, Grasping, AI]
categories: ["AI", "Robotics", "Machine Learning", "Computer Vision", "Embodied AI"]
author: "Shoubhik Banerjee"
draft: false
---

# New Robotic Manipulation Methods: RePlan-VLA, LAGR, and GTI

Three new approaches address distinct challenges in robotic manipulation: managing long-horizon task execution, selecting task-oriented grasps, and maintaining semantic intent over multiple stages. These methods aim to improve reliability and success rates in complex physical environments by refining how Vision-Language-Action (VLA) models and grasping detectors process state and context.

## 📋 RePlan-VLA: Progress-Aware Replanning

A new framework called **RePlan-VLA** addresses performance degradation in VLA models on long-horizon tasks involving multiple interdependent manipulations. 

- **Core Logic:** It leverages the VLA's existing short-horizon manipulation capabilities within an execution-aware framework, rather than burdening the policy with long-horizon reasoning, memory, or error recovery.
- **Mechanism:** The framework explicitly monitors robot motion for progress evaluation and adaptively revises the future plan based on observed outcomes.
- **Compatibility:** It is VLA-agnostic and preserves the underlying policy entirely, requiring no additional fine-tuning.
- **Performance:** 
  - Achieves a **21.9%** improvement in success rate over the next strongest baseline on the RoboCasa365 benchmark.
  - Achieves a **10.4%** improvement on the CALVIN benchmark.
  - Validated for real-world deployment on a Franka Research 3 robot.

## 🤏 LAGR: Task-Oriented Grasp Detection

The **LAGR** method and its accompanying dataset address the need for grasps that are both physically feasible and suitable for specific downstream tasks (e.g., holding a hammer by the handle for use vs. the head for handover).

- **Dataset:** A newly constructed dataset contains **2.68 million** scored 5-DoF grasp annotations across **100,911** image-task pairs from **17** object categories.
- **Architecture:** 
  1. Generates task-independent grasp proposals with a physical feasibility score.
  2. Uses a language-conditioned re-ranker to score these proposals jointly.
- **Results:** 
  - Outperforms the next best method by **9.3 percentage points**.
  - Validated on real objects using a Franka Research 3 robot.

## 🎯 GTI: Grounding Task Intent

**GTI (Grounding Task Intent)** ensures that global task intent remains grounded in the currently executable context during long-horizon manipulation.

- **How it Works:** Uses current observation and execution history to localize the active subtask and its execution phase.
- **Visual Targets:** For each local subtask, it generates two phase-dependent visual targets:
  - An interaction/contact state.
  - A local completion state.
  - These targets, alongside the local language instruction, jointly condition the VLA to specify both current actions and target states.
- **Recovery:** Includes anomaly monitoring and local recovery mechanisms (rollback, re-observation, phase re-evaluation) to re-establish intent consistency after persistent deviation.
- **Performance Gains:** 
  - **RoboCasa365:** GR00T success on seen composite tasks increases from **14.6%** to **31.8%** (Identity Distribution) and from **12.1%** to **20.4%** (Out-of-Distribution) compared to matched Global-FT baselines.
  - **VLA-Arena:** GTI + $\pi_{0.5}$ reaches **47.6%** overall success versus **45.2%** for an adapted ForeAct baseline, with significant gains on harder L1/L2 tasks.
  - **Real-World:** Mean full-task success on PiPER tasks increases from **21.7%** to **59.2%**.

## ⚙️ Submission Details

All three papers were submitted to arXiv on **November 18, 2026**.

| Paper | Submission Time (UTC) | File Size |
| :--- | :--- | :--- |
| RePlan-VLA | 04:49:41 | 6.4 MB |
| LAGR | 05:04:12 | 9.7 MB |

#Robotics #VLA #Manipulation #Grasping #AI

---

*Source: [DOCK: Dual-Stream-Inspired Self-Supervised Object-Centric Representations Grounded in Robot Kinematics](https://arxiv.org/abs/2611.23578v1)*
*Source: [BiCAT: Bimanual Coordination Action Tokenization](https://arxiv.org/abs/2611.23499v1)*
*Source: [RageVLA: Augmentation-Trained Perception and Action for State-of-the-Art Robustness on LIBERO](https://arxiv.org/abs/2611.23517v1)*
*Source: [LoRN: Low-Rank Noise Steering for Generative Robot Policies](https://arxiv.org/abs/2611.23628v1)*
*Source: [ExecGap: Exploiting Command-Execution Gap for Patch Attacks on Vision-Language-Action Models](https://arxiv.org/abs/2611.23714v1)*
*Source: [Improving While Deployed: Learning Proactive End-to-End Driving from Imperfect Human Takeover Data](https://arxiv.org/abs/2611.23719v1)*
*Source: [RecallFlow: Episodic Memory as the Source Distribution of Generative Robot Policies](https://arxiv.org/abs/2611.23731v1)*
*Source: [ZERITH V2.5: From Predictive Power to Policy Learnability](https://arxiv.org/abs/2611.23746v1)*
*Source: [CoT-WAM: Collaborative Training of Vision-Language Models and World-Action Models via Plan Latents](https://arxiv.org/abs/2611.23803v1)*
*Source: [RePlan-VLA: Progress-Aware Replanning for Long-Horizon Vision-Language-Action Models](https://arxiv.org/abs/2611.23843v1)*
*Source: [LAGR: Language-Aware Grasp Re-Ranking for Task Oriented Grasping](https://arxiv.org/abs/2611.23858v1)*
*Source: [GTI: Grounding Task Intent Throughout Long-Horizon VLA Manipulation](https://arxiv.org/abs/2611.23926v1)*
*Source: [A Hierarchical Onboard Vision-Language-Navigation Framework for Aerial Robots in Complex Environments](https://arxiv.org/abs/2611.23930v1)*
