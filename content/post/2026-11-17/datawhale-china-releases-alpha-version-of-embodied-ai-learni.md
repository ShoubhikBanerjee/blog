---
title: "Datawhale China Releases Alpha Version of Embodied AI Learning Platform with Online Simulation"
slug: "datawhale-china-releases-alpha-version-of-embodied-ai-learning-platform-with-online-simulation"
description: "Datawhale China has launched an alpha internal test version of 'Dive into Embodied AI' (具身智能), a comprehensive learning platform for embodied intelligent robot development. The platform covers the..."
date: 2026-11-17T22:09:21+05:30
tags: [EmbodiedAI, Robotics, ReinforcementLearning, VLA, MuJoCo, Datawhale]
categories: ["AI", "Machine Learning", "Robotics", "AI Education", "Simulation"]
image: "https://avatars.githubusercontent.com/u/46047812?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Datawhale China Releases Alpha Version of Embodied AI Learning Platform with Online Simulation

Datawhale China has launched an alpha internal test version of "Dive into Embodied AI" (具身智能), a comprehensive learning platform for embodied intelligent robot development. The platform covers the full "decision—control—perception" pipeline using reinforcement learning, world models, and VLA (Vision-Language-Action) methods across simulation environments, controllers, motion planning, and perception systems.

## 🔍 Overview
The platform is structured into four main sections:
- **Embodied Introduction** (具身导论): Field overview with curated papers, datasets, open-source projects, and tools
- **Theoretical Foundation** (理论基础): Core principles and concepts
- **Project Practice** (项目实战): Hands-on projects organized by AMD Zone, Simulation Practice, and Real Machine Practice
- **Online Simulation** (在线仿真): Interactive browser-based simulation environment

The release is labeled as an alpha internal test version, currently undergoing migration and restructuring with some chapters as placeholder pages. Users are encouraged to submit issues for feedback.

## 🧩 How it works
### Online Simulation Features
The simulation environment (accessible at https://datawhalechina.github.io/dive-into-embodied-ai/simulation) provides:
- Two modes: game-style free manipulation and policy demonstration
- Pre-loaded policies:
  - Go2 and Pupper v3 PPO walking policies
  - Quaddle periodic gait comparison
  - MicroDuck head and full-body joint free manipulation (walking weights not yet available)
- Controls: keyboard and on-screen directional buttons, pause, reset, slow simulation, camera follow
- Go2 displays with simplified appearance using original collision model

### Curriculum Structure
**Embodied Introduction (7 chapters):**
1. What is Embodied AI — definition, perception-decision-action loop, body importance
2. Development History — rule programming, model control, deep RL, and large model eras
3. Robot Skills — tasks, grasping, manipulation, locomotion, navigation
4. Embodied Carriers — humanoid, robotic arms, wheeled, quadruped, mobile manipulation, simulation bodies
5. Core Challenges — data, sim-to-real, generalization, real-time, safety, evaluation
6. Tech Stack — VLM, VLA, world models, manipulation, control, navigation modules
7. Career Roles — brain algorithms, cerebellum algorithms, perception/navigation, engineering platforms, hardware

**Project Practice Categories:**
| Category | Projects |
|---|---|
| AMD Zone | AUP Learning Cloud (Ryzen AI APU, ROCm, JupyterHub, Code Server); MicroDuck RL on AMD ROCm (R9700, ROCm MuJoCo Warp, dynamic contact regression, bipedal PPO); Pupper Quadruped on AMD (RL locomotion policies, VLA experiments) |
| Simulation Practice | Build Quadruped from Scratch (MuJoCo, PD, kinematics, policy training, language control, perception); Petoi Quaddle Servo Walking (official URDF, alternating gait, contact verification, infinite checkerboard); MicroDuck RL (mjlab + MuJoCo Warp, GPU parallel PPO, bipedal gait); MuJoCo Arm with DDPG; ACT Bimanual Manipulation (ACT + ALOHA training, evaluation, reproduction) |
| Real Machine Practice | LeRobot Chinese Course (Units 0-2: robot learning, datasets, toolchain, classic robotics); SO-101 + LeRobot Real Machine Tutorial (hardware connection, safety testing, action replay) |

## 🚀 Availability
- Platform language support: Chinese, English, Italian
- Alpha version — active migration and restructuring in progress
- Some chapters are placeholder pages
- Model library integration planned (see simulation/README.md)
- Tutorial and interactive pages include "Copy as Markdown" with Markdown preview dropdown

## 💡 Why it matters
This platform provides an end-to-end educational resource bridging theory and practice for embodied AI development, with particular emphasis on hardware-accessible projects (AMD ROCm support, real robot tutorials) and interactive browser-based simulation for immediate experimentation without local GPU setup.

#EmbodiedAI #Robotics #ReinforcementLearning #VLA #MuJoCo #Datawhale

---

*Source: [datawhalechina/dive-into-embodied-ai](https://github.com/datawhalechina/dive-into-embodied-ai)*
