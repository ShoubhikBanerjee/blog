---
title: "XMimic Trains Humanoid Motion Tracking 3.7x Faster Than BlinkMimic"
slug: "xmimic-trains-humanoid-motion-tracking-3-7x-faster-than-blinkmimic"
description: "XMimic is a new AI development that trains whole-body motion tracking for the Unitree G1 robot 3.7 times faster than the previous BlinkMimic method when using four H100 GPUs. The improvement comes..."
date: 2026-11-18T22:09:17+05:30
tags: [AI, Robotics, JAX, MotionTracking, Humanoid]
categories: ["AI", "Machine Learning", "Robotics", "Computer Vision", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/34777138?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# XMimic Trains Humanoid Motion Tracking 3.7x Faster Than BlinkMimic

## 🚀 Overview

XMimic is a new AI development that trains whole-body motion tracking for the Unitree G1 robot 3.7 times faster than the previous BlinkMimic method when using four H100 GPUs. The improvement comes from rebuilding BlinkMimic's world-model trainer in JAX, enabling faster training while maintaining the same quality.

## 🧩 How it works

XMimic implements the same algorithm as BlinkMimic but runs entirely in JAX. This includes the simulator (MuJoCo Warp through MJX), the replay buffer, the world model, the policy and the critic. The entire training iterations compile into single XLA programs, so the GPU never waits for Python. The system can distribute iterations across 2 to 4 GPUs working simultaneously.

## ⚙️ Key details

- **Speed**: Reaches BlinkMimic's target in 0.86 minutes on four H100s (vs. 3.19 minutes on one); on a single H100, XMimic is 1.3 times faster
- **Quality**: Both methods achieve the same normalized evaluation return (0.86–0.87) with no clip failures after 6 minutes of training
- **Target**: Normalized evaluation return ≥ 0.82 with none of the 40 LAFAN1 clips failing, held for three consecutive checkpoints
- **GPU usage**: Uses slightly more total GPU time (3.4 vs. 3.2 GPU-minutes) but the speedup buys wall-clock time
- **Hardware**: One H100 NVL per GPU, GPUs connected by NVLink in a node
- **Training**: All methods ran on the same cluster; every 100th checkpoint is evaluated on all 40 clips with 4 replicas each
- **Hyperparameters**: Uses BlinkMimic's hyperparameters (`PRESET[main]`, commit `d264658`)

The development is detailed in the paper *XMimic and XSoma: Learning Humanoid Motion Tracking and Locomotion in Under a Minute* by Nico Bohlinger and Jan Peters (2026).

## 📄 Availability

XMimic replaces the first version which covered XMimic alone. It is accompanied by XSoma, which applies the same recipe for locomotion on rough terrain. Please cite the paper if you use XMimic:

> *XMimic and XSoma: Learning Humanoid Motion Tracking and Locomotion in Under a Minute* (Nico Bohlinger, Jan Peters, 2026)

#AI #Robotics #JAX #MotionTracking #Humanoid

---

*Source: [nico-bohlinger/xmimic](https://github.com/nico-bohlinger/xmimic)*
