---
title: "Traccia Launches OpenTelemetry-Native SDK for AI Agent Observability and Governance"
slug: "traccia-launches-opentelemetry-native-sdk-for-ai-agent-observability-and-governance"
description: "Traccia has released a production-ready Python SDK designed for observing, evaluating, and enforcing policies on AI agents and LLM applications at runtime. Built on OpenTelemetry, the..."
date: 2026-09-27T18:01:26+05:30
tags: [OpenTelemetry, AIGovernance, LLMOps, Python, AIAgents]
categories: ["AI", "AI Agents", "Observability", "Software Development"]
image: "https://avatars.githubusercontent.com/u/256045371?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Traccia Launches OpenTelemetry-Native SDK for AI Agent Observability and Governance

Traccia has released a production-ready Python SDK designed for observing, evaluating, and enforcing policies on AI agents and LLM applications at runtime. Built on OpenTelemetry, the framework-agnostic SDK provides distributed tracing and governance for AI agents, agentic workflows, and multi-agent systems.

## 🔍 Overview
Traccia provides a set of tools to manage AI agents that can act, specifically controlling what those agents are allowed to do. The SDK is built for OpenAI Agents, LangGraph, CrewAI, and LLM applications in production.

## ⚙️ Key Details

### Core Capabilities
* **LLM-Aware Tracing**: Automatically tracks prompts, completions, latency, tokens, and costs.
* **Automatic Instrumentation**: Auto-patches HTTP libraries, requests, and providers including Gemini (google-genai), Anthropic, and OpenAI.
* **Framework Integrations**: Supports OpenAI Agents SDK, CrewAI, and LangChain.
* **Prompt Management**: Features `load_prompt` and `prefetch_prompts` with cache, fallback, and stale-while-revalidate. Prompts are fetched from the Traccia prompt registry by name and deploy label.
* **Evaluation**: The `evaluate()` function runs scorers and tasks over a dataset to save experiments for comparison and promotion.

### Governance and Security

| Feature | Description |
| :--- | :--- |
| `@govern` | Runtime policy enforcement to deny or reshape tool/LLM calls using Loop Cap, Model Boundary, and Spend Cap |
| Guardrail Detection | Passive detection of custom guardrails, provider-native safeguards, and AI safety controls |
| Security Controls | Configurable data truncation and removal of secrets from logs |
| Compliance | PII/PHI redaction helpers and evidence for HIPAA and EU AI Act transparency and integrity verification |

### Technical Specifications
* **Infrastructure**: OTLP-compatible export to File, Console, SigNoz, Zipkin, Jaeger, and Grafana Tempo.
* **Metrics**: Emits OTEL-compliant metrics for token and cost tracking independent of sampling.
* **Configuration**: Uses Pydantic for type-safe configuration and a simple `init()` call for zero-configuration setup.
* **Performance**: Includes async support, efficient batching, and low-overhead instrumentation.

## 🚀 Availability
Traccia is available on PyPI. Use of tracing and prompt fetching requires a Traccia platform workspace API key created under Settings $\rightarrow$ API Keys, defaulting to `https://api.traccia.ai`.

#OpenTelemetry #AIGovernance #LLMOps #Python #AIAgents

---

*Source: [traccia-ai/traccia-py](https://github.com/traccia-ai/traccia-py)*
