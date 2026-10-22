---
title: "Open Responses API becomes vendor‑neutral standard with AWS Bedrock support"
slug: "open-responses-api-becomes-vendorneutral-standard-with-aws-bedrock-support"
description: "The Open Responses open‑source specification has moved into a vendor‑neutral home under the Agentic AI Foundation (AAIF) and is now implemented at scale by Amazon Bedrock, giving developers a single..."
date: 2026-10-22T22:11:45+05:30
tags: [OpenResponses, AWS, AIAPIs, AgenticAI]
categories: ["AI", "Machine Learning", "AI Infrastructure", "Open Source", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/10/22/Screenshot-2026-10-21-at-10.55.27 AM-1-1146x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# Open Responses API becomes vendor‑neutral standard with AWS Bedrock support

The Open Responses open‑source specification has moved into a vendor‑neutral home under the Agentic AI Foundation (AAIF) and is now implemented at scale by Amazon Bedrock, giving developers a single API format for calling language models, streaming results, and orchestrating tool use.

## 🔍 Overview
- The API format that a growing number of model providers use to call language models now has a vendor‑neutral home.\
- Open Responses joined the Agentic AI Foundation (AAIF) as a project, bringing it under open governance alongside MCP and A2A.\
- Open Responses is an open source specification that defines a single API format for calling language models, streaming results, and orchestrating tool use.\
- AWS is involved in Open Responses and employs a core maintainer on the project; Amazon Bedrock already supports the Responses API across dozens of models.

## 🧩 How it works
- **Common request/response model** – one schema for structured inputs and outputs that works across OpenAI, Anthropic, Gemini, local models, and any provider that implements the spec.\
- **Agentic loop** – a unified pattern for models to emit tool calls, receive results, and continue reasoning, whether tools are developer‑hosted or provider‑hosted.\
- **Items as the atomic unit of context** – a clear schema for messages, tool invocations, and reasoning state, with defined state machines (`in_progress`, `completed`, `failed`) for predictable behavior.\
- **Semantic streaming events** – meaningful event types like `response.output_text.delta` and `response.completed` rather than raw text deltas, so clients can be built once and work across providers.\
- **Extensibility without fragmentation** – provider‑specific tools and item types are namespaced with provider slugs, keeping the portable core clean while preserving room for innovation.

## ⚙️ Key details
- OpenAI pioneered the Responses API for stateful conversations that call external tools or functions.\
- Anthropic’s Messages API and Google’s Gemini API use different conventions; Open Responses standardizes these concepts with versioning, compliance tests, and extensibility rules.\
- AWS is a member of the AAIF Governing Board and contributes to Open Responses’ development as an AAIF project.\
- By housing Open Responses under AAIF alongside MCP and A2A, the specification evolves through community consensus, not any single company’s product roadmap.\
- Bedrock’s implementation provides a production‑grade reference for how the spec works at scale.

## 🚀 Availability
- Amazon Bedrock has supported the Responses API since December 2025 and continues to expand its implementation.\
- Developers can use the familiar OpenAI SDK to call models hosted on Bedrock simply by changing the base URL and API key.\
- Bedrock’s Responses API support includes:
  - Stateful conversation management via `previous_response_id` (no need to pass the full conversation history with each request).
  - Built‑in tool use for agentic workflows, including developer‑hosted and server‑side custom tools (server‑side tool support added in January 2026).
  - Streaming and non‑streaming modes across both `bedrock-runtime` and `bedrock-mantle` endpoints.
  - Broad model availability – the Responses API works with models from Amazon, Anthropic, Meta, Mistral, OpenAI, DeepSeek, Google, and others, all through the same API format.
- Existing applications built against the OpenAI Responses API can run on Bedrock with minimal changes, gaining access to Bedrock’s features such as Guardrails, cross‑Region inference, and intelligent prompt routing while keeping the same client code.
- Recent additions include WebSocket transport for persistent connections and a compaction endpoint for managing long conversation contexts.

## 💡 Why it matters
- **For developers** – one schema and compliance tests mean integration code can be written once and reused across providers.\
- **For model providers and inference platforms** – Open Responses gives a clear specification to implement, avoiding the need to learn multiple proprietary APIs.\
- **Community governance** – the AAIF framework ensures the spec evolves through consensus, fostering interoperability across the rapidly expanding landscape of language‑model providers.

![figure](https://d1.awsstatic.com/onedam/marketing-channels/website/aws/en_US/global-nav/aws-library_illustration_innovation_8_1200.07a6484f8eaa3100138cf8b6dce14f1db024db32.jpg)

#OpenResponses #AWS #AIAPIs #AgenticAI

---

*Source: [Open Responses Joins AAIF with AWS Support | Amazon Web Services](https://aws.amazon.com/blogs/opensource/open-responses-joins-aaif-with-aws-support/)*
