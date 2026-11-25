---
title: "Adding Local Obstacle Avoidance to Microduck via Isaac Lab and Newton"
slug: "adding-local-obstacle-avoidance-to-microduck-via-isaac-lab-and-newton"
description: "This update introduces a local obstacle avoidance system for the Microduck robot, trained within NVIDIA Isaac Lab using Newton physics simulation. By keeping the original walking policy fixed and..."
date: 2026-11-25T06:12:19+05:30
tags: [Robotics, IsaacLab, Newton, Microduck, ObstacleAvoidance]
categories: ["AI", "Robotics", "Simulated Environments", "Reinforcement Learning"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6847ab8c06094fa4afb6ee38/M70tUMNd7N4KO5QGI37YZ.png"
author: "Shoubhik Banerjee"
draft: false
---

# Adding Local Obstacle Avoidance to Microduck via Isaac Lab and Newton

This update introduces a local obstacle avoidance system for the Microduck robot, trained within NVIDIA Isaac Lab using Newton physics simulation. By keeping the original walking policy fixed and training a separate avoidance controller, the robot can navigate varied courses with ToF sensing.

## 🔍 Overview
- The goal is to add local obstacle avoidance while keeping the Microduck's walking policy fixed.
- A separate avoidance controller is trained using time-of-flight (ToF) sensing.
- The workflow reuses the walking policy from the first Microduck tutorial with its weights kept fixed.
- Users choose a direction with a gamepad; the controller adjusts the velocity command before passing it to the walking policy.

## 🧩 How it works
- **Environment**: Varied courses are built with reusable SimReady assets from Hugging Face (e.g., cardboard box, office bin, bedside cabinet, cones).
- **Simulation**: Newton simulates physics and sensor depth measurements.
- **Training**: Policies are trained in Isaac Lab across thousands of GPU-parallel simulations.
- **Sensing**: ToF sensing is modeled using Newton’s raycaster.
- **Control Flow**: 
  1. A navigation policy uses ToF sensing to adjust forward, lateral, and yaw commands at 50 Hz.
  2. The frozen walking policy converts these commands into joint actions.
  3. This allows the robot to learn obstacle avoidance without retraining its walking behavior.

## ⚙️ Key details
- **Task Separation**: The `IsaacContrib-ObstacleAvoidance-Flat-MicroDuck` task separates obstacle avoidance from balance.
- **Sensor Model**: `MicroDuckToFCamera` extends Newton’s `LegacyMultiMeshRayCasterCamera` to model the VL53L5CX ToF sensor.
  - Measures distance across an 8×8 grid at 15 Hz.
  - Field of view is 45°.
  - Range is 0.12–4 m.
  - Placement follows the duck’s head, similar to the real robot.
- **Data Quality**: Real recordings informed sensor placement and floor readings in simulation.
- **Robustness**: Training adds noise, delays, and missing measurements (including near grid edges) to expose the policy to imperfect data.
- **Code Structure**: 
  - Task location: `isaaclab_tasks.contrib.microduck_obstacle`
  - Configuration: `obstacle_avoidance_env_cfg.py`
  - ToF sensing: `sensors.py`
  - MDP components: `mdp/`
- **Training Inputs**: 
  - Actor receives ToF history, body state, and controller state available on the real robot.
  - Critic accesses additional simulation state for learning guidance but is not needed for deployment.
- **Rewards**: Encourage progress toward the goal, safe arrivals, and movement around obstacles.
- **Layout Randomization**: At each episode reset, the code samples a layout, shuffles props, and varies placement/rotation. Most courses scatter obstacles ahead, with some clear paths and barriers.

## 🚀 Availability
- **Framework**: NVIDIA Isaac Lab (open-source).
- **Setup**: Install `uv`, clone the `exp/microduck` branch of the Isaac Lab repository, and install dependencies.
- **Assets**: Simple primitives and OpenUSD assets are available via SimReady Central on Hugging Face.

![figure](https://cdn-uploads.huggingface.co/production/uploads/6847ab8c06094fa4afb6ee38/Tqh5FK78Q1qDuzhEDGpqQ.gif)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6847ab8c06094fa4afb6ee38/RCQ8kWS0Ky4j_YU1ch-G3.gif)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6847ab8c06094fa4afb6ee38/zJU03xK6y0Ii0XOWtmiwa.gif)

#Robotics #IsaacLab #Newton #Microduck #ObstacleAvoidance

---

*Source: [Microduck Obstacle Avoidance: A Sim2Real Workflow with Isaac Lab and Newton](https://huggingface.co/blog/nvidia/microduck-obstacle-avoidance)*
