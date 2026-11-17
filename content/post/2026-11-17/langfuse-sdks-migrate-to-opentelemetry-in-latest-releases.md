---
title: "Langfuse SDKs migrate to OpenTelemetry in latest releases"
slug: "langfuse-sdks-migrate-to-opentelemetry-in-latest-releases"
description: "Langfuse has released new versions of its Python and JavaScript/TypeScript SDKs, both rewritten to be built on OpenTelemetry (OTel). The legacy SDK clients are deprecated, and developers are advised..."
date: 2026-11-17T22:09:21+05:30
tags: [Langfuse, OpenTelemetry, Python, JavaScript, LLM]
categories: ["AI", "Generative AI", "Developer Tools", "Observability", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/134601687?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Langfuse SDKs migrate to OpenTelemetry in latest releases

Langfuse has released new versions of its Python and JavaScript/TypeScript SDKs, both rewritten to be built on OpenTelemetry (OTel). The legacy SDK clients are deprecated, and developers are advised to adopt the new instrumentation methods and use the Observations API v2 for querying traces.

## 🧩 How it Works

The new SDKs use OpenTelemetry to handle observability and tracing. For real-time data ingestion, the only supported path is OpenTelemetry, combined with the Observations API v2 and Metrics API v2. 

- **Python**: Use the `langfuse` package with `get_client()`, `start_as_current_observation`, or the `@observe` decorator. Spans are created using context managers and are automatically closed when exiting their blocks.
- **JavaScript/TypeScript**: Use the `@langfuse/tracing` package with `startActiveObservation` or `startObservation`, along with `LangfuseSpanProcessor` from the `@langfuse/otel` package. 

For offline evaluation, regression testing, and prompt management, both SDKs provide dedicated packages (`langfuse` for Python and `@langfuse/client` for JavaScript).

## ⚙️ Key Details

The legacy v2 and v3 client APIs are deprecated. Querying traces using legacy endpoints like `GET /api/public/traces` or `api.traceList` is no longer recommended; developers must use `GET /api/public/v2/observations`.

- **Data Freshness**: All GET APIs other than the OpenTelemetry ingestion path can be up to 10 minutes behind.
- **Python Installation**: Install via `pip install langfuse`.
- **JavaScript Installation**: Install via `npm install @langfuse/tracing @langfuse/otel "@opentelemetry/sdk-node@<0.300"`.
- **Version Requirements**: The JS/TS SDK v6 requires Langfuse Cloud or self-hosted Langfuse v4.59.0 or later. OpenTelemetry JS SDK 2.x is supported; 3.x is not supported yet.

## 🚀 Availability

The new SDKs are available as the latest releases for both platforms, with JavaScript targeting Node.js 22+ for core tracing and OTEL helpers.

| Package | Platform / Environment | Functionality |
| :--- | :--- | :--- |
| `langfuse` | Python | Observability/tracing, datasets & experiments, LLM-as-a-judge, prompt management, full REST API client |
| `@langfuse/client` | Universal JS | Langfuse API client for universal JavaScript environments |
| `@langfuse/browser` | Browser | Langfuse browser SDK for public-key score ingestion |
| `@langfuse/tracing` | Node.js 22+ | Langfuse instrumentation methods based on OpenTelemetry |
| `@langfuse/otel` | Node.js 22+ | Langfuse OpenTelemetry export helpers |
| `@langfuse/openai` | Universal JS | Langfuse integration for OpenAI SDK |
| `@langfuse/langchain` | Universal JS | Langfuse integration for LangChain |
| `@langfuse/vercel-ai-sdk` | Universal JS | Langfuse integration for AI SDK v7 |

#Langfuse #OpenTelemetry #Python #JavaScript #LLM

---

*Source: [langfuse/langfuse-python](https://github.com/langfuse/langfuse-python)*
*Source: [langfuse/langfuse-js](https://github.com/langfuse/langfuse-js)*
