---
title: "ClawMetry Provides Zero-Config Observability for AI Agent Runtimes"
slug: "clawmetry-provides-zero-config-observability-for-ai-agent-runtimes"
description: "ClawMetry is a new observability and governance tool that allows users to monitor AI agent runtimes in real time through a single dashboard."
date: 2026-09-09T00:51:34+05:30
tags: [AIagents, observability, LLM, ClawMetry]
categories: ["AI", "AI Agents", "Developer Tools", "Software Governance"]
image: "https://avatars.githubusercontent.com/u/987905?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ClawMetry Provides Zero-Config Observability for AI Agent Runtimes

ClawMetry is a new observability and governance tool that allows users to monitor AI agent runtimes in real time through a single dashboard.

## 🔍 Overview
ClawMetry provides a centralized dashboard for an agent fleet, supporting 30 AI agent runtimes. This includes:
* Claude Code
* Cursor
* OpenAI Codex
* GitHub Copilot
* Gemini CLI
* Cline
* OpenHands
* Aider
* Goose
* OpenClaw
* NVIDIA NemoClaw
* 19 others

## 🧩 How it works
The tool is designed for zero-config deployment and is launched with one command, opening at http://localhost:8900. It automatically detects existing agent runtimes and reads them in a read-only capacity without changing how they run. For agents built on an SDK, an interceptor is used to track LLM calls. Users can run several runtimes simultaneously and use a header switcher to re-scope tabs to a specific runtime.

## ⚙️ Key details
ClawMetry tracks a variety of metrics and operational data:

| Feature | Description |
| :--- | :--- |
| Sessions & transcripts | Turn-by-turn activity with replay |
| Cost & tokens | Tracking per runtime, model, session, and day with anomaly flags |
| Flow | Live diagram of messages through channels, models, and tools |
| Brain | Real-time reasoning and tool-call event stream |
| Context blowout | Window utilization sized per provider, including compaction vs forced overflow |
| Memory & skills | Files and skills loaded by each runtime |
| Health & logs | Live log stream, error rates, rate limits, disk, and memory |
| Alerts | Budget caps, error spikes, and agent-offline notifications routed to Slack, Discord, PagerDuty, Telegram, and Email |
| Approvals | Ability to pause and approve risky tool calls from a phone |

Regarding context-window blowout, ClawMetry sizes the window per provider using a table covering providers such as Anthropic.

#AIagents #observability #LLM #ClawMetry

---

*Source: [vivekchand/clawmetry](https://github.com/vivekchand/clawmetry)*
