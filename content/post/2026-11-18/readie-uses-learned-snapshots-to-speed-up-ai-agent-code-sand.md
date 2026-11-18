---
title: "Readie Uses Learned Snapshots to Speed Up AI Agent Code Sandboxes"
slug: "readie-uses-learned-snapshots-to-speed-up-ai-agent-code-sandboxes"
description: "Researchers have introduced Readie, a system that applies learned startup snapshots to reduce latency in code sandboxes used by AI agents for iterative code generation and execution."
date: 2026-11-18T18:09:03+05:30
tags: [AIagents, codeexecution, sandboxes, latencyoptimization, machinelearningsystems]
categories: ["AI", "Machine Learning", "AI Agents", "Software Engineering", "Systems"]
author: "Shoubhik Banerjee"
draft: false
---

# Readie Uses Learned Snapshots to Speed Up AI Agent Code Sandboxes

Researchers have introduced Readie, a system that applies learned startup snapshots to reduce latency in code sandboxes used by AI agents for iterative code generation and execution.

## 🔍 Overview
- AI agents act by iteratively generating and executing code for tasks ranging from quantitative research to personal assistance
- Many agents offload execution to dedicated code sandboxes to decouple the agent harness from code execution
- Existing code sandboxes suffer from slow startup because it is hard to build a compact, pre-warmed snapshot that covers nearly all required artifacts (packages, datasets) across diverse agent-generated code

## 🧩 How It Works
- Readie proposes a set of learned startup snapshots rather than a single snapshot
- Each snapshot is small, initializes quickly, and covers a fraction of agent-generated code; together the set covers most workloads
- The snapshot set is learned from a large training workload by formulating snapshot construction as an optimization problem and solving it with an approximation algorithm
- Training workload consists of 15K public and LLM-synthesized scripts

## ⚙️ Key Details
- Startup latency reduced by 3–22× compared to existing approaches at the same storage budget
- End-to-end runtime reduced by 1.3–3.3×
- System categorized under Computer Science > Artificial Intelligence (cs.AI)

## 💡 Why It Matters
- Learned snapshot sets achieve both compactness and broad coverage where single snapshots cannot
- Faster sandbox startup improves responsiveness of AI agents that rely on iterative code execution
- Gains are realized without increasing storage budget

#AIagents #codeexecution #sandboxes #latencyoptimization #machinelearningsystems

---

*Source: [WebAgents: Unbundling Agent Creation, Hosting, and Execution for an Agent-Native Web](https://arxiv.org/abs/2611.21978v1)*
*Source: [SkillBuffBench: Measuring What Agent Skills Contribute across Harnesses, Models, Skill Access Modes and Memory](https://arxiv.org/abs/2611.22017v1)*
*Source: [Readie: Low-Latency Code Sandboxes for AI Agents](https://arxiv.org/abs/2611.22171v1)*
