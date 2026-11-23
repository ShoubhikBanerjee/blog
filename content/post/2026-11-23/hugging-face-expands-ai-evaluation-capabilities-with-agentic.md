---
title: "Hugging Face Expands AI Evaluation Capabilities with Agentic Abstractions"
slug: "hugging-face-expands-ai-evaluation-capabilities-with-agentic-abstractions"
description: "The Hugging Face hub has experienced a 16X growth in eval datasets over the past year, reaching approximately 17000 datasets. Today, it hosts around 3500 eval leaderboards, establishing it as the..."
date: 2026-11-23T22:18:20+05:30
tags: []
categories: ["AI"]
image: "https://huggingface.co/blog/assets/agentic-evals/thumbnail.png"
author: "Shoubhik Banerjee"
draft: false
---

# Hugging Face Expands AI Evaluation Capabilities with Agentic Abstractions

## 📊 Scale of Evaluation Growth

The Hugging Face hub has experienced a 16X growth in eval datasets over the past year, reaching approximately 17000 datasets. Today, it hosts around 3500 eval leaderboards, establishing it as the central home for AI evaluation.

## 🧩 What Are Agentic Abstractions?

In recent months, the hub has incorporated support for agentic abstractions relevant to evaluation:

- **Traces**: Store an agent's work in an easily reviewable and sharable way
- **Benchmarks**: Highlight datasets used to evaluate models with leaderboards
- **Environments**: Show datasets used as agentic RL or evaluation environments

## ⚙️ How Evaluation Works for Agents

- A **task** gives the agent its instruction
- The **agent harness** wraps the model and its tools, letting it work inside a pinned environment
- The **evaluation harness** runs several rollouts for each task
- When a rollout ends, a **verifier** grades the environment's final state
- Each rollout leaves a **trace**, and traces and scores together become part of the final published evidence

## 🌱 From Question-Answer to Agentic Tasks

Traditional benchmarks like MMLU (2020) and GPQA (2023) measure knowledge and reasoning through answers. As models gained planning and tool-use capabilities, agentic benchmarks expanded to include:

- SWE-bench (resolving software issues)
- WebArena (completing tasks on websites)
- Decentralized swarms, teams managed by an orchestrator, and specialized agents collaborating on scientific work

## ⚠️ Challenges in Agentic Evaluation

Agentic deployments are becoming the most prominent type in model release announcements due to high user and enterprise interest. In agentic evaluations, once an agent uses tools to complete a task, each part of the surrounding software can affect its score. A Terminal-Bench audit demonstrated accuracy varying by up to 29.9 percentage points when changing the agent harness with a fixed model.

## 🔒 The Need for Better Evaluation Practices

- 98.2% of model-benchmark scores are reported by only one party
- Artificial Analysis reports 60% of its Intelligence Index v5 rests on evaluations with private test sets or held-out answers
- Google DeepMind recently piloted double-blind evaluations, where a secure enclave hides test prompts from the model being evaluated

## 🚀 Availability

These agentic abstraction features are now available on the Hugging Face hub for developers and researchers building and evaluating AI systems.

---

*Source: [How to build and maintain an agentic evaluation](https://huggingface.co/blog/agentic-evals)*
