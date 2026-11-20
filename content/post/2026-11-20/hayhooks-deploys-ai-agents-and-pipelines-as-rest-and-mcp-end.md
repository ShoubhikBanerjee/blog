---
title: "Hayhooks deploys AI agents and pipelines as REST and MCP endpoints"
slug: "hayhooks-deploys-ai-agents-and-pipelines-as-rest-and-mcp-endpoints"
description: "Hayhooks allows developers to deploy Python wrappers or YAML pipelines as typed, validated endpoints, supporting REST APIs, OpenAI-compatible chat, MCP tools, and A2A agents with durable execution..."
date: 2026-11-20T18:09:02+05:30
tags: [Hayhooks, MCP, RESTAPI, AIAgents, Observability]
categories: ["AI", "AI Agents", "Developer Tools", "APIs", "MLOps"]
image: "https://avatars.githubusercontent.com/u/51827949?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Hayhooks deploys AI agents and pipelines as REST and MCP endpoints

Hayhooks allows developers to deploy Python wrappers or YAML pipelines as typed, validated endpoints, supporting REST APIs, OpenAI-compatible chat, MCP tools, and A2A agents with durable execution and built-in tracing.

## 🧩 How it works
*   **Endpoint Generation**: Deployments use method type hints to validate requests and generate the API schema.
*   **Protocol Support**: The system supports REST APIs, OpenAI-compatible chat completions, Model Context Protocol (MCP) tools, and Agent2Agent (A2A) agents.
*   **UI Integration**: Users can connect Open WebUI or use the embedded Chainlit UI to chat with agents.

## ⚙️ Key details
*   **Streaming & Responses**: Serves streaming Chat Completions and Responses endpoints, with responses arriving as server-sent events.
*   **Durable Execution**: Long-running work is checkpointed in Redis, allowing the system to wait for human approval, retry failures, and recover after restarts.
*   **Observability**: Executions and component traces can be inspected in a terminal dashboard or exported to an OpenTelemetry backend using `hayhooks[tracing]`.
*   **MCP & A2A Capabilities**: Runs an MCP server that exposes pipelines and agents as tools for Cursor, Claude Desktop, and other clients. Exposes chat-capable pipelines through the Agent2Agent protocol with generated agent cards for discovery and task delegation.

## 🚀 Availability
*   **Requirements**: Python 3.10 through 3.14 and an OpenAI API key are required.
*   **Access**: API docs are available at `http://localhost:1416/docs` for inspection and testing.

#Hayhooks #MCP #RESTAPI #AIAgents #Observability

---

*Source: [deepset-ai/hayhooks](https://github.com/deepset-ai/hayhooks)*
