---
title: "SWE-smith: Scalable Toolkit for Training Software Engineering Agents Debuts at NeurIPS 2025"
description: "Presented at NeurIPS 2025 in the Datasets & Benchmarks Track, SWE-smith is a new toolkit for training software engineering agents (SWE-agents). It enables the transformation of GitHub repositories..."
date: 2026-08-31T22:56:10+05:30
tags: [AI, softwareengineering, NeurIPS2025, datasets, benchmarking]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/139597579?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# SWE-smith: Scalable Toolkit for Training Software Engineering Agents Debuts at NeurIPS 2025

Presented at NeurIPS 2025 in the Datasets & Benchmarks Track, SWE-smith is a new toolkit for training software engineering agents (SWE-agents). It enables the transformation of GitHub repositories into SWE-gym environments and generates diverse tasks for agent training.

## 🔍 Overview
SWE-smith addresses the challenge of scaling data for software engineering agents. Key capabilities include:
- Converting any GitHub repository into a SWE-gym environment
- Generating unlimited tasks (e.g., file localization, program repair)
- Training language models to become proficient SWE-agents

## 🧩 How it works
The workflow involves three core steps:
1. **Environment creation**: Uses Docker to set up isolated execution environments (Ubuntu 22.04.4 LTS only; no Windows/macOS support)
2. **Task synthesis**: Generates task instances from repository code
3. **Task filtering**: Retains tasks that break one or more unit tests for meaningful training signals
4. **Issue generation**: Creates natural language issue descriptions for synthesized tasks

## ⚙️ Key details
- **Dataset**: 52k task instances across 250+ repositories ([Hugging Face link](https://huggingface.co/datasets/SWE-bench/SWE-smith))
- **Model**: SWE-agent-LM-32B (fine-tuned Qwen 2.5 Coder) achieved **40.2% pass@1** on SWE-bench Verified (+32% improvement)
- **Trajectories**: 26k agent trajectories available (5k used for SWE-agent-LM-32B training)
- **Environments**: 250+ Docker images ([GitHub repository](https://github.com/SWE-bench/SWE-smith-envs))

## 🚀 Availability
- Open-source under MIT license
- Python API example:
```python
from swesmith.profiles import registry
from datasets import load_dataset
ds = load_dataset("SWE-bench/SWE-smith", split="train")  # Loads 52k tasks
```
- Tutorials available at [swesmith.com/guides](https://swesmith.com/guides/)

## 💡 Why it matters
SWE-smith provides an unprecedented scale of diverse, executable tasks for training software engineering agents. Its SWE-agent-LM-32B demonstrates significant performance gains on standardized benchmarks, establishing a new baseline for the field. The toolkit's open infrastructure lowers barriers for research into code-capable AI systems.

#AI #softwareengineering #NeurIPS2025 #datasets #benchmarking

---

*Source: [SWE-bench/SWE-smith](https://github.com/SWE-bench/SWE-smith)*
