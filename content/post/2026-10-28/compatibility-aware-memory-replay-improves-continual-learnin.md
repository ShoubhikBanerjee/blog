---
title: "Compatibility-Aware Memory Replay Improves Continual Learning in Large Language Models"
slug: "compatibility-aware-memory-replay-improves-continual-learning-in-large-language-models"
description: "We propose Compatibility-Aware Memory Replay (CAMR), an adaptive framework that jointly controls current-example supervision and historical replay."
date: 2026-10-28T18:02:11+05:30
tags: [ContinualLearning, MemoryReplay, AIResearch]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# Compatibility-Aware Memory Replay Improves Continual Learning in Large Language Models

We propose Compatibility-Aware Memory Replay (CAMR), an adaptive framework that jointly controls current-example supervision and historical replay.
CAMR combines compatibility checks with a learned memory gate to guide an online policy over three actions: learning incoming examples with general replay, jointly reinforcing compatible related examples, and skipping direct supervision of verified mastered duplicates.

## 🔍 Overview
- Continual learning requires large language models to acquire new knowledge and capabilities while retaining what they have learned.
- Fine-tuning and replay support acquisition and retention, but deciding whether incoming examples need supervision and which historical examples to revisit remains a challenge.

## 🧩 How it works
- CAMR combines compatibility checks with a learned memory gate to guide an online policy over three actions: learning incoming examples with general replay, jointly reinforcing compatible related examples, and skipping direct supervision of verified mastered duplicates.
- The policy learns from acquisition, retention, and training-cost feedback under a bounded per-arrival replay budget.

## ⚙️ Evaluation
- We evaluate CAMR with Qwen3-8B-Base on continual factual updating and cross-task and cross-domain learning.
- On WikiBigEdit, CAMR consistently leads evaluated methods in Original Match from 3K to 100K facts, reaching 93.66% after just 3K facts and surpassing Full-history Replay (LoRA) after 100K facts.
- It also achieves the highest final scores on all four selected TRACE tasks and maintains or improve earlier-task performance relative to post-acquisition levels in a sequence spanning financial question answering, mathematical reasoning, code generation, and summarization.

## 🛠️ arXivLabs
- arXivLabs is a framework that allows collaborators to develop and share new arXiv features directly on our website.
- Both individuals and organizations that work with arXivLabs have embraced and accepted our values of openness, community, excellence, and user data privacy.
- arXiv is committed to these values and only works with partners that adhere to them.
- Have an idea for a project that will add value for arXiv's community?
- Learn more about arXivLabs.

#ContinualLearning #MemoryReplay #AIResearch

---

*Source: [CAMR: Compatibility-Aware Memory Replay for Continual Learning in Large Language Models](https://arxiv.org/abs/2610.36734v1)*
