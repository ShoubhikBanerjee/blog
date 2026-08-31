---
title: "Agency in AI is learned, not coded"
description: "A new understanding of AI agency has emerged: the capacity to perceive, reason, and act is a product of model training, not external code orchestration. This principle underpins the development of AI..."
date: 2026-08-31T22:04:32+05:30
tags: [AIagents, machinelearning, neuralnetworks, LLM, reinforcementlearning]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/189210346?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agency in AI is learned, not coded

A new understanding of AI agency has emerged: the capacity to perceive, reason, and act is a product of model training, not external code orchestration. This principle underpins the development of AI agents, from early game-playing systems to modern LLM-based coding assistants.

## 🔍 Overview
Agency in AI is not bestowed by surrounding code but learned during training. A working agent product requires both a trained model and a harness that provides an operational environment.

## 🧩 How it works
- Agency arises from a neural network (e.g., Transformer, RNN) shaped by billions of gradient updates on sequences of perception, reasoning, and action.
- The model supplies intelligence, while the harness (environment, tools, interfaces) supplies the action space.
- Two core components define an agent:
  1. A model trained to act through reinforcement learning, fine-tuning, or other gradient-based methods.
  2. A harness that provides tools, knowledge, observation interfaces, action interfaces, and permissions.

## ⚙️ Key details
- **Training**: Models learn from trajectory data—real-world sequences of perception, reasoning, and action in a target domain.
- **Harness**: Includes tools (file I/O, shell, network, database, browser), knowledge (product docs, API specs), observation interfaces, action interfaces, and permissions.

## 📜 Historical examples
| Year | System | Achievement |
|------|--------|-------------|
| 2013 | DeepMind DQN | Learned 7 Atari 2600 games from raw pixels and scores, surpassing prior algorithms and beating human experts in 3. |
| 2015 | DeepMind DQN | Scaled to 49 Atari games at professional tester level, published in *Nature*. |
| 2019 | OpenAI Five | Defeated Dota 2 world champions (OG) 2-0 after 45,000 years of self-play; won 99.4% of 42,729 public games. |
| 2019 | DeepMind AlphaStar | Beat a professional StarCraft II player 10-1 in closed matches; reached Grandmaster rank (top 0.15% of 90,000 players). |
| 2019 | Tencent Jueyu | Defeated professional Honor of Kings players in full 5v5; in 1v1 mode, pros won just 1 of 15 matches. |
| 2024-2025 | LLM agents | Deployed as coding agents, reading codebases, writing implementations, debugging failures, and coordinating as teams. |

## ❌ Common misconceptions
- Drag-and-drop workflow builders, no-code platforms, and prompt-chain orchestration libraries do not create agents. These are procedural rule pipelines with an LLM as a text-completion node.
- Agency cannot be engineered by stacking procedural logic (rule trees, node graphs, chained prompts). Intelligence is learned, not coded.

#AIagents #machinelearning #neuralnetworks #LLM #reinforcementlearning

---

*Source: [shareAI-lab/learn-claude-code](https://github.com/shareAI-lab/learn-claude-code)*
