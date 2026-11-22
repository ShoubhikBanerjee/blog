---
title: "gym-pybullet-drones refactored for gymnasium and Betaflight SITL"
slug: "gym-pybullet-drones-refactored-for-gymnasium-and-betaflight-sitl"
description: "A minimalist refactoring of the `gym-pybullet-drones` repository has been released to ensure compatibility with `gymnasium`, `stable-baselines3` 2.0, and `betaflight` SIM. The project, originally..."
date: 2026-11-22T22:08:30+05:30
tags: [gympybulletdrones, ReinforcementLearning, MultiAgent, gymnasium, betaflight]
categories: ["AI", "Machine Learning", "Reinforcement Learning", "Simulation", "Open Source"]
image: "https://avatars.githubusercontent.com/u/19434714?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# gym-pybullet-drones refactored for gymnasium and Betaflight SITL

A minimalist refactoring of the `gym-pybullet-drones` repository has been released to ensure compatibility with `gymnasium`, `stable-baselines3` 2.0, and `betaflight` SIM. The project, originally featured in GitHub's Maintainer Spotlight 2026, now supports both single-agent and multi-agent tasks with updated system requirements.

## 🔍 Overview

- **Refactoring Goal:** Minimalist update for compatibility with `gymnasium`, `stable-baselines3` 2.0, and `betaflight` SITL.
- **Version Control:** The original IROS 2021 codebase is accessible via `git checkout [paper|master]`.
- **Citation:** Users are encouraged to cite the IROS 2021 paper and the original codebase.

## 🧩 How it works

- **Single-Agent Task:** One drone hovers at z == 1.0.
- **Multi-Agent Task:** Two drones hover at z == 1.2 and 0.7 respectively.
- **PettingZooWrapper:** Exposes multi-drone aviary through PettingZoo's Parallel API, assigning one agent per drone (`drone_0`, `drone_1`, ...).
- **Observation and Reward:** Each agent receives its own row of the aviary's observation. The aviary's team reward and episode flags are shared by all agents.
- **Centralized Critics:** `env.state()` returns every drone's kinematics for centralized critics.

## ⚙️ Key details

| Requirement | Details |
| :--- | :--- |
| **Operating Systems** | Tested on Intel x64/Ubuntu 24.04 and Apple Silicon/macOS 26 |
| **Python & pybullet** | Requires Python 3.10+; `pybullet` has no pre-built wheel for versions beyond 3.10 |
| **Ubuntu Setup** | Install `gcc` to allow `pip3 install` to build `pybullet` |
| **SITL Setup** | One-time setup requires building one SITL executable per drone from the repo's top folder |
| **Dependencies** | `--num_drones` must be less than or equal to the number passed to `clone_bfs.sh`; `curl` may be required via `apt install` |

## 💡 Why it matters

The `PettingZooWrapper` makes the environment usable with Multi-Agent Reinforcement Learning (MARL) libraries built on PettingZoo. The refactoring ensures the environment remains functional with modern reinforcement learning stacks like `stable-baselines3` 2.0 while supporting Betaflight SITL for drone simulation.

#gym-pybullet-drones #ReinforcementLearning #Multi-Agent #gymnasium #betaflight

---

*Source: [learnsyslab/gym-pybullet-drones](https://github.com/learnsyslab/gym-pybullet-drones)*
