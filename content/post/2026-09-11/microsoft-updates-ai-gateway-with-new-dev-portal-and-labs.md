---
title: "Microsoft Updates AI Gateway with New Dev Portal and Labs"
slug: "microsoft-updates-ai-gateway-with-new-dev-portal-and-labs"
description: "Microsoft has released an update to the AI Gateway powered by Azure API Management and Microsoft Foundry, introducing a new AI Gateway Dev Portal and over 30 hands-on labs for exploring AI models,..."
date: 2026-09-11T06:05:05+05:30
tags: [Azure, AIGateway, MCP, LLM, AIModels]
categories: ["AI", "Cloud Computing", "AI Infrastructure", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/1844662?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft Updates AI Gateway with New Dev Portal and Labs

Microsoft has released an update to the AI Gateway powered by Azure API Management and Microsoft Foundry, introducing a new AI Gateway Dev Portal and over 30 hands-on labs for exploring AI models, MCP servers, and agents.

## 🔍 Overview
Building production-ready AI applications requires security, reliability, observability, and cost control. The AI Gateway provides a way to manage and control access to Large Language Models using enterprise-grade policies.

## ⚙️ Key details

| Capability | Features |
| :--- | :--- |
| **Security** | OAuth 2.0, managed identities, content safety filtering |
| **Performance** | Load balancing, semantic caching, request routing |
| **Observability** | Token metrics, built-in logging, tracing |
| **Cost Control** | Rate limiting, quota management, FinOps framework |
| **Extensibility** | MCP protocol support, function calling, multi-model routing |

Additional technical capabilities include:
- Distributing requests across multiple model endpoints
- Caching responses using vector similarity for faster, cheaper completions
- Routing requests to different backends based on model and version
- Managing AI budgets with automated quota controls
- Implementing MCP with the client authorization flow

## 🧩 How it works
The available labs consist of Jupyter notebooks that include Bicep infrastructure templates and APIM policies for deployment to an Azure subscription. Users can launch these notebooks via GitHub Codespaces or by selecting the .venv interpreter created by `uv sync` as the Jupyter kernel. The `tools/` folder includes utilities for development and testing, such as invoking AI Foundry APIs with tracing enabled.

## 🚀 Availability
Users can browse more than 30 labs at aka.ms/ai-gateway/labs. The AI Gateway Dev Portal is now live as a starting point for building developer portals on top of Azure API Management AI Gateway.

## 💡 Why it matters
The AI Gateway allows for the integration of various tools and models, including:
- Google Gemini models with MCP tools
- OpenAI Agents with Azure OpenAI and APIM-managed tools
- Realtime voice API combined with MCP tools
- Foundry Agent Service with multi-service control
- OpenAI function calling with an Azure Functions backend

#Azure #AIGateway #MCP #LLM #AIModels

---

*Source: [Azure-Samples/AI-Gateway](https://github.com/Azure-Samples/AI-Gateway)*
