---
title: "Graphectory Enables Process‑Centric Analysis and Real‑Time Monitoring of Agentic Systems"
slug: "graphectory-enables-processcentric-analysis-and-realtime-monitoring-of-agentic-systems"
description: "Agentic systems are modern software systems composed of orchestrated modules, exposed interfaces, and deployment pipelines. Their execution is stochastic and adaptive, and evaluation has..."
date: 2026-10-03T12:03:03+05:30
tags: [AIagents, AgenticSystems, LLM, ProcessAnalysis]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Machine Learning", "Software Engineering"]
author: "Shoubhik Banerjee"
draft: false
---

# Graphectory Enables Process‑Centric Analysis and Real‑Time Monitoring of Agentic Systems

Agentic systems are modern software systems composed of orchestrated modules, exposed interfaces, and deployment pipelines. Their execution is stochastic and adaptive, and evaluation has traditionally been outcome‑centric, focusing only on final success or failure. To expose how agents reason, plan, act, and adjust strategies, researchers introduced **Graphectory**, a systematic encoding of temporal and semantic relations in such software.

## 🔍 Overview
- Agentic workflows such as **SWE‑agent** and **OpenHands** were examined.
- Analyses covered **4,000 trajectories** generated with a **combination of four backbone Large Language Models (LLMs)**.
- The goal was to resolve issues from the **SWE‑bench Verified** benchmark.

## 🧩 How Graphectory Works
- Inspired by graph representations of conventional software, Graphectory records the sequence of actions, decisions, and context changes as a directed graph.
- This representation supports the creation of **process‑centric metrics** that assess workflow quality beyond final outcomes.
- An accompanying technique, **Langutory**, captures language‑level information alongside the graph.

## 📊 Findings from Automated Analyses
- The full analysis completed in **four minutes**.
- **Richer prompts or stronger LLMs** produced more complex Graphectory graphs, indicating deeper exploration, broader context gathering, and more thorough validation before submitting patches.
- Problem‑solving strategies depended on **problem difficulty** and the **underlying LLM**:
  - For resolved issues, agents typically followed a coherent **localization → patching → validation** pattern.
  - Unresolved issues often displayed chaotic, repetitive, or back‑tracking behaviors.
- Even when successful, agents frequently followed **inefficient processes**, leading to unnecessarily long trajectories.

## ⚙️ Real‑Time Construction and Intervention
- A novel technique builds Graphectory and Langutory **in real time** during execution.
- When the system detects trajectory issues, it sends a diagnostic message to the agent and can **roll back** the trajectory when appropriate.
- Experimental results show that **online monitoring with interventions** improves resolution rates by **6.9%–23.5%** across models for problematic instances, while **significantly shortening trajectories with near‑zero overhead**.

## 🚀 Why It Matters
- Shifts evaluation from a purely outcome‑centric view to a **process‑centric perspective**, enabling deeper insight into agent reasoning.
- Provides a practical pathway to **enhance agentic programming productivity** through automated, low‑overhead monitoring and corrective feedback.
- Establishes a foundation for future research on **systematic, graph‑based analysis of stochastic AI workflows**.

#AIagents #AgenticSystems #LLM #ProcessAnalysis

---

*Source: [Process-Centric Analysis of Agentic Software Systems for OOPSLA 2026](https://research.ibm.com/publications/process-centric-analysis-of-agentic-software-systems)*
