---
title: "AIDE ML open-sources tree-search agent for autonomous machine learning"
slug: "aide-ml-open-sources-tree-search-agent-for-autonomous-machine-learning"
description: "AIDE ML, the open-source “reference build” of the AIDE algorithm, has been released as a research-friendly Python package. The tool functions as a tree-search agent that autonomously drafts, debugs,..."
date: 2026-11-22T06:08:21+05:30
tags: [AIDEML, MachineLearning, AIagents, OpenSource, CodeGeneration]
categories: ["AI", "Machine Learning", "AI Agents", "Software Engineering", "Reinforcement Learning"]
image: "https://avatars.githubusercontent.com/u/132215366?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# AIDE ML open-sources tree-search agent for autonomous machine learning

AIDE ML, the open-source “reference build” of the AIDE algorithm, has been released as a research-friendly Python package. The tool functions as a tree-search agent that autonomously drafts, debugs, and benchmarks code until a user-defined metric is maximised or minimised.

## 🔍 Overview
AIDE ML ships with batteries-included utilities, including a CLI, visualisation tools, and config presets, designed for academics and engineer-researchers to replicate the paper, test new ideas, or prototype ML pipelines. The implementation is described as lean, specifically for experimentation and extension.

## 🧩 How it works
The agent operates by turning each Python script into a node within a solution tree. LLM-generated patches spawn child nodes, while metric feedback prunes and guides the search. Users point the agent at a dataset and describe the goal and metric in plain English, eliminating the need for YAML grids or bespoke wrappers.

## ⚙️ Key details
- **Model-neutral plumbing**: Supports OpenAI, Anthropic, Gemini, or any local LLM that speaks the OpenAI API.
- **Visualisation**: An HTML visualiser allows users to inspect the full solution tree and attached code; a Streamlit UI is available for prototyping.
- **Benchmark Performance**: In OpenAI’s MLE-Bench (75 Kaggle competitions), AIDE’s tree-search approach won 4 times more medals than the best linear agent (OpenHands).
- **Related Research**: The tool sits within a broader context of ML agent evaluations, including METR RE-Bench, Sakana AI's The AI Scientist-v2, and Meta’s Automated LLM Speedrunning Benchmark.

## 🚀 Availability
Installation is available via `pip install aideml` (or `pip install -U aideml`). Users must export their API key (e.g., `export OPENAI_API_KEY=<your-key>`).

To use the web UI:
1. Clone the repository: `git clone https://github.com/WecoAI/aideml.git`
2. Install dependencies: `pip install -e .`
3. Run the UI: `streamlit run app.py`

In the sidebar, users paste their API key, upload data, set the Goal & Metric, and press "Run AIDE". The UI displays live logs, the solution tree, and the best code found.

## 💡 Why it matters
The package provides a standardised way to explore automated ML engineering. It aligns with the Gymnasium ecosystem, an open-source Python library by the Farama Foundation for reinforcement learning, which models environments as simple Python classes. While Gymnasium provides the environment standards (including Classic Control, Box2D, MuJoCo, and Atari environments), AIDE ML offers a higher-level agentic framework for optimising code against those metrics.

#AIDEML #MachineLearning #AIagents #OpenSource #CodeGeneration

---

*Source: [WecoAI/aideml](https://github.com/WecoAI/aideml)*
*Source: [Farama-Foundation/Gymnasium](https://github.com/Farama-Foundation/Gymnasium)*
