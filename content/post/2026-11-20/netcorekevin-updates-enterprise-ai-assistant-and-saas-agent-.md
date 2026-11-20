---
title: "NetCoreKevin Updates Enterprise AI Assistant and SaaS Agent Platform"
slug: "netcorekevin-updates-enterprise-ai-assistant-and-saas-agent-platform"
description: "NetCoreKevin has introduced an update for building AI assistants and SaaS agent platforms within enterprise intranets, providing foundational features such as multi-tenancy, login authentication,..."
date: 2026-11-20T14:26:01+05:30
tags: [NetCoreKevin, DotNet, AIAgents, RAG, EnterpriseAI]
categories: ["AI", "Artificial Intelligence", "Software Development", "Enterprise Software"]
image: "https://avatars.githubusercontent.com/u/57887866?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# NetCoreKevin Updates Enterprise AI Assistant and SaaS Agent Platform

NetCoreKevin has introduced an update for building AI assistants and SaaS agent platforms within enterprise intranets, providing foundational features such as multi-tenancy, login authentication, permission points, audit logs, scheduled tasks, and model integration.

## 🔍 Overview
- Designed for enterprise intranet AI assistant and SaaS agent platform scenarios.
- Not a scaffold demo: includes pre-built dependencies, database migration support, login management, menus, permissions, scheduled tasks, and audit logs.
- Containerized deployment supported via Docker Compose to spin up the frontend, backend, MySQL, Redis, and Qdrant with a single command, alongside individual Dockerfiles for frontend and backend.

## 🧩 Architecture and Tech Stack
- **Backend**: Built on .NET 10, EF Core 10, and MySQL, split into Domain, Application, RepositorieRps, and WebApi layers with v1 and v2 API versions.
- **AI Capabilities**: Integrated within `Kevin/kevin.Module`. Uses `kevin.AI.AgentFramework` based on Microsoft Agent Framework, and `kevin.RAG` for text splitting, vectorization, and reranking in the same process without requiring an external Python service.
- **Management Frontend**: `vue/kevin.web.vue` built with Vue 3 and Ant Design Vue for configuring tenants, users, roles, agents, knowledge bases, skills, tasks, and API keys.
- **Modular Base**: Features 25 pluggable modules (each as a csproj) registered via `IModuleInitializer` and `IModuleConfigTasks` without modifying entry files, including permissions, caching, message queues, distributed locks, SignalR, Hangfire, object storage, SMS, email, and a code generator.

## ⚙️ Key Features and Capabilities
- **Prompt, Model, and Parameter Configuration**: Individual configuration per agent, separating chat models from vector models, with adjustable temperature and context cropping.
- **Dynamic Skill Loading**: Skills combine `SKILL.md` with scripts (`.py`, `.ps1`, `.sh`), allowing creation, online editing, and activation or deactivation without recompilation.
- **RAG Knowledge Base**: Uploaded documents are automatically split and written to Qdrant, with retrieval results processed by `qwen3-rerank` before feeding into the model.
- **Memory**: Isolated in Qdrant by tenant, agent, and user dimensions, with a toggle switch on individual agents.
- **Multi-Agent Collaboration**: Main agents can delegate sub-tasks to other agents.
- **Context Compression**: Compresses historical messages based on configuration thresholds.
- **Web Search**: Integrated with Doubao search from Volcano Engine for fetching new information.
- **Multimodal Support**: Handles image understanding, speech transcription (Aliyun ASR), and text-to-image generation with automatic OSS upload.
- **Tenancy and Security**: Single-database multi-tenancy using shared libraries isolated by `TenantId` with interface-level forced filtering; RBAC permissions across menu and API dimensions tied to roles, with a toggle for debugging via `IsOpenPermission`.
- **Quotas and Auditing**: Monthly token quotas issued via scheduled tasks and deducted on requests; built-in audit logs, slow query alerts, and environment-specific file logging.
- **OpenAI Protocol Compatibility**: Supports `GET /v1/models` and `POST /v1/chat/completions` (including stream) via endpoints compatible with clients like Cherry Studio, Dify, and custom clients using a `sk-` prefixed key.
- **MCP Support**: `App/WebApiMcp` provides an MCP server, allowing configuration to wrap existing HTTP interfaces into MCP tools or connect external MCP services as agent tools.
- **Integration Ecosystem**: Object storage supporting Tencent Cloud, Aliyun, and Qiniu; SMS via Tencent and Aliyun; DingTalk messages; RabbitMQ and CAP message buses; Consul service discovery; and SignalR real-time push.

#NetCoreKevin #DotNet #AIAgents #RAG #EnterpriseAI

---

*Source: [junkai-li/NetCoreKevin](https://github.com/junkai-li/NetCoreKevin)*
