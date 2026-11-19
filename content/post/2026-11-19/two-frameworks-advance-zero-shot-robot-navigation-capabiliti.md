---
title: "Two frameworks advance zero-shot robot navigation capabilities"
slug: "two-frameworks-advance-zero-shot-robot-navigation-capabilities"
description: "Recent research introduces two distinct frameworks addressing key challenges in zero-shot robot navigation: RPSI-Nav for recursive policy self-improvement in multi-object search, and ROMUX for..."
date: 2026-11-19T18:06:46+05:30
tags: [robotics, navigation, zeroshot, embodiedai, computervision, selfimprovement]
categories: ["AI", "Robotics", "Machine Learning", "Computer Vision", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# Two frameworks advance zero-shot robot navigation capabilities

Recent research introduces two distinct frameworks addressing key challenges in zero-shot robot navigation: RPSI-Nav for recursive policy self-improvement in multi-object search, and ROMUX for navigation using uncalibrated exocentric cameras.

## 🧩 How RPSI-Nav Works

RPSI-Nav forms a recursive loop where the system revises both its navigation program and the revision mechanism itself:

- Diagnoses search behavior and requests diagnostic views when observations cannot distinguish competing causes
- Generates targeted navigation revisions based on diagnosis
- Links feedback from subsequent goal searches to the rules that produced revisions
- Updates the improver (diagnosis, observation acquisition, revision planning) to govern future improvements
- Conditionally inherits accepted program updates and spatial memory across goals

## 🧩 How ROMUX Works

ROMUX predicts metric robot-centric obstacle maps from exocentric images without camera calibration:

- Trains a cross-view transformer on large-scale simulation data to predict obstacle maps from exocentric images
- Does not condition image tokens on camera information (pose or intrinsics)
- Uses a small PPO-trained policy to navigate on predicted maps toward goal coordinates relative to the robot
- Works with single or multiple cameras with partial views
- Transfers zero-shot to real robots with cameras at varying positions and orientations across room layouts

## ⚙️ Key Details

| Framework | Task | Key Innovation |
|-----------|------|----------------|
| RPSI-Nav | Zero-shot open-vocabulary multi-object navigation | Recursive self-improvement of both policy and improvement mechanism |
| ROMUX | Point-goal navigation with obstacle avoidance | Cross-view transformer predicting metric maps from uncalibrated, unknown exocentric cameras |

## 💡 Why It Matters

- RPSI-Nav addresses the constraint where fixed human-designed revision mechanisms limit continued self-improvement in navigation policies
- ROMUX eliminates time-consuming calibration requiring specialized personnel, which must be repeated when cameras move or new rooms are navigated
- Both systems operate zero-shot in unseen environments without training or fine-tuning
- Benchmark experiments and real-robot evaluations validate both approaches
- ROMUX matches success rates of policies using robot-mounted cameras in simulation with randomized cameras per episode

## 🚀 Availability

- RPSI-Nav: Benchmark experiments and qualitative real-robot evaluations completed
- ROMUX: Benchmarked in simulation with per-episode camera randomization; transferred zero-shot to real robot across various room layouts and camera positions/orientations

#robotics #navigation #zero-shot #embodied-ai #computer-vision #self-improvement

---

*Source: [Improve How You Improve: Recursive Policy Self-Improvement for Zero-Shot Open-Vocabulary Multi-Object Navigation](https://arxiv.org/abs/2611.23774v1)*
*Source: [Navigating Robots from Unknown and Uncalibrated Exocentric Cameras via Map Estimation](https://arxiv.org/abs/2611.23894v1)*
