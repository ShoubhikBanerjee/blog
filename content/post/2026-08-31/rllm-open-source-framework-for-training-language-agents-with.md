---
title: "rLLM Open-Source Framework for Training Language Agents with Reinforcement Learning"
description: "rLLM is a new open-source framework designed for training language agents using reinforcement learning. It allows developers to use the same agent code for both evaluation and training by utilizing a..."
date: 2026-08-31T18:32:11+05:30
tags: [rLLM, ReinforcementLearning, AIAgents, OpenSource]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/221438497?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# rLLM Open-Source Framework for Training Language Agents with Reinforcement Learning

rLLM is a new open-source framework designed for training language agents using reinforcement learning. It allows developers to use the same agent code for both evaluation and training by utilizing a model gateway that captures token IDs and logprobs.

## 🔍 Overview

rLLM provides a flexible environment for agent development and training with the following features:
* **Harness Support:** Includes 10+ CLI harnesses (such as Claude Code, Codex, Terminus-2, mini-swe-agent, and opencode) and Harbor-compatible task directories.
* **Agent Integration:** Users can wrap their own agents, including those built with LangGraph, OpenAI Agents SDK, or `openai.OpenAI`, using `@rllm.rollout`.
* **Extensive Benchmarking:** Integrates 60+ benchmarks across categories including math, code, MCQ, QA, search, VLM, translation, and agentic tasks (e.g., Terminal-Bench 2.0, SWE-bench, SkillsBench, AIME, MATH-500, and GPQA).
* **Simplified Evaluation:** The `rllm eval <name>` command automatically pulls and runs benchmarks.

## 🧩 How it works

rLLM follows a pipeline: **run your agent → collect traces → compute rewards → update the model**. 

During this process, the agent runs as-is. A model gateway captures LLM calls via URL-routed sessions and organizes them into a specific structure:
* **Episodes:** One task
* **Trajectories:** One agent run
* **Steps:** One LLM call

A reward function then scores the result, and an RL algorithm updates the model weights.

## ⚙️ Key details

### Training Backends

| Backend | Description |
| :--- | :--- |
| `verl` | Distributed multi-GPU training (with vLLM/SGLang) |
| `tinker` | Single-machine training (Tinker API) |
| `fireworks` | Fireworks training platform |

### Technical Specifications
* **Supported Algorithms:** GRPO, REINFORCE, RLOO, SFT, and on-policy distillation.
* **Infrastructure:** Supports Docker, Daytona, Modal, or local environments, utilizing snapshot and warm-pool acceleration.
* **Requirements:** Python >= 3.11.
* **Proven Results:** State-of-the-art open-source results include DeepScaleR-1.5B, DeepCoder-14B, DeepSWE-32B, and FinQA-4B.

## 🚀 Availability

rLLM is open-source and has been adopted by industry research teams and academic labs.

#rLLM #ReinforcementLearning #AIAgents #OpenSource

---

*Source: [rllm-org/rllm](https://github.com/rllm-org/rllm)*
