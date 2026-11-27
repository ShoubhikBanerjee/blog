---
title: "Laminar Enables Scalable Asynchronous RL Post-Training for LLMs"
slug: "laminar-enables-scalable-asynchronous-rl-post-training-for-llms"
description: "Laminar is a scalable reinforcement learning post‑training framework that enables large language models and long‑horizon agents to be fine‑tuned at scale."
date: 2026-11-27T22:09:22+05:30
tags: [Laminar, ReinforcementLearning, LargeLanguageModels, OpenSource]
categories: ["AI", "Machine Learning", "AI Agents", "Distributed Systems", "Open Source Software"]
image: "https://avatars.githubusercontent.com/u/212961691?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Laminar Enables Scalable Asynchronous RL Post-Training for LLMs

Laminar is a scalable reinforcement learning post‑training framework that enables large language models and long‑horizon agents to be fine‑tuned at scale.

## 🔍 Overview
- Built on **verl** and **Uni-Agent**.
- Open‑source implementation of *Laminar: A Scalable Asynchronous RL Post‑Training Framework* (EuroSys ’26).
- Decoupled, asynchronous, and fault‑tolerant design for large‑cluster scaling.

## 🧩 How it Works
- **Fully decoupled training and rollout**: independent loops via data and weight planes.
- **Data plane (`ExperienceBuffer`)** buffers completed trajectories for `AsyncRLTrainer`.
- **Weight plane (`Relay`)** stages published weights for inference replicas to pull on demand.
- **Trajectory‑level asynchrony**: generates and consumes individual trajectories independently.
- **Version‑mixed partial rollout**: interrupts in‑flight generations on weight sync and continues with newer weights.
- **Version‑consistent rollout**: keeps each trajectory on a single model version.
- **Dynamic repack**: consolidates long‑tail trajectories onto fewer replicas, freeing drained replicas to pull the latest weights.
- **Concurrent multi‑checkpoint evaluation (`laminar.eval`)**: version‑pinned routing and tail repacking for bubble‑free offline batch and online streaming evaluation.
- **Fault‑tolerant execution**: prevents single‑replica failures from stalling cluster‑wide progress.
- **Inference engines** recover failed replicas from `Relay` or checkpoint storage while preserving in‑flight trajectory prefixes.
- **Trainer engine** resumes from the latest checkpoint (asynchronous per‑step checkpoint in progress).

## ⚙️ Key Details
- **Extras**
```text
--extra vllm   vLLM rollout and evaluation backend
--extra megatron   Megatron‑LM training backend
--extra fsdp   FSDP2 training backend
--extra ucx   UCX transport for Relay (recommended)
```

## 🚀 Availability
- Open‑source on GitHub (built on verl and Uni-Agent).
- Manages Python, CUDA, wheel indexes, and pinned Git dependencies with `uv` (see `pyproject.toml` and `uv.lock`).

## 💡 Why it Matters
- In SWE agent training (Qwen3‑Coder‑30B‑A3B‑Instruct on SWE‑rebench, evaluated on SWE‑bench Verified on 64×H800) it improved resolve rate from **46.6 %** to **52.2 %**, surpassing the baseline peak of **51.4 %**.
- Uses **33 % fewer** trained samples and **64 % fewer** GPU‑hours to exceed the baseline peak.

#Laminar #ReinforcementLearning #LargeLanguageModels #OpenSource

---

*Source: [verl-project/laminar](https://github.com/verl-project/laminar)*
