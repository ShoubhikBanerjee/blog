---
title: "Synadia Agent Protocol Connects AI Agents Through NATS"
slug: "synadia-agent-protocol-connects-ai-agents-through-nats"
description: "The Synadia Agent Protocol for NATS lets AI agents register as `agents` micro services that callers can discover, prompt, and stream from using the same wire format. The project includes TypeScript..."
date: 2026-11-16T22:14:27+05:30
tags: [NATS, AIAgents, AgentProtocol, TypeScript, Python]
categories: ["AI", "AI Agents", "Software Development", "Messaging Systems", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/261475379?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Synadia Agent Protocol Connects AI Agents Through NATS

The Synadia Agent Protocol for NATS lets AI agents register as `agents` micro services that callers can discover, prompt, and stream from using the same wire format. The project includes TypeScript and Python caller and host SDKs, along with pre-built plugins for connecting existing AI harnesses to NATS.

## 🔍 How it works

- Each agent registers as an `agents` micro service and serves the protocol’s `prompt`, `status`, and `hb` endpoints.
- Subjects follow the pattern `agents.{verb}.{token}.{owner}.{session}`, where `verb` is `prompt`, `hb`, or `status`.
- The protocol can be used with Codex, OpenCode, Claude Code, OpenClaw, PI, Hermes, Flue, or a custom agent.

## 🧩 SDKs and plugins

The SDKs are split into caller and host packages in both TypeScript and Python:

| Component | Role |
|---|---|
| Caller SDK (`client-sdk/`) | Discovers and prompts agents. |
| Host SDK (`agent-sdk/`) | Registers and serves an agent. |

Caller-only consumers install the caller package; authors hosting agents install both halves of their language’s pair. A cross-SDK interoperability test runs the TypeScript reference agent against the Python client to validate the shared wire format.

Pre-built channel plugins connect existing AI harnesses to NATS without writing code. The active SDK release rollout roadmap tracks sender identity, extension hooks, compatibility, integration adoption, dependency controls, and release promotion.

## ⚙️ Extensions and applications

Tracing is not part of this release. The SDKs provide generic extension hooks, including prompt and request interceptors, extra envelope fields, and heartbeat extras; tracing extensions can be built in separate packages.

Apps built on the SDKs include:

- A Vue 3 browser client for discovery, prompting with attachments, streaming, and inline mid-stream `query` allow or deny.
- A control plane that spawns sessions when it discovers a headless controller and fans a single prompt across multiple working directories in parallel.
- A process that spawns and manages headless Claude Code sessions, each registering as a first-class agent at `agents.prompt.cc-headless.<owner>.<session>`.

#NATS #AIAgents #AgentProtocol #TypeScript #Python

---

*Source: [synadia-ai/synadia-agents](https://github.com/synadia-ai/synadia-agents)*
