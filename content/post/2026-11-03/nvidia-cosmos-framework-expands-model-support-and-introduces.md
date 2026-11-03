---
title: "NVIDIA Cosmos Framework Expands Model Support and Introduces Cosmos 3 Nano Simulation Recipes"
slug: "nvidia-cosmos-framework-expands-model-support-and-introduces-cosmos-3-nano-simulation-recipes"
description: "NVIDIA has updated its Cosmos platform, adding broader model compatibility, new training and inference skills, and Cosmos 3 Nano simulation recipes for robotics and autonomous‑driving scenarios."
date: 2026-11-03T22:02:32+05:30
tags: [Cosmos, AI, Simulation, Robotics, NVIDIA]
categories: ["AI", "Machine Learning", "AI Platforms", "Robotics", "Computer Vision"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/cosmos-framework-tech-blog-600x338-5784057.webp"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Cosmos Framework Expands Model Support and Introduces Cosmos 3 Nano Simulation Recipes

NVIDIA has updated its Cosmos platform, adding broader model compatibility, new training and inference skills, and Cosmos 3 Nano simulation recipes for robotics and autonomous‑driving scenarios.

## 🔍 Overview
- Cosmos is a platform of world foundation models and development tools for physical AI.
- Cosmos Framework provides agent skills and recipes for world model training, multimodal data processing, optimization and inference.
- The framework is open, fully modular, and supports the complete model development lifecycle.
- Cosmos NIM microservices enables GPU‑accelerated serving through application APIs.
- Support has been expanded beyond Cosmos 3 to include NVIDIA Alpamayo, GR00T, Qwen, pi0.5, and other compatible Hugging Face models.

## ⚙️ Core Features
- Train on text, images, video, audio, and actions using new agent skills.
- Adapt models with LoRA (parameter‑efficient) or full supervised fine‑tuning (SFT).
- Load data via JSONL, WebDataset, LeRobot, or custom adapters; train across GPUs and resume from checkpoints.
- Post‑training skills can be pointed to by agents for acceleration and automation.
- Both online and offline reinforcement‑learning (RL) paths are now covered.
- Rollout, reward, and training roles can run on shared GPUs or separate pools.
- Distillation reduces model size or generation steps; quantization reduces memory usage.
- Evaluation includes quality, accuracy, and GPU usage to maximize compute utilization.

## 📦 Model & Runtime Compatibility
| Model | Compatibility |
|-------|---------------|
| NVIDIA Alpamayo | Cosmos Framework |
| GR00T | Cosmos Framework |
| Qwen | Cosmos Framework |
| pi0.5 | Cosmos Framework |
| Other Hugging Face models | Cosmos Framework |

| Runtime | Checkpoint Support |
|---------|--------------------|
| Hugging Face Diffusers | Compatible |
| PyTorch | Compatible |
| SGLang | Compatible |
| vLLM‑Omni | Compatible |
| vLLM | Compatible |
| TRT‑LLM | Compatible |
| TRT‑Edge‑LLM | Compatible |
| NVIDIA NIM | Compatible |

## 🤖 Simulation & Robotics Recipes
- Post‑training and inference recipes are provided for robot simulation, realistic scene generation, multi‑camera driving simulation, and surgical policy evaluation.
- New Cosmos 3 Nano simulation recipes and example checkpoints let developers evaluate checkpoints and adapt Cosmos 3 Nano to custom sensors, action spaces, and data domains.
- Checkpoints support PyTorch and vLLM‑Omni and have been tested on NVIDIA Hopper and Blackwell GPUs.
- Recipes allow selection of GPU count, memory configuration, and inference settings.
- Autonomous‑vehicle (AV) checkpoints accept a prompt and a World Scenario Map (WSM) that defines lanes, objects, road markings, traffic signs, and road boundaries.
- Joint RGB‑LiDAR generation uses HD‑map rangemap controls and can include initial LiDAR observations.
- Prompts specify weather, lighting, time of day, and road conditions, with prefixes that give camera‑rig and field‑of‑view context.
- Cosmos3‑Nano‑Transfer‑Auto uses bidirectional generation to denoise an entire multi‑view clip at once for offline synthetic data generation.
- Supports 30 fps input and output video, up to 400 frames at 480p or 720p; longer sequences can be generated through autoregressive chunking.
- Changing the prompt can transform a daytime drive into a rainy night while preserving road layout and vehicle trajectories.
- These variations enable training and evaluation of perception and driving models across diverse weather and lighting conditions.

## 🚀 Deployment Options
- Cosmos NIM microservices provides GPU‑accelerated serving via application APIs.
- Rollout, reward, and training workloads can be distributed on shared GPUs or isolated GPU pools.
- Users can select GPU count, memory allocation, and inference parameters through provided recipes.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/03/Cosmos-Data-Reasoning.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2025/06/cosmos-robot-arm-composite-gif.gif)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/robotics-press-nurec-devpage-kv-1600x900-1-660x370-png.webp)

#Cosmos #AI #Simulation #Robotics #NVIDIA

---

*Source: [Build World Models for Interactive Simulation with NVIDIA Cosmos | NVIDIA Technical Blog](https://developer.nvidia.com/blog/build-world-models-for-interactive-simulation-with-nvidia-cosmos/)*
