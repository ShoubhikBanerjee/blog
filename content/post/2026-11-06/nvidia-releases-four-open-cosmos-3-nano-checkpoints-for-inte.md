---
title: "NVIDIA Releases Four Open Cosmos 3‑Nano Checkpoints for Interactive World Simulation"
slug: "nvidia-releases-four-open-cosmos-3nano-checkpoints-for-interactive-world-simulation"
description: "NVIDIA has added four open‑weight checkpoints to its Cosmos 3 model family, enabling interactive world simulation and multi‑sensor, multi‑view driving scene generation."
date: 2026-11-06T18:03:32+05:30
tags: [NVIDIA, WorldSimulation, OpenModels, AI, LiDAR]
categories: ["AI", "Machine Learning", "Computer Vision", "Robotics", "Simulation"]
image: "https://cdn-uploads.huggingface.co/production/uploads/677c471f8b4c4e271e57eaa5/rtmGVvFdD6JqkjBc26vsp.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Four Open Cosmos 3‑Nano Checkpoints for Interactive World Simulation

NVIDIA has added four open‑weight checkpoints to its Cosmos 3 model family, enabling interactive world simulation and multi‑sensor, multi‑view driving scene generation.

## 🔍 Overview
- The new checkpoints are built on the Cosmos 3 Nano architecture and each contains **16 B trainable parameters**.
- All models are released under **OpenMDW 1.1**, which permits both commercial and non‑commercial use.
- They target
  - offline synthetic driving data creation,
  - fast streaming simulation,
  - text‑guided visual rendering, and
  - bimanual robot interaction.

## 🧩 How it works
- **Cosmos3‑Nano‑Transfer‑Auto** generates synchronized video from up to **11 camera views** (including fisheyes) and joint RGB‑LiDAR data. It uses per‑camera World Scenario Map (WSM) controls for scene structure and traffic motion, while text prompts guide appearance.
- **Cosmos3‑Nano‑Sim‑Auto** is a causally distilled streaming variant of Transfer‑Auto. It produces small chunks of synchronized camera video and LiDAR in a few denoising steps, leveraging generated history and updated driving controls for long, interactive rollouts. A simulation runtime and WSM renderer are required to update controls from driving inputs.
- **Cosmos3‑Nano‑Sim‑Transfer** takes simulator controls and a text prompt to render photorealistic video observations. The physics and ground‑truth state remain with the simulator; the text prompt only influences appearance.
- **Cosmos3‑Nano‑Sim‑Bimanual** predicts video based on robot or camera actions. It supports two‑arm simulation for YAM and AgiBot embodiments, controllable by a policy or human‑operated joysticks. Training used 59 control values padded to 64, with a schema that defines coordinate frames, rotations, gripper calibration, validity masks, and control domains.

## ⚙️ Key details
- **Open weight**: All four checkpoints are open‑weight and can be post‑trained on user data to match specific camera layouts, LiDAR configurations, or environments.
- **Multi‑sensor sync**: Camera and LiDAR streams are generated together, linking visual observations with 3‑D sensing.
- **Control flexibility**: Scene and traffic‑signal controls let researchers vary road layouts and signal states, enabling study of driving‑policy responses.
- **Streaming interaction**: Streaming generation ties video prediction to ongoing interaction, allowing exploration of how actions and observations unfold together.
- **Licensing**: Released under OpenMDW 1.1, allowing commercial and non‑commercial use.

## 🚀 Availability
The four checkpoints—**Cosmos3‑Nano‑Transfer‑Auto**, **Cosmos3‑Nano‑Sim‑Auto**, **Cosmos3‑Nano‑Sim‑Transfer**, and **Cosmos3‑Nano‑Sim‑Bimanual**—are now available as open‑weight models in the Cosmos 3 family.

## 💡 Why it matters
- Provides researchers with **open tools** for generating realistic driving data across many sensors and viewpoints.
- Enables **fast, interactive simulation** of driving scenarios, supporting closed‑loop policy evaluation.
- Extends simulation capabilities to **robotic manipulation** with bimanual actions, broadening the scope of world‑model research.

| Model | Primary capability |
|---|---|
| Cosmos3‑Nano‑Transfer‑Auto | Offline multi‑view driving data generation with weather, lighting, text‑guided appearance, and joint RGB‑LiDAR sync |
| Cosmos3‑Nano‑Sim‑Auto | Fast streaming of synchronized camera video and LiDAR for interactive driving rollouts |
| Cosmos3‑Nano‑Sim‑Transfer | Convert simulator controls + text prompt into photorealistic video observations |
| Cosmos3‑Nano‑Sim‑Bimanual | Predict video from bimanual robot actions; supports YAM and AgiBot two‑arm embodiments |


![figure](https://cdn-uploads.huggingface.co/production/uploads/6ab2a746c7d0655b3d8dfbb9/fownH6rn05tSp1jDBTz8m.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/68127936de624fb6f57d9989/3vFxCEUXz_xJVrTBr4hNr.jpeg)

#NVIDIA #WorldSimulation #OpenModels #AI #LiDAR

---

*Source: [New NVIDIA Cosmos 3 Open Models for Interactive World Simulation](https://huggingface.co/blog/nvidia/cosmos-interactive-world-simulation)*
