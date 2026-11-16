---
title: "Grafana Releases Agent Observability SDKs and Plugins"
slug: "grafana-releases-agent-observability-sdks-and-plugins"
description: "Grafana has released open‑source SDKs and plugins that let developers instrument and monitor their coding agents in Grafana Cloud."
date: 2026-11-16T22:14:27+05:30
tags: [Grafana, Observability, AIagents, OpenSource, SDKs]
categories: ["AI", "Machine Learning", "AI Agents", "Developer Tools", "Open Source"]
image: "https://avatars.githubusercontent.com/u/7195757?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Grafana Releases Agent Observability SDKs and Plugins

Grafana has released open‑source SDKs and plugins that let developers instrument and monitor their coding agents in Grafana Cloud.

## 🔍 Overview
- Grafana Agent Observability monitors agents you build and coding agents.
- The repo provides open‑source SDKs and plugins that send telemetry to it.
- Capture sessions from coding agents like Cursor, Claude Code, Codex, Copilot CLI, OpenCode, Pi, Vibe, experimental Kiro CLI, and others.

## 🧩 How it Works
- Install the `agento11y` plugin for supported coding agents (except Hermes). Hermes has a separate Python plugin guide.
- Installation options:
  - `curl -fsSL https://raw.githubusercontent.com/grafana/agento11y/main/plugins/agento11y/scripts/install.sh | sh`
  - `brew install grafana/grafana/agento11y`
  - `go install github.com/grafana/agento11y/plugins/agento11y/cmd/agento11y@latest`
- After installation, run `agento11y login` and launch an agent, e.g., `agento11y codex`.
- The Coding Agent Observability guide covers all install options, configuration, and supported agents.

## ⚙️ Key Details
- Instrument agents with SDKs available for Go, Python, JS, .NET, Java.
- For custom app or agent code, use the `agento11y-instrument` agent skill:
  - Install `gcx` CLI: `curl -fsSL https://raw.githubusercontent.com/grafana/gcx/main/scripts/install.sh | sh` or `brew install gcx`.
  - Install skill: `gcx agent skills install agento11y-instrument`.
  - Skill inspects code, applies SDK with small diffs after confirmation, and verifies data with `gcx agento11y`.
  - If agent does not support skills, give `llms.txt` and ask it to instrument.
  - Alternatively, use the onboarding wizard in the Agent Observability plugin.
- Set `AGENTO11Y_*` environment variables and construct the client:
  - JS: `import { Agento11yClient } from "@grafana/agento11y"; const client = new Agento11yClient();`
  - Python: `from agento11y import Client; client = Client()`
  - Go: `client := agento11y.NewClient(agento11y.Config{})`

## 🚀 Availability
- All SDKs and plugins are open source and available in the Grafana GitHub repo.
- Supported agents include Cursor, Claude Code, Codex, Copilot CLI, OpenCode, Pi, Vibe, experimental Kiro CLI, and others.

## 💡 Why it Matters
- Enables monitoring of generations, tools, cost, traces, and evaluations across coding agents in one place.
- Helps observe usage, cost, tokens, and tools across agents.
- Allows developers to instrument their own apps or agents with minimal code changes.

#Grafana #Observability #AIagents #OpenSource #SDKs

---

*Source: [grafana/agento11y](https://github.com/grafana/agento11y)*
