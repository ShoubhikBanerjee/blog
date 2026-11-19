---
title: "RadixArk Releases DaisyRose-27B Model With RL Training on Long-Horizon Agent Tasks"
slug: "radixark-releases-daisyrose-27b-model-with-rl-training-on-long-horizon-agent-tasks"
description: "RadixArk has released DaisyRose-27B, its first model, built on Qwen3.8-27B and trained with reinforcement learning using the Miles framework. The model was trained on 1,200 curated long-horizon agent..."
date: 2026-11-19T18:06:46+05:30
tags: [RadixArk, DaisyRose, ReinforcementLearning, AIAgents, OpenSource, LLM]
categories: ["AI", "Machine Learning", "AI Agents", "Large Language Models", "Reinforcement Learning"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6aeabf9f2efd990530425e58/faP4Su889q_DIgN3wmU9M.png"
author: "Shoubhik Banerjee"
draft: false
---

# RadixArk Releases DaisyRose-27B Model With RL Training on Long-Horizon Agent Tasks

RadixArk has released DaisyRose-27B, its first model, built on Qwen3.8-27B and trained with reinforcement learning using the Miles framework. The model was trained on 1,200 curated long-horizon agent tasks over 18 days on 144 H200 GPUs, achieving a Terminal-Bench 4.1 pass@1 improvement from 5.6% to 12.0%.

## 🔍 Overview
- First model release from RadixArk
- Base: Qwen3.8-27B
- Training method: Reinforcement learning via Miles (open-source RL framework)
- Training scale: 1,200 tasks, sessions up to 1M tokens, 18 days, 144 H200 GPUs
- License: Apache 2.0 checkpoints available

## 🧩 How It Works
### Task Design
- Tasks built in partnership with Eigent AI from a large pool covering machine learning, software engineering, science, and other fields
- Thousands of candidates filtered to ~1,200 final tasks using three criteria:
  - Each task targets a mistake the original Qwen3.8-27B makes
  - Tasks redesigned around those mistakes, difficulty adjusted until solve rate falls in a useful learning range
  - Each task requires several interdependent steps: the agent must reason, plan, and execute across a long job
- Each attempt runs up to 1.5 hours in a sandbox with >100 tool calls and >256K output tokens
- Tasks must reward actually solving the problem; every task reviewed alongside model attempts; flawed tasks fixed or removed

### Training Backend (Miles)
- Fully asynchronous mode: agent keeps working while model learns, neither waits for the other
- 128 H200s run inference on agent tasks; 16 H200s run the trainer
- After each step, updated model deployed to the 128 inference GPUs
- Internal training backend built for agent training: each step learns from a handful of very long sessions (up to 1M tokens) folded into multiple trajectories via harness summarization

### Sandbox Service
- Built on open-source AgentENV project (RadixArk contributes fixes)
- Mid-September to mid-November: ~944,000 sandboxes run, up to 1,566 concurrent
- Service scaled from 1 to 12 machines
- 10 upgrades shipped, nearly all while training was running
- 99% sandbox creation success across 9 weeks; >99.95% since late October

## ⚙️ Key Details
### Benchmark Results
| Benchmark | Qwen3.8-27B | DaisyRose-27B |
|---|---|---|
| Terminal-Bench 4.1 pass@1 | 5.6% | 12.0% |
- DaisyRose-27B scores higher than original Qwen3.8-27B on every benchmark evaluated
- Largest gain on Terminal-Bench 4.1 (5.6% → 12.0%)
- Gains also on reasoning, instruction following, and coding benchmarks
- Scores use higher of BF16 and FP8 runs; difference <1 point where both evaluated

### Model Architecture
- Retains Qwen3.8-27B architecture, tokenizer, chat template, image understanding, and 256K-token context window
- Longer training sessions use harness summarization to span multiple trajectories
- Model thinks before answering by default; reasoning returned in `reasoning_content`, final answer in `content`

### Training Efficiency
| Metric | RadixArk Backend | Open-Source Trainer (Megatron) |
|---|---|---|
| Model FLOPs Utilization (MFU) | 37% | 16% |
| Training cost reduction | 57% less GPU time | baseline |
| Throughput (tokens/sec across 144 GPUs) | ~16,800 | ~8,300 |
| End-to-end speed | 2× faster | baseline |
- Stability: 63,000 GPU-hours over weeks; speed and efficiency held steady from first to last step
- Larger gains on mixture-of-experts models: 6.2× on Qwen3.6-35B-A3B, >10× on ~300B GLM-5.3-Flash

## 🚀 Availability
- Checkpoints released under Apache 2.0
- Recommended serving: SGLang with DSpark speculative decoding
- SGLang cookbook provides launch configurations for different GPUs and checkpoint formats
- Quickstart: start server with served model name `DaisyRose-27B` on port 30000, then send requests via OpenAI Python client

## 💡 Why It Matters
- Demonstrates that carefully designed long-horizon agent tasks, an efficient asynchronous RL backend, and a robust sandbox service can jointly deliver large benchmark gains with substantially lower compute cost
- 57% less GPU time for equivalent training via higher MFU (37% vs 16%)
- 2× end-to-end throughput improvement
- Sandbox infrastructure proved reliable at scale (99.95% success rate) with live upgrades during training
- Gains generalize across benchmark categories and are especially pronounced on mixture-of-experts architectures

![figure](https://www.radixark.com/images/daisyrose-27b/benchmarks.png)

![figure](https://www.radixark.com/images/daisyrose-27b/gpu-efficiency.png)

![figure](https://www.radixark.com/images/daisyrose-27b/training-stability.png)

#RadixArk #DaisyRose #ReinforcementLearning #AIAgents #OpenSource #LLM

---

*Source: [DaisyRose-27B: Pushing the Frontier of Post-Training Efficiency](https://huggingface.co/blog/RadixArk/daisyrose-27b-pushing-the-frontier-of-post-trainin)*
