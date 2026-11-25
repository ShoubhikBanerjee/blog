---
title: "Idun Agent Platform Is No Longer Maintained as Open-Source Project"
slug: "idun-agent-platform-is-no-longer-maintained-as-open-source-project"
description: "The Idun Agent Platform is no longer maintained. Its code stays open source under the GPLv3 license, and its official documentation remains online for reference."
date: 2026-11-25T12:10:39+05:30
tags: [LangGraph, FastAPI, OpenSource, AIAgents, Python]
categories: ["AI", "AI Agents", "Open Source", "Software Tools"]
image: "https://avatars.githubusercontent.com/u/170414217?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Idun Agent Platform Is No Longer Maintained as Open-Source Project

The Idun Agent Platform is no longer maintained. Its code stays open source under the GPLv3 license, and its official documentation remains online for reference.

## 🔍 Overview
Idun Agent Platform was created as an open-source, self-hosted production wrapper for LangGraph and Google ADK agents. It allows developers to deploy agents as production-ready FastAPI services without vendor lock-in.

Teams building AI agents typically face a tradeoff: building a custom production wrapper (combining FastAPI, traces, guardrails, and an admin UI), which is slow, or adopting SaaS solutions like LangGraph Cloud or LangSmith, which introduces sovereignty trade-offs. Idun provided a third path by offering a self-sufficient FastAPI process installed via a single `pip install` command on local or private infrastructure.

## ⚙️ Key details
The platform is distributed as a single wheel bundling three Python packages:

| Package | Description |
| --- | --- |
| `idun_agent_engine` | The engine SDK providing the FastAPI app factory, Model Context Protocol (MCP) registry, observability, and guardrails. |
| `idun_agent_standalone` | Provides the `idun` CLI, admin REST API, and UIs for chat, administration, and traces. |
| `idun_agent_schema` | Contains the Pydantic configuration schemas. |

Built-in platform capabilities and features include:
- AG-UI copilotkit API and bundled chat UI
- Admin panel and managed prompts
- 15+ guardrails
- MCP tool governance
- OpenTelemetry observability and dedicated trace store
- OIDC and SSO integration
- Memory persistence and messaging integrations

## 🛠️ Usage details
- Prerequisites: Python 3.12 or 3.13.
- Installation: `pip install idun-agent-engine`.
- CLI: The `idun` executable provides commands including `setup`, `serve`, `init`, `hash-password`, and `agent serve` via `idun_agent_standalone`.
- Workflow: Users create a directory (such as `my-agent/`), save the required files, and run the engine from within that directory or via an absolute path.
- Path Resolution: The `graph_definition: "./agent.py:graph"` setting is resolved relative to the directory where `idun init` is run.
- Endpoints: Launching the service opens a chat UI at `http://localhost:8000`. Settings, MCP servers, guardrails, and SSO are configured at `/admin`, while trace data is available at `/admin/traces`.

## 🚀 Availability
- Maintenance Status: No longer maintained.
- Licensing: Code remains available open source under GPLv3.
- Documentation: Stays online for developer reference.

#LangGraph #FastAPI #OpenSource #AIAgents #Python

---

*Source: [Idun-Group/idun-agent-platform](https://github.com/Idun-Group/idun-agent-platform)*
