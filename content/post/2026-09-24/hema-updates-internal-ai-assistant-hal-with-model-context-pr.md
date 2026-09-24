---
title: "HEMA Updates Internal AI Assistant HAL with Model Context Protocol"
slug: "hema-updates-internal-ai-assistant-hal-with-model-context-protocol"
description: "The 100-year-old Dutch retailer HEMA has updated HAL, its internal AI assistant, by incorporating Model Context Protocol (MCP) and Amazon Bedrock AgentCore to consolidate fragmented organizational..."
date: 2026-09-24T22:03:57+05:30
tags: [HEMA, AmazonBedrock, MCP, AIagents, DigitalTransformation]
categories: ["AI", "AI Agents", "Enterprise Software", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/21/ML-21352-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# HEMA Updates Internal AI Assistant HAL with Model Context Protocol

The 100-year-old Dutch retailer HEMA has updated HAL, its internal AI assistant, by incorporating Model Context Protocol (MCP) and Amazon Bedrock AgentCore to consolidate fragmented organizational knowledge into a governed source of truth.

## 🔍 Overview
HEMA, which operates over 750 stores across multiple countries, utilized a technology organization of engineers, product owners, and business analysts to build a knowledge layer. The project focuses on two primary goals:
* **HAL:** Consolidate fragmented knowledge into one governed source of truth.
* **MCP:** Deliver that knowledge to people within the tools they already use, such as the HAL chat, Kiro, Claude, and other agents, rather than requiring them to visit separate portals.

## 🧩 How it works
HEMA built a knowledge layer on Amazon Bedrock AgentCore, a platform used to build, connect, and optimize agents at scale. The system integrates several components:

| Component | Function |
| :--- | :--- |
| **Model Context Protocol (MCP)** | Provides a standardized interface between AI clients and backend capabilities, allowing sources to be exposed as MCP tools. |
| **Gateway** | Directly turns AWS Lambda functions and OpenAPI specifications into MCP tools without requiring custom MCP server code. |
| **Identity** | Provides managed outbound OAuth2 (a token vault) to internal APIs and managed inbound JSON Web Token (JWT) authentication. |
| **Runtime** | Hosts the internal agent, built with the Strands framework, as a container. |
| **Memory & Guardrails** | Amazon Bedrock Guardrails and Memory provide content filtering and conversation memory with Dutch-language support and EU inference regions. |

## ⚙️ Key details
* **Data Sources:** The system uses a service catalog that maps people to teams, teams to services, services to APIs, and business capabilities. It also imports structured data from data-mesh tables and the product information management (PIM) engine.
* **Security:** Security is anchored in Microsoft Entra ID with no AWS credentials on the client. Access control is driven by existing Active Directory groups.
* **Evolution:** The first version of HAL was a self-contained assistant consisting of a Next.js web chat UI and a Strands agent packaged as a Linux/ARM64 container. The current architecture allows MCP-compatible clients to consume the same tools without custom work.

## 💡 Why it matters
Finding answers that previously required navigating three or four portals over an entire afternoon now happens in seconds from within a chat window or Integrated Development Environment (IDE). This architecture serves as the foundation for the next step: evolving HAL from a read-only knowledge layer into an action layer.

#HEMA #AmazonBedrock #MCP #AIagents #DigitalTransformation

---

*Source: [From portal-hopping to instant answers: HEMA’s journey with MCP and Amazon Bedrock | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/from-portal-hopping-to-instant-answers-hemas-journey-with-mcp-and-amazon-bedrock/)*
