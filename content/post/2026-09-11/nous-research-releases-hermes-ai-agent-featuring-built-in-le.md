---
title: "Nous Research Releases Hermes AI Agent Featuring Built-In Learning Loop and Cross-Platform Integration"
slug: "nous-research-releases-hermes-ai-agent-featuring-built-in-learning-loop-and-cross-platform-integration"
description: "Nous Research has developed Hermes, a self-improving AI agent designed with a built-in learning loop. The system creates skills from experience, improves them during use, and builds a deepening model..."
date: 2026-09-11T22:04:55+05:30
tags: [NousResearch, AIAgents, OpenSource, MachineLearning, Hermes]
categories: ["AI", "AI Agents", "Software Development", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/134168893?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Nous Research Releases Hermes AI Agent Featuring Built-In Learning Loop and Cross-Platform Integration

Nous Research has developed Hermes, a self-improving AI agent designed with a built-in learning loop. The system creates skills from experience, improves them during use, and builds a deepening model of the user across sessions using Honcho dialectic user modeling.

## 🧩 How it works

Hermes is built around a continuous learning cycle that persists knowledge through agent-curated memory and periodic nudges. It utilizes FTS5 session search combined with LLM summarization for cross-session recall and is compatible with the agentskills.io open standard.

*   **Autonomous Skill Creation:** The agent generates new skills after completing complex tasks.
*   **Self-Improvement:** Skills are refined automatically during active use.
*   **Dialectic Modeling:** It develops a user model to maintain continuity across sessions.
*   **Trajectory Management:** Supports batch trajectory generation and compression for training future tool-calling models.

## ⚙️ Key features

The agent provides a full TUI with multiline editing, slash-command autocomplete, and streaming tool output. It can spawn isolated subagents for parallel workstreams and allows users to write Python scripts that call tools via RPC to collapse multi-step pipelines into zero-context-cost turns.

| Feature | Capability |
| :--- | :--- |
| Connectivity | Telegram, Discord, Slack, WhatsApp, Signal, and CLI from a single gateway |
| Scheduling | Built-in cron scheduler for daily reports, nightly backups, and weekly audits |
| Voice Support | Transcription of voice memos with cross-platform continuity |
| Model Support | Compatible with Nous Portal, OpenRouter, OpenAI, and custom endpoints |
| Terminal Backends | Local, Docker, SSH, Singularity, Modal, Daytona, and Vercel Sandbox |

## 🚀 Deployment and Infrastructure

Hermes is designed to be highly portable and cost-efficient. It can run on a $5 VPS, a GPU cluster, or serverless infrastructure like Modal and Daytona, where the environment hibernates when idle to reduce costs. 

For Windows users, Hermes runs natively without the need for WSL. The installer is fully self-contained and manages its own environment, including Python 3.11, Node.js, and a portable Git Bash (MinGit) located in `%LOCALAPPDATA%\hermes\git`. This installation does not require administrator privileges and remains isolated from system-wide Git installs.

Users should note that some antivirus software, such as Bitdefender or Windows Defender, may trigger a false positive on `uv.exe` within the Hermes bin folder. This file is Astral's Rust-based Python package manager, which Hermes bundles to manage its internal environment.

#NousResearch #AIAgents #OpenSource #MachineLearning #Hermes

---

*Source: [NousResearch/hermes-agent](https://github.com/nousresearch/hermes-agent)*
