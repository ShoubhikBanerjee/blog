---
title: "Weight‑Space Programming: LLMs Read and Edit Neural Network Weights"
slug: "weightspace-programming-llms-read-and-edit-neural-network-weights"
description: "Yesterday’s hot paper *Sparks of Weight‑Space Programming: LLMs can natively read & write neural network weights* introduced a new capability called **Weight‑Space Programming**. The authors (Rikiya..."
date: 2026-11-04T12:02:19+05:30
tags: [WeightSpace, LLM, NeuralNetworks, AIResearch]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Neural Networks"]
author: "Shoubhik Banerjee"
draft: false
---

# Weight‑Space Programming: LLMs Read and Edit Neural Network Weights

Yesterday’s hot paper *Sparks of Weight‑Space Programming: LLMs can natively read & write neural network weights* introduced a new capability called **Weight‑Space Programming**. The authors (Rikiya Takehi, Jayden Teoh, Alex Zhang, Omar Khattab) showed that frontier language models can interpret and directly modify raw model weights.

## 🔍 Overview
- GPT‑6 Astra can look at a network’s raw floating‑point weight list and infer the task the network was trained for.
- Without any environment feedback, Astra can also *write* new small game‑playing networks that outperform PPO‑trained networks after 100 million steps.
- Astra edited only 0.016 % of the weights of Qwen3.5‑0.8B to fix a reasoning‑loop issue identified in the model card, raising MATH‑500 from 7.9 % to 48.1 % and tripling IFEval performance.
- All weight modifications were performed without granting the model the ability to write training loops.

## 🧩 How it works
- The model receives a **text description of a neural network** containing its floating‑point weights.
- Using its internal reasoning, the model can:
  1. Identify the purpose of the network (e.g., a game‑playing agent).
  2. Detect problematic weight patterns (as with Qwen3.5‑0.8B’s math loops).
  3. Generate corrected weight values and replace them directly in the text.
- The process is called **Weight‑Space Programming** by the authors.

## ⚙️ Key results
- **Game‑playing networks** created by Astra beat PPO‑trained agents that had been trained for 100 million steps.
- **Math improvement** on Qwen3.5‑0.8B:
  - MATH‑500 accuracy: 7.9 % → 48.1 %.
  - IFEval score: increased threefold.
- No gradient‑based training or external feedback was required.

## 🎮 Experiments
The paper trained four neural networks for simplified 10×10 grid versions of classic Atari games:
- Breakout
- Pong
- Pac‑Man (gridworld variant)
- Freeway

The accompanying GitHub repository (**RikiyaT/lm_understand-logs**) contains the prompts and weight files in the `exp1_which_game` folder. The prompts are self‑contained.

### Model reasoning examples (run on a laptop)
| Model | Game identified | Reasoning time | Tokens used | Confidence |
|-------|----------------|----------------|------------|------------|
| Kimi K3.1 Pro | Breakout | 9 m 41 s | 19,493 | — |
| Qwen 3.8 27B (LM Studio) | Pac‑Man‑style gridworld | 46 m 12 s | 43,506 | 72 % |
| Qwen 3.8 27B (LM Studio) | Pong | 1 h 4 m 54 s | — | 75 % |
| Qwen 3.8 27B (LM Studio) | Breakout | 52 m 25 s | — | — |

> *“That’s still my favorite model to run on my own laptop—it’s just 17 GB … and somehow feels close to the leading proprietary models of 2025.”* – user observation about Kimi K3.1 Pro.

## 🗣️ Community response
- spaCy author **Matthew Honnibal** called the paper misleading for conflating reading and writing capabilities.
- **Sean Goedecke** argued that the Qwen3.5‑0.8B weight‑editing example mirrors the steps a human ML researcher would take.

## 📦 Availability
- Paper (classified as a “blog post” but paper‑shaped) is publicly referenced.
- Code and data are hosted at **github.com/RikiyaT/lm_understand-logs**.
- The `exp1_which_game` folder contains the exact prompts used in the experiments.


#WeightSpace #LLM #NeuralNetworks #AIResearch

---

*Source: [Qwen 3.8 27B on my laptop can interpret model weights, too](https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/)*
