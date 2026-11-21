---
title: "ROS-Free Sim-to-Real Framework for Vision-Language-Action Models"
slug: "ros-free-sim-to-real-framework-for-vision-language-action-models"
description: "A new Robot Control Stack (RCS) provides a lean, ROS‑free sim‑to‑real framework for training and deploying Vision‑Language‑Action (VLA) models and reinforcement‑learning agents."
date: 2026-11-21T06:15:51+05:30
tags: [RobotLearning, SimToReal, VisionLanguageAction, RL, Gymnasium]
categories: ["AI", "Robotics", "Machine Learning", "Reinforcement Learning", "Computer Vision"]
image: "https://avatars.githubusercontent.com/u/209346905?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ROS-Free Sim-to-Real Framework for Vision-Language-Action Models

A new Robot Control Stack (RCS) provides a lean, ROS‑free sim‑to‑real framework for training and deploying Vision‑Language‑Action (VLA) models and reinforcement‑learning agents.

## 🔍 Overview
- A lean, ROS‑free sim‑to‑real framework for training and deploying Vision‑Language‑Action (VLA) models and RL agents.
- Built as a native Gymnasium wrapper that unifies MuJoCo simulation and real‑world robot control into a single API.

## 🧩 How it works
- RCS provides native MuJoCo Gymnasium wrappers with synchronous execution for several robots.
- The same Python code used in simulation can be run on physical hardware without modification.
- Execution is synchronous, matching the highly parallelized data‑collection pattern of modern ML workflows.
- Implemented in Python with a lightweight C++ backend, eliminating complex message‑passing or network configuration.

## ⚙️ Key details
- **Zero ROS overhead** – No ROS/ROS2 or MoveIt dependencies.
- **Modular wrapper architecture** – Cameras, grippers, and action spaces can be stacked as needed.
- **Factory functions** – e.g., `rcs.envs.creators.SimEnvCreator` for quick environment composition.
- **Ready‑to‑Use apps** – Includes teleoperation data‑collection and remote model inference via vlagents.
- **Relative actions** – Bounded by 10 cm translation and 10 ° rotation.
- **Access to low‑level robot API** – Retrieve current Cartesian position.

## 📦 Supported Robots
| Robot | Support |
|-------|---------|
| Franka FR3 / Panda | Native support out‑of‑the‑box |
| xArm7 | Native support out‑of‑the‑box |
| UR5e | Native support out‑of‑the‑box |
| SO101 | Native support out‑of‑the‑box |
| I2RT YAM | Native support out‑of‑the‑box |
| Flexiv Rizon 4s | Native support out‑of‑the‑box |

## 🚀 Availability
- RCS ships with pre‑built applications for data collection via teleoperation and remote inference.
- Users can compose custom Gymnasium environments to match specific training needs.

#RobotLearning #SimToReal #VisionLanguageAction #RL #Gymnasium

---

*Source: [RobotControlStack/robot-control-stack](https://github.com/RobotControlStack/robot-control-stack)*
