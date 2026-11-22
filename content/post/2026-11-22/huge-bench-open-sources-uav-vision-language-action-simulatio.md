---
title: "HUGE-Bench Open-Sources UAV Vision-Language-Action Simulation Platform with 2.56M Meters of Trajectories"
slug: "huge-bench-open-sources-uav-vision-language-action-simulation-platform-with-2-56m-meters-of-trajectories"
description: "Researchers have released HUGE-Bench, an open-source UAV simulation platform targeting high-level vision-language-action tasks where agents ground brief, potentially ambiguous commands into safe,..."
date: 2026-11-22T12:09:58+05:30
tags: [UAV, VisionLanguageAction, Simulation, Robotics, OpenSource, 3DGS]
categories: ["AI", "Machine Learning", "Robotics", "Computer Vision", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/83287600?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# HUGE-Bench Open-Sources UAV Vision-Language-Action Simulation Platform with 2.56M Meters of Trajectories

Researchers have released HUGE-Bench, an open-source UAV simulation platform targeting high-level vision-language-action tasks where agents ground brief, potentially ambiguous commands into safe, multi-stage behaviors. The platform combines photorealistic rendering with collision-capable geometry through aligned 3DGS-Mesh representations.

## 🔍 Overview
- Targets high-level UAV vision-language-action tasks
- Agents ground brief, potentially ambiguous commands into safe, multi-stage behaviors
- Built on aligned 3DGS-Mesh representations combining photorealistic rendering with collision-capable geometry
- Enables scalable data generation and collision-aware evaluation
- Designed to be easy to configure, high-fidelity, and collision-aware

## 📊 Key Details
| Attribute | Specification |
|---|---|
| Real-world scenes | 4 |
| High-level tasks | 8 |
| Trajectory distance | 2.56M meters |
| Test episodes (HUGE_Dataset_v0) | 993 (576 seen, 417 unseen) |
| 3DGS-Mesh environments | 4 (plus 3 finely reconstructed subregions for low-altitude forward obstacle avoidance) |

## 🧩 Released Components
- **HUGE_Trajectory**: All trajectory data (train and test) plus one 3DGS environment for pipeline debugging, released in LeRobot format compatible with pi0 training pipeline
- **Checkpoints**: Available at HUGE_PI0 and HUGE_PI05
- **HUGE_Environment**: All 4 3DGS-Mesh environments plus 3 finely reconstructed subregions
- **Trajectory collection scripts**: RGB, depth, subtask, and instruction generation
- **3DGS-Mesh construction pipeline**
- **Multi-stage trajectory annotations** and LeRobot episode mappings (lightweight sidecar release; existing Hugging Face parquet files unchanged)
- **Per-episode unseen labels**: Available in evaluation/test_unseen_sources.jsonl
- **Evaluation guide**: Corrected split counts and Table 2 reference scores

## 🚀 Availability & Usage
- Fine-tune PI0 or PI0.5 using HUGE_Trajectory by following the official OpenPI repository setup
- Dataset follows LeRobot format expected by the pipeline
- Training configuration steps:
  - Copy drone_policy.py to openpi/src/openpi/policies/drone_policy.py
  - Replace openpi/src/openpi/training/config.py with provided config.py
  - Update config paths for local setup
  - Set LeRobot repo_id to dataset (e.g., task_overall/train or task_obstacle/train)
  - Replace base-checkpoint path with PI0 or PI0.5 base checkpoint params directory

#UAV #VisionLanguageAction #Simulation #Robotics #OpenSource #3DGS

---

*Source: [jingyu198/HUGE-Bench](https://github.com/jingyu198/HUGE-Bench)*
