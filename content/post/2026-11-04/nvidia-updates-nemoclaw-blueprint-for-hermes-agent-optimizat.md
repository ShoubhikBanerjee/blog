---
title: "NVIDIA updates NemoClaw blueprint for Hermes agent optimization"
slug: "nvidia-updates-nemoclaw-blueprint-for-hermes-agent-optimization"
description: "NVIDIA released an updated NemoClaw blueprint that guides a complete optimization cycle for a Hermes enterprise assistant, showing how to use NeMo Compass, NeMo Eval Author, and NeMo Relay to..."
date: 2026-11-04T22:02:53+05:30
tags: [NVIDIA, AIAgents, AgentOptimization, NeMo]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Machine Learning", "Developer Tools"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/agentic-workflow-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA updates NemoClaw blueprint for Hermes agent optimization

NVIDIA released an updated NemoClaw blueprint that guides a complete optimization cycle for a Hermes enterprise assistant, showing how to use NeMo Compass, NeMo Eval Author, and NeMo Relay to identify failures, create evaluations, update instructions, and compare results.

## 🔍 Overview
- The NemoClaw blueprint walks you through one full optimization cycle: record agent traces, analyze them with **NeMo Compass**, generate tests with **NeMo Eval Author**, update the agent’s instructions, and compare performance on development and held‑out tasks.
- The example agent is a **Hermes enterprise assistant** connected via **Model Context Protocol (MCP)** to a fictional company’s chat, email, files, and tickets.

## 🧩 How it works
1. **Record traces** – Each Hermes run is stored as a single JSON line; the repository contains 42 traces plus an `ETHOS.md` file that defines the assistant’s expected behavior.
2. **Analyze with NeMo Compass** – The tool scans the traces and returns findings based on three signals:
   - Signs of unusual behavior
   - How the agent uses tools
   - Divergence from the agent’s intended behavior
   It also supplies trace IDs that link each signal to the relevant run.
3. **Create evaluations with NeMo Eval Author** – Using a coding agent such as **Codex** or **Claude Code**, four **Harbor** evaluations are generated (e.g., “draft a response”). The author also builds a verifier that flags runs where the agent calls the `send_message` tool without human confirmation.
4. **Update the agent** – The Hermes agent’s `SOUL.md` is edited to enforce that requests to write, draft, compose, prepare, or suggest a message only produce a draft for review and never send automatically.
5. **Compare results** – The updated agent is run on both development and held‑out tasks to see the impact of the instruction changes.

## ⚙️ Key components
| Library | Role |
|---|---|
| NeMo Compass | Analyzes stored traces, identifies recurring problems, evaluation gaps, and prioritizes improvements |
| NeMo Eval Author | Provides coding‑agent workflows to create Harbor or NeMo Gym evaluations and verifiers |
| NVIDIA NeMo Relay | (Mentioned as part of the blueprint; specific role not detailed in the evidence) |

## 🛠️ Required environment
- Linux machine running Docker natively
- Recommended OS: **Ubuntu 24.04** with **8 vCPUs** and **32 GB RAM**
- **OpenShell 0.1.2** and **Harbor 0.22.0**
- An NVIDIA API key from **build.nvidia.com**
- A coding agent supported by NeMo Eval Author (e.g., **Codex** or **Claude Code**)

## 📈 Results & Findings
- Internal benchmarks showed that running the full set of NeMo Compass signals on thousands of traces identified anomalies that a coding agent assigned a similar task missed.
- The verifier flagged runs where the assistant sent a message without human confirmation, marking them as failures.

## 🚀 Getting started
- Follow the step‑by‑step tutorial on GitHub.
- Alternatively, launch the workflow with an **NVIDIA Brev** launchable.
- Use the provided **Hermes** blueprint, `ETHOS.md`, and `SOUL.md` files as a starting point.


![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/agentic-workflow-1024x576-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/10/nemoclaw-featured-660x370-png.webp)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/Tracing-Agent-Harness-660x370-png.webp)

#NVIDIA #AIAgents #AgentOptimization #NeMo

---

*Source: [Use NVIDIA NeMo to Turn Agent Failures into Tests and Harness Fixes | NVIDIA Technical Blog](https://developer.nvidia.com/blog/use-nvidia-nemo-to-turn-agent-failures-into-tests-and-harness-fixes/)*
