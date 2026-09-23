---
title: "AWS Labs releases TOLAP: Open‑source tool‑object level access control"
slug: "aws-labs-releases-tolap-opensource-toolobject-level-access-control"
description: "TOLAP (Tool‑Object Level Access Protocol) is now available as an open‑source project under Apache‑2.0. It provides a specification and libraries that let teams enforce fine‑grained access policies at..."
date: 2026-09-23T18:02:56+05:30
tags: [TOLAP, AccessControl, AIAgents, OpenSource]
categories: ["AI", "Security", "AI Agents", "Software Development", "Open Source"]
image: "https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/21/Screenshot-2026-09-21-at-10.53.24 AM-1131x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# AWS Labs releases TOLAP: Open‑source tool‑object level access control

TOLAP (Tool‑Object Level Access Protocol) is now available as an open‑source project under Apache‑2.0. It provides a specification and libraries that let teams enforce fine‑grained access policies at the data source.

## 🔍 Overview
- "Tool‑Object Level Access Protocol (TOLAP) closes that gap."
- Role‑based access control answers whether a user can reach a resource, while attribute‑based access control evaluates policy at a centralized engine.
- Database row‑level security is genuinely enforcement at the source — and it’s worth using.
- Guardrails constrain what the model says, and agent frameworks such as Amazon Bedrock Agents, Azure AI Agent Service, Google Vertex AI Agents, and LangChain authorize whether the agent may invoke a tool.

## 🧩 How it works
- Policy is applied where the data originates, not in a layer above it.
- "The tool wraps the data source and enforces before anything crosses the boundary."
- Policies name individual data objects — columns, rows, fields, tags, endpoints, HTTP methods, similarity thresholds, storage prefixes, result limits.
- The calling agent needs no security‑aware code.
- "Your code fetches the data; TOLAP decides what may leave."

## ⚙️ Key details
| Component | Description |
|---|---|
| Versioned policy schema | Three layers: definition, assignment (links to user or group with scope and expiry), and merged effective policy that actually gets enforced. One schema spans databases, APIs, knowledge bases, and object storage. |
| Normative specification | Defines canonical signing, the enforcement pipeline order, and the fail‑closed rules. |
| SDKs ( .NET, Python, TypeScript ) | Each ships a core, store and enforcement package; core packages have zero external dependencies in all three languages. |
| Reference policy server & authoring console | For teams who’d rather run a policy service than build one. |
| Integrations | Fourteen tested integrations across the three languages, including MCP SDK, Strands, LangChain, LangChain.js, Vercel AI SDK, Mastra, OpenAI Agents, Pydantic AI, Semantic Kernel, and Bedrock Agents. |

- TOLAP is not an MCP server and does not speak the MCP protocol.
- It provides enforcement around the function your tool layer already calls.

## 🚀 Availability
- "Today it’s available as open source under Apache-2.0 at github.com/awslabs/tolap."
- The repository contains the five items listed above and fourteen worked integrations with popular agent frameworks.

## 💡 Why it matters
- Row‑level security and guardrails are essential for safe AI‑driven applications.
- Agent frameworks need a way to authorize tool invocations; TOLAP supplies that capability.
- By delivering a shared specification and ready‑made libraries, "every team doesn’t have to solve it from scratch," accelerating secure AI development.


#TOLAP #AccessControl #AIAgents #OpenSource

---

*Source: [Introducing TOLAP: object-level access control for AI agent tools | Amazon Web Services](https://aws.amazon.com/blogs/opensource/introducing-tolap-object-level-access-control-for-ai-agent-tools/)*
