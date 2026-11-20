---
title: "Hugging Face introduces RL-trained harness adapters for improved LLM efficiency"
slug: "hugging-face-introduces-rl-trained-harness-adapters-for-improved-llm-efficiency"
description: "Hugging Face has introduced 'harness adapters,' a method for adapting favorite models to specific agent harnesses using reinforcement learning (RL) to improve performance and cost efficiency. While..."
date: 2026-11-20T22:08:48+05:30
tags: [LLMs, ReinforcementLearning, LoRA, Agents, HuggingFace]
categories: ["AI", "Large Language Models", "Reinforcement Learning", "Software Engineering", "Model Optimization"]
image: "https://huggingface.co/blog/assets/harness-adapters-at-scale/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Hugging Face introduces RL-trained harness adapters for improved LLM efficiency

Hugging Face has introduced "harness adapters," a method for adapting favorite models to specific agent harnesses using reinforcement learning (RL) to improve performance and cost efficiency. While base models generally target general performance, combining a model with a specific harness often leaves performance and efficiency on the table for targeted tasks. By training custom adapters on specific task distributions, developers can squeeze more capability out of existing models for their specific use cases.

## 🧩 How it works
The technique involves combining RL on a custom task distribution with the user's favorite agent harness. This process yields more accurate and efficient models specifically for that target harness and task combination. The core mechanism is that models are not fully optimized for every harness and task; they are optimized for general performance. With RL, a custom harness adapter can be trained to optimize the model for the specific harness and task at hand.

In recent experiments, researchers froze the weights of the Qwen3.8-27B model and added a custom RL-trained LoRA adapter. This approach resulted in the model reasoning less, calling fewer tools, and performing better on the first attempt. 

| Model / Configuration | Terminal-Bench 2.1 Score | Avg Tokens per Task |
| :--- | :--- | :--- |
| Qwen3.8-27B (Base) | 39% | 2.9K |
| Qwen3.8-27B (with RL LoRA) | 55% | 1.5K |

## ⚙️ Key details
To validate this approach on harder real-world software engineering tasks, the team trained one LoRA adapter for Qwen3.8-27B for each of three agent harnesses: Pi, Hermes Agent, and OpenCode. The RL training occurred inside the harness itself. Datasets, training, and agent rollouts were managed on the Hub in Jobs using TRL's AsyncGRPOTrainer, OpenEnv, and harbor.

Key technical components of the recipe include:
*   **Super Adapter:** The three individual LoRAs were merged into a single "super adapter" that runs unchanged under all three harnesses.
*   **Docker Images:** Ready-to-use docker images for RL tasks are provided with target harnesses pre-installed. The final images use Pi 1.5.2, OpenCode 2.2.7, and Hermes Agent v0.22.6.
*   **Custom Dataset Pipeline:** A custom dataset for agentic coding was created using the Hub, OpenEnv, and Repo2RLEnv. This pipeline combines task retrieval from existing RL environments, task generation via Repo2RLEnv, and task validation with OpenEnv.
*   **Task Sources:** 
    *   *SWE-smith* injects bugs into real Python and Go repositories using LLM rewrites or mutations.
    *   *SWE-Gym* (packaged as Harbor tasks in TaskTrove) converts real GitHub issues and merged fixes into tasks.
    *   *Tasksmith* generates tasks from merged pull requests. In one instance, Tasksmith produced 24 valid tasks from 30 merged pull requests in 10 Python repositories.

Every task in the dataset passes an eligibility screen via `openenv validate` and a difficulty check against the base model. Each harness adapter beat the base model under its own harness on both performance and efficiency benchmarks.

## 🚀 Availability
All artifacts related to this work, including adapters, GGUFs, RL tasks, and the safeagents plugin, are browsable through a Hugging Face collection. A fully reusable recipe is shared so developers can reproduce these results on their own task, harness, and model combinations.

![figure](https://huggingface.co/buckets/huggingface/harness-adapters-blog-assets/resolve/images/task-pipeline.png)

#LLMs #ReinforcementLearning #LoRA #Agents #HuggingFace

---

*Source: [Introducing harness adapters: adapt your favorite model to your harness to improve performance and cost](https://huggingface.co/blog/harness-adapters-at-scale)*
