---
title: "RoboARC benchmarks robot manipulation under precise spatial constraints"
slug: "roboarc-benchmarks-robot-manipulation-under-precise-spatial-constraints"
description: "RoboARC is a new benchmark designed to test whether robot agents can reason out the correct motions for hard manipulation tasks that hinge on exact spatial constraints. The collection features 90..."
date: 2026-11-26T18:08:23+05:30
tags: [robotics, manipulation, benchmark, spatial, AI]
categories: ["AI", "Robotics", "Artificial Intelligence", "Machine Learning", "Computer Vision"]
author: "Shoubhik Banerjee"
draft: false
---

# RoboARC benchmarks robot manipulation under precise spatial constraints

RoboARC is a new benchmark designed to test whether robot agents can reason out the correct motions for hard manipulation tasks that hinge on exact spatial constraints. The collection features 90 tasks across six constraint types, involving both rigid and soft materials, evaluated in MuJoCo simulation on three different robot platforms.

## 🧩 How it works

Each task is structured as a frozen scene with a physics-based grader and a verified reference solution that replays bit-identically. Tasks are provided in two evaluation regimes:

- Privileged regime: Full simulator state access and resets allowed
- Standard regime: Real-sensor inputs (camera images and proprioception) with a single attempt and no resets

Seven coding agents and four vision-language-action (VLA) policies—none trained on these tasks—were evaluated against the benchmark.

## ⚙️ Key details

The strongest performer was GPT-6 Astra in Codex, which achieved:

- 86% success rate in the Privileged regime
- 43% success rate in the Standard regime

The four VLA policies, evaluated zero-shot, solved none of their 18 one-arm puzzles.

Analysis of 15 tasks that GPT-6 Astra solved in Privileged but failed in Standard revealed that:

- Object poses alone added 4 points (from 24% to 28%)
- Part geometry alone added 13 points (from 24% to 37%)
- Both object poses and part geometry together added 36 points (from 24% to 60%)

Only 7% of the coding agents' failed runs passed more than half of a task, and 53% of failed runs in the Standard regime were stuck on a single step. The results show that frontier coding agents can reason out correct motions once they know object locations and shapes, but performance drops significantly when relying solely on sensor inputs in a single attempt.

## 🚀 Availability

The RoboARC benchmark is available at the project website.

## 💡 Why it matters

The findings highlight that spatial constraint understanding remains a critical gap in robotic manipulation. While agents can reason about motion when given complete scene information, real-world sensor limitations significantly reduce performance. The benchmark provides a standardized evaluation framework for future research in constraint-based manipulation tasks.

#robotics #manipulation #benchmark #spatial #AI

---

*Source: [RoboARC: Physical Puzzles for Robotic Manipulation under Spatial Constraints](https://arxiv.org/abs/2611.33390v1)*
*Source: [Skeptic: Grounding Failure Diagnosis for Robot Skill Discovery](https://arxiv.org/abs/2611.33560v1)*
*Source: [Lab2Sim: Agentic Generation of Interactive Laboratory Equipment from Operation Videos](https://arxiv.org/abs/2611.33705v1)*
*Source: [A general-purpose safe manipulator planning framework for diverse environments without retraining](https://arxiv.org/abs/2611.33721v1)*
*Source: [RoboJackVR: Turning Robot Tasks into VR Games for Scalable Demonstration Collection](https://arxiv.org/abs/2611.33731v1)*
*Source: [PROVE: Predict-to-Specify and Observe-to-Verify for Human-Aligned Evaluation of Mobile Manipulation](https://arxiv.org/abs/2611.33733v1)*
*Source: [CoTAMP: Cooperative Task and Motion Planning for Quadruped Robots with Large Language Models](https://arxiv.org/abs/2611.33911v1)*
*Source: [SEEK: Self-Evolution through Execution Knowledge for Agentic Robot Manipulation](https://arxiv.org/abs/2611.33915v1)*
