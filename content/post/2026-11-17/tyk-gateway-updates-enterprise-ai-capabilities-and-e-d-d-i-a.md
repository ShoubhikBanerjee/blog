---
title: "Tyk Gateway Updates: Enterprise AI Capabilities and E.D.D.I Agent Middleware"
slug: "tyk-gateway-updates-enterprise-ai-capabilities-and-e-d-d-i-agent-middleware"
description: "Tyk has released updates expanding its API and AI Gateway platform to support MCP (Model Context Protocol) and introducing E.D.D.I (Enhanced Dialog Driven Interface), a production-grade,..."
date: 2026-11-17T06:20:51+05:30
tags: [Tyk, APIGateway, AIagents, MCP, EDDI, MultiAgent]
categories: ["AI", "API Management", "AI Agents", "Developer Tools", "Enterprise Software"]
image: "https://avatars.githubusercontent.com/u/16121529?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Tyk Gateway Updates: Enterprise AI Capabilities and E.D.D.I Agent Middleware

Tyk has released updates expanding its API and AI Gateway platform to support MCP (Model Context Protocol) and introducing E.D.D.I (Enhanced Dialog Driven Interface), a production-grade, config-driven multi-agent orchestration middleware for conversational AI.

## 🔍 Overview
Tyk Gateway is a cloud-native, open-source, enterprise-ready API and AI Gateway that supports REST, GraphQL, TCP, gRPC, and MCP. Built since 2014, it is designed to be the fastest API gateway on the planet. The platform is provided “batteries-included” with no feature lockout, enabling organizations to rate limit, authenticate, gather analytics, and apply microservice patterns with ease.

E.D.D.I is a new addition built on Java 25 and Quarkus. It coordinates users, AI agents, and business systems through intelligent routing, persistent memory, and API orchestration without requiring code. E.D.D.I ships as a Red Hat-certified Docker image and has been selected as a UNIDO Trusted Partner for Industrial AI.

## 🧩 How it works
Tyk Gateway operates as a config-driven engine that turns JSON into production-grade AI agents. It supports multi-agent orchestration, 19+ LLM providers, MCP/A2A protocols, RAG, and persistent memory while maintaining enterprise compliance with the EU AI Act, GDPR, and HIPAA.

E.D.D.I supports native protocols including MCP, A2A (Agent-to-Agent), the OpenAI Chat Completions API, Slack, OpenAPI, and OAuth 2.0. The system includes a Manager dashboard and Chat UI built-in. When running locally, everything is served from one port (`http://localhost:7070`), which opens a chooser between the Manager (admin dashboard) at `/manage`, the Workforce workspace (group conversations) at `/workforce`, and the standalone chat UI at `/chat`. The wizard auto-generates a unique vault encryption key for secret management.

## ⚙️ Key details
- **Tyk Gateway:** Supports REST, GraphQL, TCP, gRPC, and MCP.
- **E.D.D.I:** Built on Java 25 and Quarkus.
- **Compliance:** EU AI Act, GDPR, HIPAA.
- **Protocols:** MCP, A2A, OpenAI Chat Completions API, Slack, OpenAPI, OAuth 2.0.
- **Testing:** E.D.D.I maintains 20,000+ tests with >90% instruction and >80% branch coverage.

## 🚀 Availability
There are three different ways to try Tyk:

| Offering | Description |
| :--- | :--- |
| **Tyk Open Source** | Run with Docker in under 2 minutes. Requires Docker and Docker Compose. Use `docker compose up -d` to start. |
| **Tyk Self-Managed** | Enterprise API Management platform on your infrastructure. Uses Tyk Install to run Gateway, Dashboard, Portal, Pump, Redis, and PostgreSQL via Docker Compose. Requires a license. |
| **Tyk Cloud** | Hosted Enterprise API Management SaaS. Tyk hosts and manages the full stack; no installation required. Free trial available. |

For E.D.D.I, the fastest setup is a one-command installer that sets up EDDI and a chosen database via Docker Compose. On Linux, use `curl -fsSL https://raw.githubusercontent.com/labsai/EDDI/main/install.sh | bash`. On Windows PowerShell, use `Invoke-WebRequest` to download and run `install.ps1`. The installer supports flags such as `--defaults`, `--db=postgres --with-auth`, and `--full`.

Updates are handled via `eddi update`, which pulls the latest Docker image from the registry and restarts containers, ensuring the remote digest is checked for changes even if the tag remains the same.

#Tyk #APIGateway #AIagents #MCP #EDDI #MultiAgent

---

*Source: [TykTechnologies/tyk](https://github.com/TykTechnologies/tyk)*
*Source: [labsai/EDDI](https://github.com/labsai/EDDI)*
*Source: [OpenPipe/ART](https://github.com/OpenPipe/ART)*
