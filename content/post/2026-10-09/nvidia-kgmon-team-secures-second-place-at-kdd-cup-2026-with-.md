---
title: "NVIDIA KGMON Team Secures Second Place at KDD Cup 2026 with Agent Harness"
slug: "nvidia-kgmon-team-secures-second-place-at-kdd-cup-2026-with-agent-harness"
description: "The NVIDIA KGMON team placed second in the KDD Cup 2026 Data Agents competition with a system that streamlines the agent harness to be smaller, clearer, and easier to verify."
date: 2026-10-09T18:05:31+05:30
tags: [KDD2026, AIAgents, NVIDIA, LLM, DataIntegration]
categories: ["AI", "Machine Learning", "AI Agents", "Data Engineering", "Artificial Intelligence"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/KGMON-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA KGMON Team Secures Second Place at KDD Cup 2026 with Agent Harness

The NVIDIA KGMON team placed second in the KDD Cup 2026 Data Agents competition with a system that streamlines the agent harness to be smaller, clearer, and easier to verify.

## 🔍 Overview
- The competition required agents to answer natural‑language questions over heterogeneous data sources such as databases, CSV/JSON files, prose documents, PDFs, and briefing videos.
- Every task demanded more than simple retrieval: agents had to inspect data, choose appropriate tools, reason across sources, produce a final answer file, and navigate traps common in analytical workflows.
- Teams were limited to a small, fixed LLM, making the harness the primary optimization surface.
- KGMON’s approach focused on preprocessing, constrained tools, persistent state, and systematic evaluation to make the task easier for the available model.

## 🛠️ Architecture & Workflow
- **Unified data access** – CSV and JSON files were converted into tables inside a single SQLite database, giving the agent one SQL interface for all structured data.
- **Single tool set** – The environment exposed only a few helpers: schema inspection, SQL queries, document lookup, prose extraction, and answer writing.
- **Schema‑scouting step** – Before the main reasoning loop the system inspected tables, columns, join keys, duplicate names, units, null patterns, and row‑grain issues, then supplied this context to the agent.
- **Middleware repair** – Malformed tool calls were automatically fixed so a single bad call would not abort the attempt.
- **Stateful Python environment** – Variables persisted between tool calls, allowing reuse of intermediate results.
- **Predefined functions** – `schema()`, `sql(query)`, and `write_answer(df)` reduced boilerplate, syntax errors, and file‑handling mistakes.
- **Execution tracing** – Repeated attempts and trajectory inspection helped identify failures and refine the harness.

| Function / Helper | Role |
|-----------------|------|
| `schema()` | Provide the agent with table and column metadata discovered during scouting |
| `sql(query)` | Execute a SQL statement against the unified SQLite database |
| `write_answer(df)` | Write the final answer file in the required format |
| Document lookup | Retrieve relevant prose or PDF content |
| Prose extraction | Pull specific text snippets from unstructured documents |

Figure 1 (see below) illustrates the overall workflow from data ingestion to final answer generation.

## ⚙️ Reliability Techniques
- Preprocessing data into a uniform SQL schema reduced routing failures and saved turns for reasoning.
- Constrained tool set limited the ways the agent could interact with the environment, lowering the chance of mistakes.
- Persistent state and middleware repair prevented a single error from ending an attempt.
- Short, valid attempts conserved the limited turn budget for additional runs, evaluation, and ensembling.
- Execution traces and trajectory inspection were used to pinpoint failures such as bad tool calls or answer‑format issues.

## 🚩 Common Failure Modes
- Bad tool call (e.g., syntax error) 
- Incorrect join key leading to wrong results
- Missed document rule or threshold in unstructured sources
- Answer‑format mismatch causing the final output to be rejected

## 💡 Why It Matters
- The techniques are especially useful when building reliable systems around smaller open models.
- Reliability often stems more from a well‑designed harness than from expanding the openness of the model itself.
- A streamlined harness leaves more capacity for the fixed LLM to focus on analysis rather than plumbing.

*Figure 1: Overall workflow of the KGMON system*  
![Workflow](/image1)


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/figure-1-3.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/KGMON-1024x576-png.webp)

#KDD2026 #AIAgents #NVIDIA #LLM #DataIntegration

---

*Source: [Building Reliable Data Analytics Agents: Lessons from the KDD Cup | NVIDIA Technical Blog](https://developer.nvidia.com/blog/building-reliable-data-analytics-agents-lessons-from-the-kdd-cup/)*
