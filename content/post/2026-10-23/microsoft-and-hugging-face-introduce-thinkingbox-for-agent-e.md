---
title: "Microsoft and Hugging Face Introduce ThinkingBox for Agent Evaluation and Training"
slug: "microsoft-and-hugging-face-introduce-thinkingbox-for-agent-evaluation-and-training"
description: "Microsoft and Hugging Face have jointly developed ThinkingBox, a system designed to evaluate AI agents by comparing final database states with expected outcomes, and ThinkingBox-Training to improve..."
date: 2026-10-23T12:04:45+05:30
tags: [AIagents, RLHF, Qwen, Microsoft, HuggingFace]
categories: ["AI", "Machine Learning", "AI Agents", "Software Evaluation"]
image: "https://cdn-uploads.huggingface.co/production/uploads/64b8491203124195cd795cad/oS8I8qx7iBS8EcNIXR3q9.png"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft and Hugging Face Introduce ThinkingBox for Agent Evaluation and Training

Microsoft and Hugging Face have jointly developed ThinkingBox, a system designed to evaluate AI agents by comparing final database states with expected outcomes, and ThinkingBox-Training to improve agent performance via reinforcement learning.

## 🔍 Overview
ThinkingBox-Bench is a benchmark dataset consisting of 507 tasks. Each task provides an agent with a real backend, a set of MCP tools, and a simulated LLM user with private context. The system grades agents based on the database records left behind rather than the specific tool calls used.

## 🧩 How it works
* **Executable Checks:** For most tasks, an executable check returns a 1 or 0 directly from the terminal database state.
* **Reward System:** ThinkingBox converts these executable checks into rewards for post-training agents on tasks outside the benchmark.
* **Offline Policy-Relative Difficulty:** This method estimates a task's success probability using the base policy before training. A task is considered hard for the current model until the model learns it; this selected training pool remains fixed during the run.

## ⚙️ Key details
Researchers used a training pool of ThinkingBox-format tasks outside the benchmark to fine-tune Qwen3.8-27B using GRPO for 50 steps. This model was then evaluated on the 507-task benchmark, which served as an out-of-distribution test set.

**Qwen3.8-27B Performance Results:**

| Metric | Before Training | After Training |
| :--- | :--- | :--- |
| pass@1 (Average Success) | 51.70% (5,242 attempts) | 60.78% (6,163 attempts) |
| Observed 20/20 (Repeatable Success) | 7.50% (38 tasks) | 21.10% (107 tasks) |
| pass@20 (Solved at least once) | 89.35% (453 tasks) | 87.97% (446 tasks) |

**Other Model Observations:**
* **Kimi-K3:** Solved 93.89% of tasks at least once, but completed only 13.41% (68 of 507) on all twenty attempts.
* **Claude Opus 5.5:** Scored 0.66 percentage points higher than Claude Opus 5 on pass@1, but both passed exactly 241 tasks on all twenty attempts.

## 💡 Why it matters
ThinkingBox identifies discrepancies where an agent may appear competent but fails the final state. For example, a model once closed a customer ticket as resolved while the underlying carrier exception remained open, resulting in nine competent-looking tool calls but one wrong database row. In another case involving a room downgrade request requiring manager approval, the agent failed in 15 of 20 attempts before training; after RL fine-tuning, it preserved the booking and payment state in all 20 attempts and matched all expected records in 19.

## 🚀 Availability
ThinkingBox-Training is now available on GitHub.

#AIagents #RLHF #Qwen #Microsoft #HuggingFace

---

*Source: [Turning Database Grading into RL Rewards: Post-Training Agents with ThinkingBox](https://huggingface.co/blog/microsoft/thinkingbox-training)*
