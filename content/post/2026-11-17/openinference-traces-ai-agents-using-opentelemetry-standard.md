---
title: "OpenInference Traces AI Agents Using OpenTelemetry Standard"
slug: "openinference-traces-ai-agents-using-opentelemetry-standard"
description: "OpenInference is a specification that builds on OpenTelemetry to trace AI agents, including their LLM calls, tool use, retrieval, and reasoning steps. It defines how AI applications are recorded as..."
date: 2026-11-17T12:12:52+05:30
tags: [OpenInference, OpenTelemetry, AIObservability, LLM, AgentFrameworks]
categories: ["AI", "AI Agents", "Observability", "Developer Tools", "Large Language Models"]
image: "https://avatars.githubusercontent.com/u/59858760?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# OpenInference Traces AI Agents Using OpenTelemetry Standard

OpenInference is a specification that builds on OpenTelemetry to trace AI agents, including their LLM calls, tool use, retrieval, and reasoning steps. It defines how AI applications are recorded as OpenTelemetry traces, ensuring that instrumentation follows a consistent standard regardless of the framework or language used.

## 🔍 Overview
- The specification defines which span kinds mark LLM calls, agents, tools, retrievers, and embeddings.
- It specifies which attributes hold inputs, outputs, token counts, and metadata.
- Instrumentation follows the specification so that traces read the same whichever framework or language produced them.

## 🧩 How it works
- OpenInference builds on OpenTelemetry to capture the execution flow of AI agents.
- Instrumentation libraries automatically trace popular model providers and agent frameworks.
- The system records specific steps such as LLM calls, tool use, retrieval, and reasoning.

## ⚙️ Key details
- **Natively Supported Tools**:
  - Arize Phoenix
  - Arize AX
- **Backend Compatibility**: Works with any OpenTelemetry-compatible backend.

## 🚀 Availability
- Instrumentation libraries are available for the following languages:
  - Python
  - JavaScript
  - Java
  - Go

#OpenInference #OpenTelemetry #AIObservability #LLM #AgentFrameworks

---

*Source: [Arize-ai/openinference](https://github.com/Arize-ai/openinference)*
