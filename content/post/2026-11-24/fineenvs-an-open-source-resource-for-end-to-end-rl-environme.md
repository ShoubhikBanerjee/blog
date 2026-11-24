---
title: "FineEnvs: An Open-Source Resource for End-to-End RL Environments"
slug: "fineenvs-an-open-source-resource-for-end-to-end-rl-environments"
description: "A new open-source resource called FineEnvs has been released to address the shifting bottleneck in reinforcement learning (RL) for LLMs, where the environment design now poses a greater challenge..."
date: 2026-11-24T18:09:57+05:30
tags: [FineEnvs, ReinforcementLearning, OpenSource, LLMTraining, HuggingFace]
categories: ["AI", "Reinforcement Learning", "Machine Learning", "Open Source Software", "Large Language Models"]
image: "https://avatars.githubusercontent.com/u/27956426?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# FineEnvs: An Open-Source Resource for End-to-End RL Environments

A new open-source resource called FineEnvs has been released to address the shifting bottleneck in reinforcement learning (RL) for LLMs, where the environment design now poses a greater challenge than the algorithm. The project provides an end-to-end, reproducible, and open-source framework for designing, building, deploying, training against, and scaling RL environments to thousands of concurrent sessions.

## 🧩 How it works
The ecosystem is built on real, executable code rather than diagrams or unverified examples. Key characteristics of the resource include:
- **Reproducible Training:** Every rollout has been executed, and every training curve comes from a job that users can launch in a single command without requiring their own GPU.
- **Comprehensive Coverage:** The resource covers how to design an environment, how to build it, how to deploy it, how to train against it, and how to scale it to thousands of concurrent sessions.
- **Framework Agnosticism:** The environments are compatible with six different frameworks, allowing users to train using SETA, native OpenCode, or Harbor, utilizing HF Jobs or Slurm.
- **Verified SFT Traces:** Includes data-analysis tasks with verified SFT traces and a single-turn GRPO tutorial on HF Jobs.

## ⚙️ Key details
The release features three distinct environments demonstrated across six frameworks side by side. These environments utilize specific models and reward mechanisms:

| Environment / Task | Description | Model / Reward Mechanism |
| :--- | :--- | :--- |
| Math Image OCR | Train models to read math images into LaTeX | Qwen3-VL-2B with a verifiable reward |
| Watercolour Painting | Train models to paint watercolours by writing p5.brush sketches | Qwen3.5-35B-A3B rewarded by an aesthetic preference model |
| VLM Navigation | Drop a VLM at a random street corner on Earth | Scored on kilometres of error |
| Document OCR & ASR | OCR over a million pages in 22 languages and speech recognition over 102 | Behind one OpenEnv server; Gemma 4 trained to read and hear Kannada |
| Port Logistics | Re-plan a broken week of container-ship dockings at the Port of Barcelona | Graded against a proven optimum; simulates live news, pilots, tugs, and real wind |
| JetBlue Operations | Run JetBlue through a real storm day | Two desks talk, then three with the passengers on board |
| Lean 4 Proofs | OpenAI's Comparator challenges as Harbor tasks | Prove a research result in Lean 4, graded by Comparator in a separate sandbox |
| Math Proofs | Write a natural-language proof of an olympiad problem | LLM judge grades it 0–7 against the problem's rubric (QED-Nano recipe) |
| 24 Game | Make the target from every card using + − × ÷ | Variants include the current year from eight cards and any four-digit number from nine |

## 🚀 Availability
The resource is accessible through the following locations:
- **Source, recipes, and notebooks:** Available in the project repository.
- **Environments, datasets, models, and demos:** Hosted at huggingface.co/FineEnvs.
- **Training Infrastructure:** Supports execution via HF Jobs or Slurm.

#FineEnvs #ReinforcementLearning #OpenSource #LLMTraining #HuggingFace

---

*Source: [adithya-s-k/FineEnvs](https://github.com/adithya-s-k/FineEnvs)*
