---
title: "Azure Foundry Introduces Knowledge Bases and Toolboxes for AI Agents"
description: "Foundry has introduced new capabilities for AI agents, specifically Foundry IQ for knowledge management and Toolboxes for integrated tool orchestration. These developments focus on optimizing context..."
date: 2026-09-03T22:06:46+05:30
tags: [Azure, Foundry, AIAgents, MachineLearning, DataRetrieval]
categories: [AI]
image: "https://azure.microsoft.com/en-us/blog/wp-content/uploads/2026/09/Foundry-Economics-Series_3.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Azure Foundry Introduces Knowledge Bases and Toolboxes for AI Agents

Foundry has introduced new capabilities for AI agents, specifically Foundry IQ for knowledge management and Toolboxes for integrated tool orchestration. These developments focus on optimizing context window usage and improving retrieval efficiency.

## 🧩 How it works

Foundry IQ improves retrieval by decomposing agent queries into subqueries and performing parallel searches across connected data sources. It then semantically reranks results and returns grounded passages with citations. The system integrates with a variety of data sources:

| Source | Description |
| :--- | :--- |
| Work IQ | Knowledge base source |
| Fabric IQ | Knowledge base source |
| Web IQ | Knowledge base source |
| Microsoft Azure Blob Storage | Knowledge base source |
| SharePoint | Knowledge base source |
| OneLake | Knowledge base source |
| Azure SQL | Knowledge base source |

Toolboxes manage agent tools via a single Model Context Protocol (MCP) endpoint. Rather than providing a model with a full list of tools, which consumes context window tokens, the system provides a plain language description of needs and a mechanism to call the relevant tool. This keeps the cost of the tool list flat regardless of library size.

## ⚙️ Key details

- Foundry IQ performs access control by running under the caller’s Microsoft Entra identity, synchronizing access-control lists, and honoring Microsoft Purview sensitivity labels.
- A single knowledge base can serve multiple agents, and indexed sources support incremental refreshing.
- Toolboxes support built-in tools, custom MCP servers, OpenAPI 3.0 and 3.1 APIs, and A2A agents.
- Foundry manages authentication, access policies, and tool versions centrally, allowing agents to use updated tools without code changes or redeployment.

## 💡 Why it matters

Internal evaluations of Foundry IQ showed an improvement in evidence recall of up to 54% on the BrowseComp-Plus benchmark and a 34% reduction in retrieval token costs. Additionally, Toolboxes reduced average input-token consumption by approximately 97% for large tool libraries in internal benchmarks.

![figure](https://azure.microsoft.com/en-us/blog/wp-content/uploads/2026/08/Foundry-Economics-Series_2.jpg)

![figure](https://azure.microsoft.com/en-us/blog/wp-content/uploads/2026/08/Foundry-Economics-AI-Managed-1.jpg)

![figure](https://azure.microsoft.com/en-us/blog/wp-content/uploads/2026/08/Azure-Foundry-AI-at-Scale-3.jpg)

#Azure #Foundry #AIAgents #MachineLearning #DataRetrieval

---

*Source: [AI agent optimization: How context engineering lowers AI costs | Microsoft Azure Blog](https://azure.microsoft.com/en-us/blog/the-economics-of-agent-optimization-context-engineering-for-enterprise-ai-agents/)*
