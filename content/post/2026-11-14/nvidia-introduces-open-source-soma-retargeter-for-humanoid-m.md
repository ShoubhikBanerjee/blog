---
title: "NVIDIA Introduces Open Source SOMA Retargeter for Humanoid Motion Adaptation"
slug: "nvidia-introduces-open-source-soma-retargeter-for-humanoid-motion-adaptation"
description: "The open source NVIDIA SOMA Retargeter adapts human motion data to fit a humanoid robot's specific proportions, joint structures, and ranges of motion. Built around the shared human-motion..."
date: 2026-11-14T12:02:58+05:30
tags: [NVIDIA, Robotics, SOMARetargeter, HumanoidRobots, OpenSource]
categories: ["AI", "Robotics", "AI Tools", "Open Source", "Machine Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/SOMA_Retargeter_Featured_600x338.gif"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Introduces Open Source SOMA Retargeter for Humanoid Motion Adaptation

The open source NVIDIA SOMA Retargeter adapts human motion data to fit a humanoid robot's specific proportions, joint structures, and ranges of motion. Built around the shared human-motion representation in NVIDIA SOMA-X, the tool provides capabilities to configure robot embodiments, refine motion, and process trajectory data for downstream learning or control systems.

## ⚙️ How It Works

Directly copying human joint movement is not feasible for humanoid robots due to differences in physical structure. SOMA Retargeter adapts motion through a standardized workflow:

- **Input**: Reads a Biovision Hierarchy (BVH) animation represented on the SOMA base skeleton.
- **Processing**: Scales motion targets to the robot's proportions, solves configured inverse-kinematics objectives for joint poses per frame, and applies configured post-processing corrections.
- **Output**: Generates a comma-separated values (CSV) file containing the robot's root position, orientation, and joint angles for each frame.

## 🧩 Compatible Motion Sources

Human motion inputs can be unified on the SOMA skeleton representation across multiple capture and generation methods:

| Source / Tool | Function | Description |
| --- | --- | --- |
| BONES-SEED | Motion Capture | Collection of human motion-capture data. |
| GEM-X | Video Reconstruction | Reconstructs whole-body 3D human motion from a single video using the SOMA body model. |
| Kimodo | Motion Generation | Generates human motion sequences from text and pose constraints on the SOMA skeleton. |
| ARDY | Motion Generation | Generates movement from text and pose constraints with interactive steering as motion unfolds. |

## 🚀 SOMA Retargeter v0.2 Release

The v0.2 release includes sample motions from the BONES-SEED dataset, reference retargeting results, and pre-built configurations for five humanoid robot embodiments:

- Unitree G1
- Unitree H2
- Booster T1
- AgiBot X2 Ultra
- AgiBot A3T3

To retarget a sample forward walk using the Unitree G1 configuration, users open a terminal in the repository root and start the viewer:

`uv run python app/bvh_to_csv_converter.py --config assets/default_bvh_to_csv_converter_config.json --viewer gl`

With `unitree_g1` selected by default, selecting **Retarget** on the BVH Motion row under **Scene Options → Motion** executes the scaling, inverse-kinematics solving, and post-processing. The viewer displays the resulting robot animation alongside the source human motion.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/11/Figure2_Converter_G1_Walk_UI_Clean_1202x921.webp)

#NVIDIA #Robotics #SOMARetargeter #HumanoidRobots #OpenSource

---

*Source: [Adapt Human Motion for Robots with NVIDIA SOMA Retargeter | NVIDIA Technical Blog](https://developer.nvidia.com/blog/adapt-human-motion-for-robots-with-nvidia-soma-retargeter/)*
