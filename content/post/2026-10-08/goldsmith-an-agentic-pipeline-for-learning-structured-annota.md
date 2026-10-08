---
title: "Goldsmith: An Agentic Pipeline for Learning Structured Annotation Definitions"
slug: "goldsmith-an-agentic-pipeline-for-learning-structured-annotation-definitions"
description: "Many annotation projects begin before experts have a stable guideline or enough labels to train a task‑specific model."
date: 2026-10-08T18:03:50+05:30
tags: [annotation, LLM, promptoptimization, AItools]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Data Annotation", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# Goldsmith: An Agentic Pipeline for Learning Structured Annotation Definitions

Many annotation projects begin before experts have a stable guideline or enough labels to train a task‑specific model.

## 🔍 Overview
- Goldsmith is an agentic pipeline that converts a small **gold set**—expert‑annotated calibration examples that capture the intended task boundaries—into a reusable structured annotation definition.
- The definition is treated as a **trainable textual object**.

## 🧩 How It Works
- Candidate definitions are executed on the same gold examples and scored with an **executable structured loss**.
- Core components such as output schema, formatting, retrieval, repair, judging, and human review stay in an **external harness**.
- An **LLM editor** rewrites the highest‑loss failures into textual‑gradient revisions; revisions are accepted only when the measured loss decreases.

## ⚙️ Key Results
- In prompt‑optimization comparisons, Goldsmith **outperforms** direct rewriting, OPRO, APE, and PromptBreeder when evaluated under matched protocols.
- When combined with retrieval, score‑based routing, and human review, the learned definition **improves downstream annotation** for:
  - Typed span tasks
  - Pair‑level relation tasks
  - Fixed‑trigger event‑argument tasks
- These findings demonstrate that **scarce expert supervision** can support both task‑definition learning and scalable annotation.

## 💡 Why It Matters
- Provides a systematic way to bootstrap annotation pipelines without requiring extensive labeled data up front.
- Leverages the expressive power of LLMs to iteratively refine task definitions while maintaining a measurable loss signal.
- Enables more efficient use of expert effort, reducing the barrier to high‑quality annotation for new tasks.


#annotation #LLM #promptoptimization #AItools

---

*Source: [Goldsmith: Gold-Loss-Guided Definition Optimization with an Agentic Annotation Harness](https://arxiv.org/abs/2610.09489v1)*
*Source: [A Comparative Study of Evaluation Metrics for Long-Document Financial Narrative Summarization with Transformers](https://arxiv.org/abs/2610.09529v1)*
