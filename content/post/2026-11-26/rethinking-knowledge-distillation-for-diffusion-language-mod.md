---
title: "Rethinking Knowledge Distillation for Diffusion Language Models and ViCARD for Visual Reasoning"
slug: "rethinking-knowledge-distillation-for-diffusion-language-models-and-vicard-for-visual-reasoning"
description: "Recent developments in AI research highlight two distinct studies addressing limitations in knowledge distillation and visual reasoning: an investigation into knowledge distillation for diffusion..."
date: 2026-11-26T12:19:42+05:30
tags: [KnowledgeDistillation, DiffusionModels, VisualReasoning, MachineLearning, ArtificialIntelligence]
categories: ["AI", "Machine Learning", "Computer Vision", "Natural Language Processing", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# Rethinking Knowledge Distillation for Diffusion Language Models and ViCARD for Visual Reasoning

Recent developments in AI research highlight two distinct studies addressing limitations in knowledge distillation and visual reasoning: an investigation into knowledge distillation for diffusion language models (DLMs) and the introduction of ViCARD for multimodal reasoning.

## 🔍 Overview of Knowledge Distillation for DLMs
* Knowledge distillation has proven effective for autoregressive models, but its applicability to DLMs remains poorly understood.
* A systematic study of knowledge distillation for DLMs uncovered two non-intuitive failures of classical forward-KL (FKL) distillation:
  * Student perplexity does not improve monotonically with more teacher-generated data.
  * On the same teacher-generated corpus, FKL distillation underperforms simply training the student with the original DLM denoising objective.
* A unified, data-free distillation framework for masked DLMs was proposed to address these issues, submitted on 25 Nov 2026.

## ⚙️ Key Details of the DLM Framework
* Off-policy distillation phase: Absorbs general knowledge from a static set of teacher-generated data.
* On-policy distillation phase: Consists of three techniques:
  * A trajectory loss along the student's own reverse process.
  * Confidence reweighting that down-weights tokens where the teacher is unsure.
  * A trust-region anchor that stabilizes the moving target.

## 🚀 Performance Highlights
* On MDLM, the resulting student attains a GPT-2 perplexity of $24.75$, surpassing the teacher's $27.04$.
* On Dream-7B distillation to a 93M student model, the framework reduces Qwen-2.5 perplexity from the FKL-distilled baseline of $25.23$ to $19.83$ while preserving performance on zero-shot general capability benchmarks.

## 🧩 ViCARD for Multimodal Reasoning
* Submitted on 24 Nov 2026, ViCARD (Visual Credit Assignment with RewardGated Distillation) integrates per-token visual supervision with verified correctness rewards.
* Outcome-based reinforcement learning (RL) in visual reasoning faces challenges including no learning signal when perceptual errors cause all sampled responses to fail, and broadcasting a uniform advantage across every token within a response.
* ViCARD mechanisms:
  * Leverages a teacher with its input image cropped to the relevant visual area to provide per-token supervision while valuing correctness.
  * If all sampled rollouts fail, ViCARD samples an additional crop-teacher answer and activates on-policy distillation only if that answer is correct.
  * Provides fine-grained visual credit within informative reward groups and a learning signal for otherwise uninformative all-fail groups.
* Extensive comparisons across model scales demonstrate that ViCARD improves fine-grained visual reasoning performance over RL and distillation baselines, while retaining broad visual reasoning capabilities.

#KnowledgeDistillation #DiffusionModels #VisualReasoning #MachineLearning #ArtificialIntelligence

---

*Source: [Rethinking Knowledge Distillation for Diffusion Language Models](https://arxiv.org/abs/2611.33670v1)*
*Source: [ViCARD: Visual Credit Assignment with Reward-Gated Distillation for Multimodal Reasoning](https://arxiv.org/abs/2611.33437v1)*
