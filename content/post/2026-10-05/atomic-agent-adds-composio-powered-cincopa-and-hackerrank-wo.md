---
title: "Atomic Agent adds Composio-powered Cincopa and HackerRank Work integrations"
slug: "atomic-agent-adds-composio-powered-cincopa-and-hackerrank-work-integrations"
description: "Atomic Agent, the open‑source AI agent that runs on your machine and supports local models via llama.cpp, now integrates with the multimedia platform Cincopa and the coding‑assessment platform..."
date: 2026-10-05T06:06:53+05:30
tags: [AIAgents, Composio, Cincopa, HackerRankWork]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Developer Tools"]
image: "https://composio.dev/toolkits/graphics/composio_ogImage.png"
author: "Shoubhik Banerjee"
draft: false
---

# Atomic Agent adds Composio-powered Cincopa and HackerRank Work integrations

Atomic Agent, the open‑source AI agent that runs on your machine and supports local models via llama.cpp, now integrates with the multimedia platform Cincopa and the coding‑assessment platform HackerRank Work through Composio’s Tool Router.

## 🔍 Overview
- Atomic Agent runs locally and supports local models through **llama.cpp**.
- Integration is provided via **Composio**, which connects to more than 1,500 apps.
- Both Cincopa and HackerRank Work are accessed through the **Model Context Protocol (MCP)** implementation offered by Composio’s Tool Router.

## 🧩 How it works
- Requires **Atomic Agent v0.5.6 or later**, a **Composio API key**, and an account on the target service (Cincopa or HackerRank Work).
- Add the line `COMPOSIO_API_KEY=YOUR_COMPOSIO_API_KEY` to `~/.atomic-agent/.env` (ASCII characters only because the key is sent in an HTTP header).
- Atomic Agent connects to Composio’s Tool Router over **Streamable HTTP MCP**.
- On first use, open the sign‑in link returned in the chat to authorize the connection.
- Tools become available **immediately, without a restart**.
- Execution and account‑connection tools follow the Agent’s configured approval policy, and any approval prompt must be reviewed before an action is allowed.

## ⚙️ Features
### Cincopa capabilities
- **Remote media uploading**: Instruct the agent to upload videos, images, or audio from external URLs directly into Cincopa galleries.
- **Upload status tracking**: Query real‑time status of ongoing or recent uploads.
- **Abort in‑progress uploads**: Cancel stalled or unnecessary uploads.
- **API connection validation**: Verify API credentials and connectivity.
- **Upload iframe generation**: Retrieve an iframe URL for embedding an upload widget.

### HackerRank Work capabilities
- List all companies and their unique identifiers.
- Consume SAML assertions.
- Get the SP‑initiated SSO sign‑on URL.
- Schedule coding assessments, retrieve interview feedback, and more using natural language.

## 📋 Tools (Cincopa & HackerRank Work)
| Tool | What it does |
|------|--------------|
| Upload Asset From URL | Upload a new asset from an external URL and receive a status ID for tracking. |
| Abort Asset Upload From URL | Cancel an ongoing asset upload by providing its status ID. |
| Get Asset Upload From URL Status | Check the status of an upload initiated via URL using its status ID. |
| Get Upload Iframe | Generate an upload iframe URL for embedding a widget. |
| Validate API Connection | Confirm API credentials and connectivity to the service. |
| List Companies | Retrieve a list of all companies and their unique identifiers (HackerRank Work). |
| Consume SAML Assertions | Process SAML assertions for authentication (HackerRank Work). |
| Get SP‑initiated SSO URL | Obtain the service‑provider‑initiated SSO sign‑on URL (HackerRank Work). |

## 🔒 Security & Compliance
- All sensitive data (tokens, keys, configuration) is **encrypted at rest and in transit**.
- **Composio** is **SOC 2 Type 2** compliant and follows strict security practices, ensuring safe handling of Cincopa and HackerRank Work credentials.
- You can configure which Cincopa scopes and actions are allowed when connecting the account to Composio.

## 📦 Availability & Limits
- The **Hobby plan** includes **100,000 tool calls per month**.
- With a standalone MCP server, tools are fixed to that server; using the Composio Tool Router allows dynamic loading of tools from Cincopa, HackerRank Work, and many other apps via a single MCP endpoint.

## 🚀 Getting Started
1. Ensure you have **Atomic Agent v0.5.6+**, a **Composio API key**, and an account on the desired service.
2. Add `COMPOSIO_API_KEY=YOUR_COMPOSIO_API_KEY` to `~/.atomic-agent/.env`.
3. Start Atomic Agent.
4. In the Agent UI, go to **Integrations → Composio**, paste the API key, and confirm.
5. Follow the sign‑in link returned in the chat to authorize the connection.
6. The relevant tools appear instantly; you can now issue natural‑language commands to upload media to Cincopa or manage assessments in HackerRank Work.


#AIAgents #Composio #Cincopa #HackerRankWork

---

*Source: [Cincopa MCP Integration with Atomic Agent | Composio](https://composio.dev/toolkits/cincopa/framework/atomic-agent)*
*Source: [HackerRank Work MCP Integration with Atomic Agent | Composio](https://composio.dev/toolkits/hackerrank_work/framework/atomic-agent)*
