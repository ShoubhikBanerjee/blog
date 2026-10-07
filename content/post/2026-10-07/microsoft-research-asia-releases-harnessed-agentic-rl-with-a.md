---
title: "Microsoft Research Asia releases Harnessed Agentic RL with Agent Lightning v1.0"
slug: "microsoft-research-asia-releases-harnessed-agentic-rl-with-agent-lightning-v1-0"
description: "Microsoft Research Asia introduced the Harnessed Agentic RL training paradigm and open‑sourced Agent Lightning v1.0, a lightweight framework that lets the same agent harness used in deployment..."
date: 2026-10-07T22:09:50+05:30
tags: [AIagents, ReinforcementLearning, Kubernetes, OpenSource]
categories: ["AI", "Machine Learning", "AI Agents", "Reinforcement Learning", "Systems"]
image: "https://www.microsoft.com/en-us/research/wp-content/uploads/2026/10/AgentLightning-TWLIFB-1200x627-1.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft Research Asia releases Harnessed Agentic RL with Agent Lightning v1.0

Microsoft Research Asia introduced the Harnessed Agentic RL training paradigm and open‑sourced Agent Lightning v1.0, a lightweight framework that lets the same agent harness used in deployment participate directly in reinforcement learning.

## 🔍 Overview
- Harnessed Agentic RL removes the need to reimplement the agent inside the training framework.
- Agent Lightning v1.0 provides a complete agent RL control plane in roughly **3,500 lines of code**.
- The framework runs agents as standard **Kubernetes jobs** on self‑managed clusters, cloud Kubernetes, or local infrastructure, without reliance on paid commercial sandbox services.

## 🧩 How it works
- The agent continues to call the model through an **LLM proxy**; the training system only observes the request‑response pairs.
- The **agent harness** that coordinates the deployed agent also handles the environment interaction loop during training.
- Because only LLM calls are recorded, a single rollout can be split into a variable number of training samples.
- Retokenization is required to obtain token IDs; re‑tokenizing text can shift token boundaries, so adjacent calls may not be merged into one sample.

## ⚙️ Key details
- **Lightweight design** – the entire codebase is about **3,500 lines**, making it easy to understand, modify, and extend.
- **Native Kubernetes support** – agents run directly as Kubernetes jobs, supporting self‑managed, cloud, and local clusters.
- **Data‑efficient training recipe** – an end‑to‑end coding‑agent pipeline raised **Qwen3.5‑9B** from **41.8 %** to **56.4 % Pass@1** on **SWE‑bench Verified**, a **14.6 percentage‑point** gain using only **≈6,000** training samples from an open‑sourced dataset.
- **Traditional vs. harnessed RL** – conventional agentic RL assumes the training framework owns the interaction loop, requiring developers to rebuild the agent’s context management, tool protocols, and execution logic inside the RL framework. This rebuilding is costly and can produce a training agent that differs from the deployed agent.

## 📊 Early systems and agents
| Name | Role |
|------|------|
| verl | Early RL system built with training framework owning the loop |
| AReaL | Early RL system built with training framework owning the loop |
| slime | Early RL system built with training framework owning the loop |
| mini‑SWE‑agent | Coding agent with its own context management, tool protocols, and execution logic |
| OpenHands | Coding agent with its own context management, tool protocols, and execution logic |
| OpenCode | Coding agent with its own context management, tool protocols, and execution logic |
| Claude Code | Coding agent with its own context management, tool protocols, and execution logic |
| Codex | Coding agent with its own context management, tool protocols, and execution logic |

## 🚀 Availability
- The researchers released **Agent Lightning v1.0** as an open‑source project.
- v1.0 emphasizes staying lightweight, integrating with real harnesses, and providing a reproducible agent RL training pipeline.
- By pointing the endpoint that previously called the model API at Agent Lightning, developers can train using the same harness that will be deployed.

## 💡 Why it matters
- AI agents now consist of complex full‑stack systems; their capabilities increasingly depend on the **agent harness** that coordinates them from outside the model.
- Harnessed Agentic RL aligns the training environment with the deployment environment, eliminating the mismatch that arises when agents are rebuilt for training.
- The data‑efficient results demonstrate that strong performance gains are achievable with modest training data when the correct harness is used.

![figure](https://uhf.microsoft.com/images/microsoft/RE1Mu3b.png)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/AgentLightning-blog_EXT_FA_figure.1.jpg)

#AIagents #ReinforcementLearning #Kubernetes #OpenSource

---

*Source: [Agent Lightning: Lightweight RL agent-training framework](https://www.microsoft.com/en-us/research/blog/agent-lightning-v1-0-a-3500-line-lightweight-agentic-rl-framework-for-training-agents-with-real-harnesses/)*
