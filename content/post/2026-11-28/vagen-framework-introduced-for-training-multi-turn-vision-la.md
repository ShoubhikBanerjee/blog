---
title: "VAGEN framework introduced for training multi-turn vision-language model agents"
slug: "vagen-framework-introduced-for-training-multi-turn-vision-language-model-agents"
description: "VAGEN is a new reinforcement learning (RL) framework specifically designed for training multi-turn vision-language model (VLM) agents. The framework enables these agents to build an internal world..."
date: 2026-11-28T18:07:42+05:30
tags: [VAGEN, RL, VLM, AI, Agents, ReinforcementLearning]
categories: ["AI", "Machine Learning", "Reinforcement Learning", "Vision-Language Models", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/204804147?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# VAGEN framework introduced for training multi-turn vision-language model agents

VAGEN is a new reinforcement learning (RL) framework specifically designed for training multi-turn vision-language model (VLM) agents. The framework enables these agents to build an internal world model through explicit visual state reasoning.

## 🔍 Overview
- VAGEN functions as a multi-turn reinforcement learning framework built for VLM agents.
- It supports a novel approach called World Modeling RL, which improves multi-turn performance by explicitly supervising the world model reasoning process.
- The framework frames multi-turn VLM agentic tasks as a Partially Observable Markov Decision Process (POMDP).

## 🧩 How it works
- **World Modeling RL**: A reinforcement learning approach that supervises the world model reasoning process to enhance agent performance.
- **StateEstimation**: A reinforcement signal that helps the agent determine "what is the current state?"
- **TransitionModeling**: A reinforcement signal that helps the agent determine "what comes next?"
- **LLM-as-Judge**: Used to provide a world-modeling reward for the StateEstimation and TransitionModeling signals.
- **Architecture Decoupling**: The reusable harness, environment, model, rollout, and evaluation boundaries keep world-modeling signals independent from the selected training algorithm.

## ⚙️ Key details
- **VAGEN-Lite**: A lightweight and clean reimplementation of VAGEN built on the VERL agent-loop for easy customization and stable performance.
- **Version Support**: Added support for Verl 0.9.0, which decoupled the environment and harness layer.
- **Legacy Code**: Previous full-featured releases are available on the vagen-legacy branch, and the last commit before major updates is tagged as vagen-lite-verl-v0.6.1-final.

## 🚀 Availability
- **VAGEN-Lite Release**: Introducing VAGEN-Lite in December 2025 as a lightweight reimplementation.
- **Branch Migration**: The `main` branch migrated to VAGEN-Lite in February 2026.
- **Verl Update**: Support for Verl 0.9.0 added in August 2026, marking a major update that decoupled the environment and harness layer.

#VAGEN #RL #VLM #AI #Agents #ReinforcementLearning

---

*Source: [mll-lab-nu/VAGEN](https://github.com/mll-lab-nu/VAGEN)*
