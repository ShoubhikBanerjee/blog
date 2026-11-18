---
title: "Strands Agents SDK and StarVLA Robotics Platform Updates"
slug: "strands-agents-sdk-and-starvla-robotics-platform-updates"
description: "This update covers two distinct open-source developments: a Python-based SDK for building AI agents with minimal code, and StarVLA, a research platform for vision-language-action models in robotics."
date: 2026-11-18T18:09:03+05:30
tags: [AIAgents, Robotics, StarVLA, OpenSource, VisionLanguageAction]
categories: ["AI", "Robotics", "AI Agents", "Open Source Software", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/209155962?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Strands Agents SDK and StarVLA Robotics Platform Updates

This update covers two distinct open-source developments: a Python-based SDK for building AI agents with minimal code, and StarVLA, a research platform for vision-language-action models in robotics.

## 🧩 Strands Agents SDK
A model-driven approach to building AI agents is now available via the `strands-agents` SDK.

- **Language & Version:** Python 3.10 or higher.
- **Installation:** `pip install strands-agents`.
- **Scope:** The core SDK is installed by default. Many samples require additional packages, so users should check each sample's README and `requirements.txt` or `pyproject.toml`.
- **Node.js Support:** For Node.js 18 or higher, the package is available as `@strands-agents/sdk` via npm or yarn.
- **Usage Warning:** Examples in the repository are for demonstration and educational purposes only. They are not intended for direct use in production. Proper security and testing procedures must be applied before deployment.

## 🤖 StarVLA Robotics Research Platform
StarVLA ("start VLA") is an open-source research platform for integrating cutting-edge technologies for generalist robots. It follows a top-down, intuitive separation and high-cohesion, low-coupling principle to enable plug-and-play design and rapid prototyping.

### ⚙️ Key Details & Branches
- **Stable Branch:** Use the `starVLA` branch for verified results.
- **Development Branch:** The `starVLA_dev` branch is where new features are actively merged and may be temporarily unstable. Thanks to the low-coupling design, switching between branches is easy.
- **Custom Scripts:** Files under any `**/bar/` directory are git-ignored, allowing users to place custom scripts without polluting the repository.

### 🚀 Recent Updates
- **2026/09/05:** Updated RoboCasa365 (PandaOmnon) integration with a consolidated data, training, and evaluation guide. A 50-task local research snapshot covering StarVLA-OFT, StarVLA-PI, and StarVLA-GR00T is included. The best selected local result is StarVLA-PI at 40.64% (1,016/2,500). These results are for research reference and are not official RoboCasa leaderboard submissions.
- **2026/08/27:** Released VLAct and the paper "Beyond Data Scaling: Representation-Centric Continued Pre-training for Vision-Language-Action Models." VLAct introduces representation-centric continued pre-training for reusable VLA backbones. Users of the Qwen3-VL-4B StarVLA recipe can try the VLAct-pretrained backbone by setting `framework.qwenvl.base_vlm` to `[StarVLA/VLAct_Qwen3_Pretrain]`.
- **2026/08/09:** StarVLA now supports RoboDojo through XPolicyLab, providing training recipes for the official RoboDojo dataset and an evaluation path for released checkpoints.
- **2026/06/22:** A StarVLA Contributors Group was created to facilitate communication and discuss the contributor list before each release.
- **2026/05/30:** Support for VLA training with Qwen-series backbones on Ascend NPU was added.
- **2026/05/01:** A step-by-step guide for integrating custom robots or datasets into StarVLA is available. Additionally, agent skills are being built to make StarVLA a substrate for AI coding agents, with verification for GitHub Copilot.
- **2026/04/09:** A unified multi-benchmark co-training example combining LIBERO, SimplerEnv, RoboTwin, and VLA-Arena is in progress.

#AIAgents #Robotics #StarVLA #OpenSource #Vision-Language-Action

---

*Source: [strands-agents/samples](https://github.com/strands-agents/samples)*
*Source: [starVLA/starVLA](https://github.com/starVLA/starVLA)*
