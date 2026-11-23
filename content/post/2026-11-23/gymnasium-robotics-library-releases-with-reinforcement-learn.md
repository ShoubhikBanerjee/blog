---
title: "Gymnasium-Robotics Library Releases with Reinforcement Learning Robotic Environments"
slug: "gymnasium-robotics-library-releases-with-reinforcement-learning-robotic-environments"
description: "The Gymnasium-Robotics library has been released, offering a collection of Reinforcement Learning robotic environments built on the Gymnasium API and powered by the MuJoCo physics engine. Users can..."
date: 2026-11-23T22:18:20+05:30
tags: [ReinforcementLearning, Robotics, MuJoCo, Gymnasium, RLENvironments]
categories: ["AI", "Machine Learning", "Robotics", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/62961550?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Gymnasium-Robotics Library Releases with Reinforcement Learning Robotic Environments

The Gymnasium-Robotics library has been released, offering a collection of Reinforcement Learning robotic environments built on the Gymnasium API and powered by the MuJoCo physics engine. Users can install environments via pip, with support for both the maintained MuJoCo Python bindings and legacy mujoco-py versions through optional extras. The package is officially supported on Linux and macOS, with community contributions welcomed for Windows compatibility.

## 🧩 Available Environments

- **Fetch Environments**: 7-degree-of-freedom robot arm for tasks including Reach, Push, Slide, and Pick and Place
- **Shadow Dexterous Hand Environments**: 24-degree-of-freedom anthropomorphic hand for object manipulation with cube, egg-object, or pen
- **Maze Environments**: Navigation tasks using 2-DoF force-controlled ball or Ant agent, with varying maze complexity
- **Adroit Arm Environments**: Shadow Dexterous Hand with additional arm degrees of freedom for hammering, door opening, pen twirling, and ball manipulation
- **Franka Kitchen Environments**: 9-DoF Franka robot arm in a kitchen setting for multitask interaction scenarios
- **MaMuJoCo**: Multi-agent factorizations using pettingzoo.ParallelEnv API
- **D4RL Environments**: Now available with refactored action/observation spaces

## ⚙️ API and Features

The environments extend the core Gymnasium API by inheriting from GoalEnv class, which enforces:

- Dictionary observation space containing three required keys
- Exposed reward, terminated, and truncated signals for flexible goal re-computation
- Compatibility with Hindsight Experience Replay (HER) algorithms

Some environment variations include data from 92 touch sensors in the observation space.

#ReinforcementLearning #Robotics #MuJoCo #Gymnasium #RLENvironments

---

*Source: [Farama-Foundation/Gymnasium-Robotics](https://github.com/Farama-Foundation/Gymnasium-Robotics)*
