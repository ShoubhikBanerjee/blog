---
title: "New benchmark automates failure attribution in LLM‑based multi‑agent systems"
slug: "new-benchmark-automates-failure-attribution-in-llmbased-multiagent-systems"
description: "A benchmark for automated failure attributions in agentic systems was presented as the ICML 2025 Spotlight paper *Which Agent Causes Task Failures and When?*."
date: 2026-10-31T12:02:07+05:30
tags: [AIAgents, LLM, Benchmark, Debugging]
categories: ["AI", "Machine Learning", "AI Agents", "Benchmarking", "Natural Language Processing"]
image: "https://avatars.githubusercontent.com/u/188122941?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New benchmark automates failure attribution in LLM‑based multi‑agent systems

A benchmark for automated failure attributions in agentic systems was presented as the ICML 2025 Spotlight paper *Which Agent Causes Task Failures and When?*.

## 🔍 Overview
- **The first and the best benchmark debugging failures from agentic trajectories.**
- Introduces the task of automated failure attribution in LLM‑based multi‑agent systems.
- Given a failed task, the goal failure attribution is to automatically identify the agent and step responsible for the failure.

## 🧩 How it works
The repository implements three failure‑attribution methods. Choose one with the `--method` flag:

| Method name | Description |
|------------|-------------|
| `all_at_once` | All-at-Once judging |
| `step_by_step` | Step‑Step judging |
| `binary_search` | Binary Search judging |

Example command:
```bash
python inference.py --method step_by_step --model gpt-4o --is_handcrafted False --directory_path ../Who&When/Algorithm-Generated
```

## ⚙️ Key details
- **184** annotated failure tasks collected from:
  - **Algorithm‑generated agentic systems** built using [CaptainAgent](https://docs.ag2.ai/latest/docs/use-cases/notebooks/notebooks/agentchat_captainagent/)
  - **Hand‑crafted systems** such as [Magnetic‑One](https://www.microsoft.com/en-us/research/articles/magentic-one-a-generalist-multi-agent-system-for-solving-complex-tasks/)
- The dataset covers a wide range of realistic multi‑agent scenarios based on queries from [GAIA](https://huggingface.co/gaia-benchmark) and [AssistantBench](https://assistantbench.github.io/).
- Access the dataset on [Hugging Face 🤗](https://huggingface.co/datasets/Kevin355/Who_and_When).
- Evaluation example:
```bash
python evaluate.py --data_path ../Who\&When/Algorithm-Generated --eval_file outputs/step_by_step_gpt-4o_alg_generated.txt
```
Results are stored in the `outputs` directory by default; more results are reported in the paper.

## 🚀 Availability
- Code repository provides the implementation of the ICML 2025 spotlight paper.
- Dataset is publicly downloadable from Hugging Face.
- Users must specify the `AutoFA` method (`--method`) and the dataset type (`--is_handcrafted`) before running inference.

## 💡 Why it matters
- **Reduces manual debugging effort:** Automates the labor‑intensive process of inspecting failure logs and tracing errors.
- **Accelerates system development:** Speeds up the iteration cycle by quickly identifying faulty agents and critical mistakes.
- **Enables intermediate feedback for agent self‑improvement:** Pinpointing decisive errors provides actionable signals for agentic systems' self‑correction or can serve as rewards in reinforcement learning.

If you find it useful, please consider citing the work.

#AIAgents #LLM #Benchmark #Debugging

---

*Source: [ag2ai/Agents_Failure_Attribution](https://github.com/ag2ai/Agents_Failure_Attribution)*
