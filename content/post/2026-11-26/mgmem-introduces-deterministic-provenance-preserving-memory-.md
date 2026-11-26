---
title: "MGMem Introduces Deterministic, Provenance-Preserving Memory for Long-Horizon LLM Agents"
slug: "mgmem-introduces-deterministic-provenance-preserving-memory-for-long-horizon-llm-agents"
description: "Long-horizon Large Language Model (LLM) agents need persistent memory that surfaces the right past interaction at the right time across thousands of turns. Many existing systems rely on generative..."
date: 2026-11-26T12:19:42+05:30
tags: [LLM, Memory, AIAgents, NLP]
categories: ["AI", "Machine Learning", "AI Agents", "Natural Language Processing"]
author: "Shoubhik Banerjee"
draft: false
---

# MGMem Introduces Deterministic, Provenance-Preserving Memory for Long-Horizon LLM Agents

Long-horizon Large Language Model (LLM) agents need persistent memory that surfaces the right past interaction at the right time across thousands of turns. Many existing systems rely on generative indexing—rewriting history into summaries, facts, or knowledge graphs—which is costly, nondeterministic, and erases provenance.

## 🔍 Overview
- **Problem**: Generative indexing calls cost thousands of calls per build, produce inconsistent answers, and hide original dialogue turns.
- **Solution**: MGMem provides a deterministic, discriminative‑parser pipeline that eliminates generative indexing.

## 🧩 How it Works
- **Incidence Graph**: Recurring mentions across sessions are organized into an incidence graph.
- **Three‑Stage Resolver**: Question mentions are resolved by a subject‑conditioned three‑stage resolver.
- **Raw Dialogue Return**: The pipeline returns raw dialogue episodes to the reader, preserving provenance.

## ⚙️ Key Details
- **Determinism**: No generative indexing calls; the process is fully deterministic.
- **Efficiency**: Removes the need for thousands of generative calls.
- **Provenance**: Original turns are accessible, avoiding synthesized text.

## 🚀 Performance
- On English multi‑session dialogue QA, MGMem outperforms matched‑protocol baselines on **LoCoMo** without generative indexing calls.
- On the full **LongMemEval‑S**, MGMem remains competitive overall and leads or ties on single‑session types among local retrieval comparisons.

## 📦 Availability
- Code is provided via the referenced URL in the submission.

*Submitted on 21 Oct 2026; Computer Science > Computation and Language.*

#LLM #Memory #AIAgents #NLP

---

*Source: [Semantic Density Does Not Predict Agent-Memory Collapse](https://arxiv.org/abs/2611.33184v1)*
*Source: [Sequentially Acquiring Concept Knowledge to Guide Continual Learning](https://arxiv.org/abs/2611.33399v1)*
*Source: [MGMem: An Efficient, Deterministic, and Provenance-Preserving Framework for Long-Horizon Agent Memory](https://arxiv.org/abs/2611.33174v1)*
*Source: [Failure Broadens, Success Sharpens: Continual Adaptation of Tool-Use Agents Across Diverse Tasks with Dual-Polarity Memory](https://arxiv.org/abs/2611.33612v1)*
