---
title: "NVIDIA NeMo Gym Boosts Reliability of Siemens Fuse AI Agent for Standard-Cell Characterization"
slug: "nvidia-nemo-gym-boosts-reliability-of-siemens-fuse-ai-agent-for-standard-cell-characterization"
description: "NVIDIA’s open‑source NeMo Gym was used to evaluate and improve the reliability of the Siemens Fuse EDA AI Agent that drives the Solido Characterization Suite for standard‑cell characterization."
date: 2026-10-14T22:09:38+05:30
tags: [AIagents, EDA, NVIDIA, ChipDesign]
categories: ["AI", "Artificial Intelligence", "Electronic Design Automation", "Computer Architecture", "Machine Learning"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/agentic-workflow-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA NeMo Gym Boosts Reliability of Siemens Fuse AI Agent for Standard-Cell Characterization

NVIDIA’s open‑source NeMo Gym was used to evaluate and improve the reliability of the Siemens Fuse EDA AI Agent that drives the Solido Characterization Suite for standard‑cell characterization.

## 🔍 Overview
- AI agents can give remarkable productivity gains in complex chip design workflows, but their tendency to generate plausible yet incorrect artifacts makes reliability a major barrier to production adoption.
- In multistage engineering workflows, an undetected error early in setup can silently propagate through downstream stages and final artifact generation.
- Standard‑cell characterization is the process of generating accurate timing, power, and noise models for logic cells across operating conditions and is required whenever a semiconductor foundry issues a new process design kit (PDK).

## 🛠️ How NeMo Gym Works
- NeMo Gym is an open library for evaluating and improving models and agents using environments.
- The NeMo Gym agentic evaluation environment is designed to diagnose failure modes and track error propagation across complex, multistage workflows.
- It defines the task, tools, state, and a domain‑specific verifier that inspects final outputs (e.g., Liberty .lib files) against verified reference artifacts.
- Each rollout starts from a clean state, records thinking traces, input and output messages, and tool actions, enabling engineers to trace complete rollout trajectories and identify root causes behind subtle errors.

## 📊 Evaluation of the Siemens Fuse AI Agent
- The Siemens Fuse team used NeMo Gym to scale up evaluations of the Solido Characterization Suite agent when calling characterization tools.
- The agent orchestrates tools from the broader Solido Characterization Suite through the Siemens Fuse EDA AI Agent, which exposes Model Context Protocol (MCP) servers and skills to common coding harnesses including Claude Code, Codex, and Cursor.
- Evaluations verified the generated Liberty files against known references, surfacing both common and rare failures such as missing cells, missing corners, incorrect slew thresholds, and timing or power values outside tolerance.
- Findings guided changes to the agent’s skill and MCP tool descriptions.
- The measured benchmark composite score increased from approximately 55 % to about 95 % across a benchmark of representative standard‑cell characterization tasks, while turns and output tokens were reduced.

## 💡 Why It Matters
- Reliable AI agents can automate the full characterization flow: tool setup, large‑scale SPICE simulation, distributed compute, Liberty file generation, debugging, and final validation.
- Early‑stage errors that previously propagated silently are now caught by a rigorous verification protocol.
- Faster, trustworthy automation shortens the time required to regenerate and validate timing and power models whenever a foundry updates a PDK.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/agentic-workflow-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/ai-powered-library-characterization.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/evaluation-architecture-nemo-gym.webp)

#AIagents #EDA #NVIDIA #ChipDesign

---

*Source: [Optimizing Agent Reliability and Tool Calling Efficiency for Chip Design Using NVIDIA NeMo Gym | NVIDIA Technical Blog](https://developer.nvidia.com/blog/optimizing-agent-reliability-and-tool-calling-efficiency-for-chip-design-using-nvidia-nemo-gym/)*
