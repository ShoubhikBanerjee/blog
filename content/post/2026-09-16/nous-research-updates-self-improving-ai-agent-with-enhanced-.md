---
title: "Nous Research Updates Self-Improving AI Agent with Enhanced Learning and Deployment"
slug: "nous-research-updates-self-improving-ai-agent-with-enhanced-learning-and-deployment"
description: "Nous Research has updated its self-improving AI agent, featuring a built-in learning loop that enables the agent to create and improve skills through experience."
date: 2026-09-17T00:50:10+05:30
tags: [NousResearch, AIAgents, MachineLearning, LLM]
categories: ["AI", "AI Agents", "Software Development", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/134168893?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Nous Research Updates Self-Improving AI Agent with Enhanced Learning and Deployment

Nous Research has updated its self-improving AI agent, featuring a built-in learning loop that enables the agent to create and improve skills through experience.

## 🔍 Overview
This agent utilizes a built-in learning loop to:
* Create skills from experience and improve them during use.
* Nudge itself to persist knowledge.
* Search past conversations.
* Build a deepening model of the user across sessions using Honcho dialectic user modeling.

## ⚙️ Key Details

### Technical Capabilities
* **Memory and Learning:** Features agent-curated memory with periodic nudges and autonomous skill creation following complex tasks.
* **Search and Recall:** Employs FTS5 session search with LLM summarization for cross-session recall.
* **Execution:** Supports spawning isolated subagents for parallel workstreams and writing Python scripts that call tools via RPC to collapse multi-step pipelines into zero-context-cost turns.
* **Training:** Provides batch trajectory generation and trajectory compression for training the next generation of tool-calling models.
* **Standards:** Compatible with the agentskills.io open standard.

### Interface and Integration
* **TUI:** Full TUI includes multiline editing, slash-command autocomplete, conversation history, interrupt-and-redirect, and streaming tool output.
* **Platforms:** Accessible via Telegram, Discord, Slack, WhatsApp, Signal, and CLI through a single gateway process.
* **Additional Features:** Includes voice memo transcription, cross-platform conversation continuity, and a built-in cron scheduler with delivery to any platform.

### Infrastructure and Deployment
* **Model Flexibility:** Compatible with Nous Portal, OpenRouter, OpenAI, and custom endpoints; users can switch using `hermes model` without code changes.
* **Hosting:** Can run on a $5 VPS, GPU clusters, or serverless infrastructure.
* **Terminal Backends:** Supports seven backends: local, Docker, SSH, Singularity, Modal, Daytona, and Vercel Sandbox.
* **Serverless Persistence:** Daytona and Modal allow the environment to hibernate when idle and wake on demand.

## 🚀 Availability
The agent offers native Windows support without requiring WSL, including the CLI, gateway, TUI, and tools. 

| Component | Windows Location | Linux/WSL2 Location |
| :--- | :--- | :--- |
| Installation Path | `%LOCALAPPDATA%\hermes` | `~/.hermes` |
| MinGit Path | `%LOCALAPPDATA%\hermes\git` | N/A |

**Windows Installation Details:**
* The installer includes uv, Python 3.11, Node.js, ripgrep, ffmpeg, and a portable Git Bash.
* Uses a ~45MB MinGit download that is isolated from system Git installs and requires no admin privileges.

#NousResearch #AIAgents #MachineLearning #LLM

---

*Source: [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent)*
