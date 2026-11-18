---
title: "Xing 4 LLM Series Advances Architecture and Training on Ascend Hardware"
slug: "xing-4-llm-series-advances-architecture-and-training-on-ascend-hardware"
description: "A new report details Xing 4, a series of large language models extending the TeleChat lineage through coordinated advances in model architecture and training infrastructure on Ascend hardware. The..."
date: 2026-11-18T22:09:17+05:30
tags: [LLM, Ascend, TeleChat, MindSpore, AIAgents, DistributedTraining]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Large Language Models", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# Xing 4 LLM Series Advances Architecture and Training on Ascend Hardware

A new report details Xing 4, a series of large language models extending the TeleChat lineage through coordinated advances in model architecture and training infrastructure on Ascend hardware. The work spans architecture selection, large-scale pretraining, and reasoning and agentic post-training, culminating in a 285B-parameter model trained on 8,192 Ascend 910C cards.

## 🔍 Overview
- Xing 4 extends the TeleChat lineage with coordinated architecture and infrastructure advances
- Report covers architecture selection, large-scale pretraining, and reasoning and agentic post-training
- Establishes an Ascend-oriented training foundation for continued development across model scales

## 🧩 How it works
- Studies sparse activation, attention design, model depth and width, and speculative decoding to balance capacity with computation, memory access, and execution overhead
- Pretraining infrastructure builds on MindSpore HyperParallel with:
  - Topology-aware hybrid sharding
  - Efficient distributed optimizer execution
  - Coordinated management of long-sequence workloads and activation memory
- CPU affinity and core isolation reduce host scheduling interference
- Post-training introduces TeleGym, a unified agent execution platform connecting execution, evaluation, and trajectory construction to policy optimization
- TeleGym uses disaggregated asynchronous execution, bounded oversampling, and partial rollout to accommodate heterogeneous task durations while preserving trajectory continuity across policy updates

## ⚙️ Key details
- 285B-parameter model pretrained on 8,192 Ascend 910C cards
- Architecture studies cover sparse activation, attention design, model depth/width, speculative decoding
- Infrastructure: MindSpore HyperParallel with topology-aware hybrid sharding, distributed optimizer execution, long-sequence and activation memory management
- Post-training platform: TeleGym with disaggregated asynchronous execution, bounded oversampling, partial rollout
- Foundation supports continued development across model scales and demanding reasoning and agent workloads

## 💡 Why it matters
- Demonstrates end-to-end Ascend-oriented training pipeline from architecture to agentic post-training
- Provides concrete system configuration (285B parameters, 8,192 Ascend 910C cards) for architectural and systems studies
- TeleGym platform enables unified agent execution, evaluation, and policy optimization for reasoning workloads

#LLM #Ascend #TeleChat #MindSpore #AIAgents #DistributedTraining

---

*Source: [TeleChat to Xing4: Advancing Frontier Agentic Models on Domestic Chips and Frameworks](https://arxiv.org/abs/2611.22115v1)*
