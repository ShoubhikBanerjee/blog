---
title: "Matryoshka Attribution Learns to Attribute LLM Outputs to Representations and Weights"
slug: "matryoshka-attribution-learns-to-attribute-llm-outputs-to-representations-and-weights"
description: "Researchers have introduced Matryoshka Attribution (MAttr), a mask learning method designed to attribute large language model (LLM) outputs to specific internal components by identifying nested..."
date: 2026-09-23T18:02:56+05:30
tags: [LLM, MechanisticInterpretability, MachineLearning, Llama31]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# Matryoshka Attribution Learns to Attribute LLM Outputs to Representations and Weights

Researchers have introduced Matryoshka Attribution (MAttr), a mask learning method designed to attribute large language model (LLM) outputs to specific internal components by identifying nested subsets that minimize downstream loss.

## 🧩 How it works

* **Mask Learning:** MAttr uses a differentiable sigmoid top-$k$ operator to parameterize the mask.
* **Training Process:** The method supervises training across all sparsities simultaneously by randomizing $k$ during training, which creates a learned ordering of components based on their attribution score.
* **Objective:** It frames attribution as a learnable objective that can be addressed using gradient descent.

## ⚙️ Key details

* **Benchmark Performance:** MAttr achieved the number 1 position on the official Mechanistic Interpretability Benchmark (Mueller et al., 2025).
* **Capabilities:** The method identifies sparse and task-transferrable circuits across varying circuit bases.
* **RL Application:** MAttr can be trained with reinforcement learning to identify weight changes responsible for downstream behaviors during LLM finetuning.

## 💡 Why it matters

Existing attribution methods using gradients, causal interventions, or learnable masks are often infeasibly expensive or struggle to identify causally-important internal computations. MAttr provides a practical application for interpretability, as demonstrated by the following:

* **Refusal Removal:** When trained on refusal judge scores, restoring 1% of Llama 3.1 8B Instruct's weights to their base model state was sufficient to remove refusals while maintaining capabilities.

#LLM #MechanisticInterpretability #MachineLearning #Llama3.1

---

*Source: [Terminal Shrinkage Averaging Reveals a Schedule-Estimator Interaction in LLM Pretraining](https://arxiv.org/abs/2609.25482v1)*
*Source: [LatentPort: Beyond KV Cache - Cross-Model Transfer of Recurrent Memory in Hybrid Language Models: A 4B-to-9B Hybrid-State Handoff Without Target Prefix Replay](https://arxiv.org/abs/2609.25053v1)*
*Source: [Matryoshka attribution: Learning to attribute language model outputs to representations and weights](https://arxiv.org/abs/2609.25518v1)*
*Source: [Compressing Long Context into Answer-Aligned Memory Embeddings for LLM Inference](https://arxiv.org/abs/2609.25537v1)*
