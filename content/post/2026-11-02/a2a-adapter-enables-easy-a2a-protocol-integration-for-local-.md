---
title: "a2a-adapter Enables Easy A2A Protocol Integration for Local AI Agents"
slug: "a2a-adapter-enables-easy-a2a-protocol-integration-for-local-ai-agents"
description: "The new **a2a-adapter** tool wraps existing agent CLIs, local agents, workflow engines, and Python agent frameworks behind the A2A (Agent-to-Agent) Protocol."
date: 2026-11-02T18:01:40+05:30
tags: [A2A, AIAgents, Python, Tooling]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Software Development", "Tools"]
image: "https://avatars.githubusercontent.com/u/186759928?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# a2a-adapter Enables Easy A2A Protocol Integration for Local AI Agents

The new **a2a-adapter** tool wraps existing agent CLIs, local agents, workflow engines, and Python agent frameworks behind the A2A (Agent-to-Agent) Protocol.

## 🔍 Overview
- Provides automatic AgentCard generation, JSON‑RPC handling, task lifecycle management, and streaming via the official A2A SDK.
- Your adapter only needs to invoke the underlying agent; a2a‑adapter takes care of the A2A plumbing.

## 🧩 How It Works
1. Install `a2a-adapter` into your project's virtual environment (Python 3.11+ required).
2. Wrap your existing agent with the adapter and start the server.
3. The adapter exposes the agent as an A2A server, e.g., `http://localhost:9000`, with an auto‑generated Agent Card at `http://localhost:9000/.well-known/agent-card.json`.
4. The server can be mounted inside an existing ASGI app using `to_a2a(adapter)`.

## ⚙️ Supported Agents
- Claude Code
- Codex
- Pi
- OpenClaw
- n8n
- LangGraph
- LangChain
- CrewAI
- Ollama
- Hermes Agent
- Custom Python functions

## 🚀 Installation & Usage
- Install the CLI as an isolated tool so the `a2a-adapter` command is on your `PATH`.
- Upgrade later with `uv tool upgrade a2a-adapter`.
- Avoid system‑wide `pip install` because macOS's built‑in pip runs Python 3.9 (too old) and many Linux distributions block it (PEP 668).
- Ensure the underlying agent works on its own; `a2a-adapter` does not install the agent.
  - Example: install Claude Code and run `claude` once to sign in.
- If the agent executable is not on `PATH`, specify it with `--executable /path/to/agent`.
- Start the server from the project directory where the agent should run.
- Options placed **before** `--` configure the A2A server; options placed **after** `--` are passed to the underlying agent CLI.
- Run `a2a-adapter -help` for a list of supported agents, or `a2a-adapter <agent> -help` for agent‑specific usage.

## 💡 Why It Matters
- A single adaptor turns any compatible local agent into an A2A‑compliant service without modifying the agent code.
- The same A2A server interface works for both classic local agents (Claude Code, Codex, Pi, OpenClaw) and modern Python‑based frameworks.
- By providing a standard Agent Card at `/.well-known/agent-card.json`, the adapter enables discovery and integration in broader A2A ecosystems.

#A2A #AIAgents #Python #Tooling

---

*Source: [hybroai/a2a-adapter](https://github.com/hybroai/a2a-adapter)*
