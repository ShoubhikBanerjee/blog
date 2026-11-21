---
title: "OpenTelemetry plugin enables comprehensive tracing and metrics for Hermes Agent"
slug: "opentelemetry-plugin-enables-comprehensive-tracing-and-metrics-for-hermes-agent"
description: "An OpenTelemetry plugin has been released for Hermes Agent, enabling detailed observability for AI agent workflows. This update allows every interaction and process within the agent to be tracked and..."
date: 2026-11-21T22:09:40+05:30
tags: [OpenTelemetry, AIAgents, HermesAgent, Observability, LLMOps]
categories: ["AI", "AI Agents", "Developer Tools", "Observability", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/13635706?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenTelemetry plugin enables comprehensive tracing and metrics for Hermes Agent

An OpenTelemetry plugin has been released for Hermes Agent, enabling detailed observability for AI agent workflows. This update allows every interaction and process within the agent to be tracked and exported to compatible backends.

## 🔍 Overview

The plugin integrates Hermes Agent with OpenTelemetry (OTel) standards. It captures various operational aspects of the agent, including:
*   Model calls and API requests
*   Tool calls and skill loads
*   Approvals and delegated sub-agents

All of these events are structured into a single OTel trace for each Hermes turn. This trace includes metrics for tokens, costs, and latency. Optionally, logs and structured events are also captured and exported to any OTLP backend via HTTP or gRPC.

## 🧩 How it works

The plugin uses a comprehensive attribute schema to log details across different components of the agent. Attributes are emitted in two conventions to support various backends:
*   **OpenInference** (`llm.*`, `input.value`): Optimized for Phoenix.
*   **OTel GenAI** (`gen_ai.*`): Optimized for Langfuse, Weave, and generic dashboards.

This dual-convention approach eliminates the need for custom mapping in backend configurations.

## ⚙️ Key details

Specific trace data includes:

| Component | Tracked Details |
| :--- | :--- |
| Skills | Name, source (`skill_view` / path read), path; remains open until the turn ends |
| Model Calls | Model, provider, input user message, output assistant response |
| Metrics | Token counts (incl. cache and reasoning buckets), duration, finish reason, request parameters |
| Errors | `ERROR` status, exception details, and retry metadata |
| Tool Calls | Arguments, results, inferred target/command, and `hermes.tool.outcome` (`completed`, `error`, `timeout`, `blocked`, `cancelled`) |
| Approvals | Decision wait time, choice (`once`, `session`, `always`, `deny`, `timeout`, `smart_approve`, `smart_deny`, `smart_escalate`), and who decided |
| Sub-agents | Role, goal, status, duration, summary, child's model, and total subtree cost |
| Kanban | A card's run is traced from the dispatcher's claim through the worker's turn |

The `hermes.query_source` attribute distinguishes the origin of calls:
*   `main`: The agent loop's own calls
*   `subagent`: A delegated child's calls
*   `auxiliary`: Calls made on the agent's behalf (e.g., titling, compression, Mixture-of-Agents references, vision). These are tagged with `hermes.auxiliary.task`.

For successful `git commit` operations, the plugin records `hermes.tool.git_commit`, which is also counted as a `hermes.commit.count` and a `commit` event.

## 🚀 Multi-agent Support

The plugin supports complex orchestration patterns:
*   Delegated children
*   Kanban workers operating on different profiles and models
*   Swarms
*   Mixture-of-Agents
*   Cron jobs

In multi-agent runs, child executions are nested within the trace, ensuring that a single connected trace represents the entire workflow. GPU and CPU utilization are monitored using host metrics.

#OpenTelemetry #AIAgents #HermesAgent #Observability #LLMOps

---

*Source: [briancaffey/hermes-otel](https://github.com/briancaffey/hermes-otel)*
