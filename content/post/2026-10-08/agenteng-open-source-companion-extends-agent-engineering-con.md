---
title: "AgentEng Open‑Source Companion Extends Agent Engineering Conference"
slug: "agenteng-opensource-companion-extends-agent-engineering-conference"
description: "Today we are introducing **AgentEng: Agent Engineering HQ**, an open‑source conference and tooling companion that lets developers retrieve the Agent Engineering Conference catalogue, query..."
date: 2026-10-08T12:07:03+05:30
tags: [AgentEngineering, OpenSource, AItools, Python, Conference]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Developer Tools", "Conferences"]
image: "https://shashikantjagtap.net/wp-content/uploads/2026/10/AgentEng_hero-1200x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# AgentEng Open‑Source Companion Extends Agent Engineering Conference

Today we are introducing **AgentEng: Agent Engineering HQ**, an open‑source conference and tooling companion that lets developers retrieve the Agent Engineering Conference catalogue, query agent‑engineering tools, and experiment with them directly from a terminal.

## 📅 Overview
- The Agent Engineering Conference — first edition held at Everyman, Canary Wharf, London on 16 October 2026 – brings founders and engineering leaders together for technical talks on context, memory, evaluation, harnesses, inference and coding agents.
- Future editions are planned for London and San Francisco alongside existing community events.
- While the conference website used a terminal‑style interface for presentation, the new companion lets users *run* that interface themselves.

## 🛠️ How it works
- **AgentEng** ships as a Python package that includes:
  - a **Python CLI**
  - a **Model Context Protocol (MCP) server**
  - an **Agent2Agent (A2A) service**
  - experimental **Agent Client Protocol (ACP) client** support
- The package bundles a **public event catalogue** and a **directory of agent‑engineering tools**. Both expose a typed request/result format, so a query made via the CLI, MCP or A2A hits the same catalogue service and returns consistent metadata.
- Event and tool lookups work **offline**; no provider key or model call is required.

## ⚙️ Key details
- **Event catalogue** contains:
  - London and San Francisco events
  - speaker profiles, talk abstracts, agendas, venue information, FAQs, registration links
- **Tool directory** helps find frameworks, coding agents, memory systems, evaluation tools, models and infrastructure discussed at the conference.
- Installation options:
  - The website installer bundles the CLI and server extras and can bootstrap **uv** when needed.
  - If you already use **uv**, install directly with `uv tool install 'agenteng[server]'`.
- Usage:
  - Run `agenteng` in a terminal to open an interactive menu.
  - Use individual commands to browse the published programme (examples provided in the documentation).

## 🚀 Availability
- Source code and documentation are publicly available for anyone to use, study, or contribute.
- The package can be installed via standard Python tooling or the provided website installer.

## 💡 Why it matters
- Developers can **investigate topics before attending**, import the programme into their coding workspace, and **experiment with tools afterwards** without waiting for the next event.
- By exposing the same catalogue through multiple interfaces, AgentEng lets teams keep source references and metadata while choosing the most convenient way to interact with the data.
- The companion creates a **continuing home** for the work presented at the conference, turning a one‑off event into an ongoing, searchable knowledge base for the agent‑engineering community.


![figure](https://shashikantjagtap.net/wp-content/uploads/2026/10/AgentEng_hero-820x431.png)

#AgentEngineering #OpenSource #AItools #Python #Conference

---

*Source: [Agent Engineering HQ Launched AgentEng: CLI, MCP, A2A and ACP Support for Agentic AI Events](https://shashikantjagtap.net/agent-engineering-hq-launched-agenteng-cli-mcp-a2a-and-acp-support-for-agentic-ai-events/)*
*Source: [10 Agentic AI Tools for Product Teams in 2026](https://figr.design/blog/agentic-ai-tools)*
*Source: [Agentic AI Masterclass — Hands-on AI Agents Training in Munich](https://www.eventbrite.com/e/agentic-ai-masterclass-hands-on-ai-agents-training-in-munich-tickets-1998605662337)*
