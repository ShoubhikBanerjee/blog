---
title: "QDA Automates Quantization Recipe Design for Large Language Models"
slug: "qda-automates-quantization-recipe-design-for-large-language-models"
description: "Researchers have introduced QDA, a system that uses an LLM agent to automatically design post-training quantization recipes for large language models, reducing the need for manual expert tuning."
date: 2026-11-19T22:12:49+05:30
tags: [Quantization, LLM, AIAgents, ModelCompression, PostTrainingQuantization]
categories: ["AI", "Machine Learning", "AI Agents", "Model Optimization", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# QDA Automates Quantization Recipe Design for Large Language Models

Researchers have introduced QDA, a system that uses an LLM agent to automatically design post-training quantization recipes for large language models, reducing the need for manual expert tuning.

## 🔍 Overview
- Post-training quantization (PTQ) is the standard way to serve large language models at low cost.
- The optimal quantization recipe varies across models and precisions, requiring experts to redesign it for each new model—a time-consuming and often sub-optimal process.
- QDA automates this design by employing an LLM agent that iteratively refines quantization recipes over multiple rounds of building and evaluating candidates.

## 🧩 How it works
- The agent explores candidate recipes through rounds of building and evaluation; more rounds yield better recipes.
- To accelerate evaluation, QDA scores each candidate in minutes using output KL divergence from the original model on held-out reasoning traces, and validates promising candidates with long generations to detect failures such as repetition loops.
- To accelerate building, QDA provides a library of public PTQ methods that are mutually compatible and compatible with new model architectures.

## ⚙️ Key details
- Evaluated across four reasoning models, QDA improves accuracy over the strongest public recipe by:
  - 0.9 percentage points at W4A16
  - 1.4 percentage points at W4A8
  - 2.2 percentage points at W3A16
  - Using 64 GPU-hours per search.
- On the 320B-parameter MoE model GLM-5.3-Flash at NVFP4 W4A4, QDA recovers 98.3% of the FP8 model's accuracy, compared to 96.9% for the best vendor checkpoint.
- All QDA checkpoints run on existing serving kernels with no inference overhead.

## 🚀 Availability
- The library, evaluator, and harness will be released publicly.

## 💡 Why it matters
- Automating quantization recipe design reduces expert effort and improves compression accuracy across diverse models and precision settings.
- Faster evaluation and building enable practical deployment of quantized reasoning models at scale.

#Quantization #LLM #AIAgents #ModelCompression #PostTrainingQuantization

---

*Source: [QDA: Closed-Loop LLM Quantization Design with Agents](https://arxiv.org/abs/2611.23388v1)*
*Source: [MoMoVL: Modality-Aware Adaptive Compression for On-Device Sparsely-Activated Vision-Language Models](https://arxiv.org/abs/2611.23695v1)*
