---
title: "Atomic Agent Adds Snowflake Integration via Composio and MCP"
slug: "atomic-agent-adds-snowflake-integration-via-composio-and-mcp"
description: "Atomic Agent, the open‑source on‑device AI assistant, now supports direct interaction with Snowflake through the Composio integration and the Snowflake Model Context Protocol (MCP)."
date: 2026-10-12T18:04:23+05:30
tags: [AtomicAgent, Snowflake, Composio, AIAgents, MCP]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Data Management", "Cloud Services"]
image: "https://composio.dev/toolkits/graphics/composio_ogImage.png"
author: "Shoubhik Banerjee"
draft: false
---

# Atomic Agent Adds Snowflake Integration via Composio and MCP

Atomic Agent, the open‑source on‑device AI assistant, now supports direct interaction with Snowflake through the Composio integration and the Snowflake Model Context Protocol (MCP).

## 🔍 Overview
- Atomic Agent runs on your machine and supports local models via **llama.cpp**.
- Through Composio it can connect to **1,500+ apps**, including Snowflake.
- Users can issue natural‑language requests such as "list today’s new users" or "cancel a long‑running data import"; authentication is handled automatically.

## 🧩 How it works
- Atomic Agent connects to **Composio’s Tool Router** over **Streamable HTTP MCP**.
- For each request the agent discovers the appropriate tools; Composio supplies the necessary account authentication.
- Execution and account‑connection tools obey the agent’s configured **approval policy** – you must review any approval prompt before the action proceeds.

## ⚙️ Setup & Usage
- **Requirements**: Atomic Agent **v0.5.6** or later, a **Composio API key**, and a **Snowflake account**.
- Add the line below to `~/.atomic‑agent/.env`, replacing the placeholder with your key, then start Atomic Agent:
  ```
  COMPOSIO_API_KEY=YOUR_COMPOSIO_API_KEY
  ```
- In Atomic Agent, open the **Integrations** tab, select **Composio**, press **e**, paste the API key, and press **Enter**. The tools become available **immediately, without a restart**.
- Ask Atomic Agent to perform an action in Snowflake. The agent searches Composio for the correct tool. On first use, a sign‑in link is returned in the chat – follow it to connect your Snowflake account, then return to Atomic Agent to continue.

## 🚀 Availability
- The **Hobby plan** includes **100,000 tool calls per month**.
- Integration can be disabled by setting `"composio": { "enabled": false }` in the config; the saved key remains on disk.

## 📋 Tool Reference
| Tool | What it does |
|------|--------------|
| Cancel Statement Execution | Cancels the execution of a running SQL statement |

The Snowflake MCP server implements the **Model Context Protocol**, giving the agent structured and secure access to the data warehouse and service status. It enables the agent to execute SQL, explore databases and tables, track or cancel statements, inspect catalog integrations, and monitor incidents and maintenance on your behalf.

#AtomicAgent #Snowflake #Composio #AIAgents #MCP

---

*Source: [Snowflake MCP Integration with Atomic Agent | Composio](https://composio.dev/toolkits/snowflake/framework/atomic-agent)*
