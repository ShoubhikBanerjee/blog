---
title: "FoundationWorlds launches ToyBlocks simulation framework for robot learning"
slug: "foundationworlds-launches-toyblocks-simulation-framework-for-robot-learning"
description: "Today a new framework called **FoundationWorlds** was introduced, pairing a controlled simulated world with tools for automatically generating tasks, training demonstrations, and metrics to measure a..."
date: 2026-11-06T22:02:31+05:30
tags: [Robotics, Simulation, MachineLearning, AI]
categories: ["AI", "Robotics", "Simulation", "Machine Learning", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/OAJMu2jr7i5jVAbmsKdZW.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# FoundationWorlds launches ToyBlocks simulation framework for robot learning

Today a new framework called **FoundationWorlds** was introduced, pairing a controlled simulated world with tools for automatically generating tasks, training demonstrations, and metrics to measure a robot’s behavior over time.

## 🔍 Overview
- The first FoundationWorld is **ToyBlocks**, an open simulation framework built around a robot arm and blocks on a tabletop.
- ToyBlocks automatically generates **demonstrations** – recordings of a robot completing tasks in simulation – without requiring time‑consuming teleoperation.
- It builds on earlier work in open robot learning, including **MolmoAct 2**, **MolmoBot**, and **MolmoSpaces**.

## 🧩 How it works
- **Skill generation** uses reinforcement learning (RL) and motion planning in **Isaac Lab**, Nvidia’s open‑source framework for robot learning in simulation.
- Policies learn non‑prehensile skills such as pushing a block across the table or flipping it onto another face without picking it up.
- Skill generation can draw on **privileged information** (exact block position and orientation) that a real robot cannot sense, enabling automatic creation of skills that would otherwise need teleoperation.
- A **task‑and‑motion planner (TAMP)** automatically selects and sequences skills to solve a task and plans the robot’s movements between them.
- Each plan run in simulation produces a dataset of recorded demonstrations with labels describing the performed task or skill.
- Data generation scales by running hundreds of plans in parallel on a single GPU, achieving up to **24 × real‑time** performance.

## ⚙️ Key features
- Designed around four requirements:
  1. Realistic physics and appearance
  2. Automatic generation of tasks and demonstrations at scale
  3. Challenges that combine reasoning with dexterity
  4. Broad coverage of the tasks possible within a domain
- Blocks display pictures and letters, enabling **searching, sorting, and arranging** tasks.
- A robot may need to **turn a block to see a hidden face** before deciding where it belongs.
- **Domain randomization** varies block size, table height, and other physical properties from scene to scene to test generalization.
- **High‑level reasoning models** decide what to do; **low‑level action models** control the robot’s movements.
- **Molmo 2** selects skills (e.g., rotation, flipping) via a pointing interface; **ManiFlow** executes the commanded skills on the simulated arm.
- The controllable data generator lets users create **training mixtures** that emphasize particular skills or fill gaps in existing datasets.

## 💡 Why it matters
- ToyBlocks gives researchers a way to study robotics questions in a deliberately constrained domain, providing realistic physics, automatic data generation, and a blend of reasoning and dexterity challenges.
- By training models from raw sensor observations, the framework bridges the gap between simulation and real‑world perception problems.


![figure](https://www.datocms-assets.com/64837/1793917318-toyblocks-framework-current.png)

![figure](https://www.datocms-assets.com/64837/1793904303-toyblocks-visual-08-ai2.png)

![figure](https://www.datocms-assets.com/64837/1793919269-toyblocks-visual-12a-30-trials.png)

#Robotics #Simulation #MachineLearning #AI

---

*Source: [ToyBlocks: A controlled world for robot learning and evaluation](https://huggingface.co/blog/allenai/toyblocks)*
