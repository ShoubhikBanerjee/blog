---
title: "LiteLLM Open Source AI Gateway Launches for 100+ LLM Providers"
description: "LiteLLM, an open source AI Gateway, has been released, offering a unified interface to call over 100 LLM providers, including OpenAI, Anthropic, Gemini, Bedrock, Azure, and more, using the OpenAI..."
date: 2026-08-31T19:35:04+05:30
tags: [LiteLLM, AIgateway, LLM, OpenAI, PythonSDK, ProxyServer]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/121462774?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LiteLLM Open Source AI Gateway Launches for 100+ LLM Providers

LiteLLM, an open source AI Gateway, has been released, offering a unified interface to call over 100 LLM providers, including OpenAI, Anthropic, Gemini, Bedrock, Azure, and more, using the OpenAI format.

## 🔍 Overview
LiteLLM provides a single, centralized interface to interact with multiple LLM providers, eliminating the need for provider-specific SDKs.

## ⚙️ Key details
- Unified API for 100+ LLMs, enabling seamless switching between providers without code changes
- Drop-in OpenAI compatibility
- Production-ready gateway with features such as:
  - Virtual keys
  - Spend tracking
  - Guardrails
  - Load balancing
  - Admin dashboard
- Performance: 8ms P95 latency at 1k requests per second
- Supports all OpenAI endpoints: `/chat/completions`, `/responses`, `/embeddings`, `/images`, `/audio`, `/batches`, `/rerank`, `/a2a`, `/messages`
- Rust core with Python SDK

## 🚀 Availability
- Deployable as a Python SDK for direct library integration
- Deployable as an AI Gateway (Proxy Server) for teams or organizations
- Installation via `uv add litellm`

#LiteLLM #AIgateway #LLM #OpenAI #PythonSDK #ProxyServer

---

*Source: [BerriAI/litellm](https://github.com/BerriAI/litellm)*
