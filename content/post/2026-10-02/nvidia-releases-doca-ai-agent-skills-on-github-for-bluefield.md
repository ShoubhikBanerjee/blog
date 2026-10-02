---
title: "NVIDIA Releases DOCA AI Agent Skills on GitHub for BlueField DPU Infrastructure"
slug: "nvidia-releases-doca-ai-agent-skills-on-github-for-bluefield-dpu-infrastructure"
description: "NVIDIA has released DOCA AI agent skills on GitHub, providing a standardized, machine-readable specification that allows AI agents to manage BlueField data processing units (DPUs). This development..."
date: 2026-10-02T06:06:47+05:30
tags: [NVIDIA, DOCA, AIagents, DPU, BlueField]
categories: ["AI", "AI Infrastructure", "Software Development", "Data Centers"]
image: "https://developer-blogs.nvidia.com/wp-content/uploads/2026/09/agentic-ai-660x370.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases DOCA AI Agent Skills on GitHub for BlueField DPU Infrastructure

NVIDIA has released DOCA AI agent skills on GitHub, providing a standardized, machine-readable specification that allows AI agents to manage BlueField data processing units (DPUs). This development addresses the limitations of general training data, which often fails to capture the large, rapidly evolving, and hardware-specific surface of the DOCA library.

## 🔍 Overview
DOCA is the unified software platform for NVIDIA BlueField DPUs, designed for agentic AI infrastructure. It encompasses multiple domains of data center management:
* Accelerated networking
* AI-native storage
* In-silicon security
* Telemetry
* Lifecycle management

## 🧩 How it works
The system uses a lightweight, open format centered on a `SKILL.md` file. Unlike static documentation, these skills are specifications that an agent can reason against directly. Each skill is scoped to a specific DOCA component or workflow, such as DOCA Flow, GPUNetIO, or PCC. 

When an agent loads a skill, it receives:
* Verified API signatures and function signatures
* Hardware capability requirements
* Correct pkg-config module names
* Build-container constraints
* Common failure modes and their specific mitigations

## 📊 Performance and Validation
NVIDIA evaluated the impact of these skills using 65 real DOCA developer prompts. Without the skills, agents frequently guessed versions and misused APIs. With the skills enabled, agent performance reached 100% satisfaction across all graded checklist items.

| Failure Mode Without Skills | Frequency (out of 65 prompts) |
| :--- | :--- |
| Misuse of APIs and flags | 59 |
| Hardware capability not verified | 46 |
| Wrong tool routing | 39 |
| Skipped smoke tests | 34 |
| Guessed versions | 30 |

## ⚙️ Key details
By using skills, agents can verify what a device actually supports before writing code, rather than encountering errors after deployment. The agents apply preflight checks, rollback plans, and awareness of hardware states like cold power-cycles. For example, an agent using skills for the DOCA Comch API uses correct argument orders and verified flags without inventing sequences. 

## 🚀 Availability
DOCA AI agent skills are now available on GitHub. This allows developers to focus on writing code while the agent handles hardware-specific constraints and verified API calls from the start.

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2026/08/AI-Agent-Skills-660x370.png)

![figure](https://developer-blogs.nvidia.com/wp-content/uploads/2024/05/nvidia-bluefield-doca-graphic-660x370.png)

#NVIDIA #DOCA #AIagents #DPU #BlueField

---

*Source: [Build Applications on NVIDIA BlueField Faster with NVIDIA DOCA Agent Skills | NVIDIA Technical Blog](https://developer.nvidia.com/blog/build-applications-on-nvidia-bluefield-faster-with-nvidia-doca-agent-skills/)*
*Source: [AI in 2026: Taking Your AI Use to the Next Level, BK, 10/02/2026](https://www.eventbrite.com/e/ai-in-2026-taking-your-ai-use-to-the-next-level-bk-10022026-tickets-1997162759576)*
*Source: [Agentic AI workshop 2026: A Two-Day Industry Masterclass | University of Essex](https://www.essex.ac.uk/events/2026/10/01/agentic-ai-workshop-2026)*
