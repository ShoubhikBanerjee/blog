---
title: "Yuxi Launched as a Multi-Tenant Private Knowledge Intelligent Agent Platform"
slug: "yuxi-launched-as-a-multi-tenant-private-knowledge-intelligent-agent-platform"
description: "Yuxi is a multi-tenant knowledge intelligent agent platform designed for private deployment. It integrates knowledge base retrieval, knowledge graphs, LangGraph multi-agent orchestration, MCP/Skills,..."
date: 2026-09-10T22:04:27+05:30
tags: [Yuxi, AIagents, RAG, KnowledgeGraph, PrivateDeployment]
categories: ["AI", "AI Agents", "Knowledge Management", "Software Development"]
image: "https://avatars.githubusercontent.com/u/35524243?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Yuxi Launched as a Multi-Tenant Private Knowledge Intelligent Agent Platform

Yuxi is a multi-tenant knowledge intelligent agent platform designed for private deployment. It integrates knowledge base retrieval, knowledge graphs, LangGraph multi-agent orchestration, MCP/Skills, sandbox tools, and permissions management within a single workspace.

## 🔍 Overview

Users can utilize Yuxi for the following primary functions:
* **Knowledge Q&A**: Upload documents that are parsed, chunked, and vector-indexed to allow agents to answer questions based on retrieved content.
* **Multi-step Task Execution**: Combine tools, MCP, Skills, sub-agents, and sandboxes to produce files that can be previewed and downloaded.
* **Knowledge Graph Integration**: Extract entities and relations from Milvus knowledge base document blocks and write them into Neo4j for use in retrieval.
* **Team Management**: Manage knowledge bases, agents, Skills, and models by user, department, and sharing scope.

## 🧩 How it works

### Document Processing and Retrieval

| Feature | Detail |
| :--- | :--- |
| Supported Formats | PDF, Word, PPT, Excel, Markdown |
| Parsing Engines | MinerU, PaddleX, RapidOCR |
| External Connections | Dify, Notion |
| RAG Tuning | Configurable Embedding and Rerank algorithms with multi-way recall testing |

### User Interaction and Execution

* **Interface**: Users can reference knowledge base documents, personal files, or extended Skills in one conversation interface using the `@` symbol.
* **Transparency**: The system displays task decomposition steps, tool call status, context token consumption, and the agent's thinking chain, step plans, and sub-task status for asynchronous tasks.
* **Safety**: Human approval via confirmation cards is required for critical operations, such as modifying files or calling high-risk external interfaces.
* **Delivery**: The system automatically summarizes results and provides an interactive delivery entrance upon task completion.

## ⚙️ Key details

* **Version**: The current repository default configuration corresponds to v0.7.3.
* **Initialization**: The initialization script creates a `.env` file, reads the SiliconFlow API Key, and generates secure keys for JWT, API Key derivation, and the Sandbox provisioner.
* **API Documentation**: Available at `http://localhost:5050/docs`.
* **Evaluation Tools**: Includes a built-in RAG effect evaluation tool for quantifying retrieval and answer quality, as well as support for Langfuse Dataset to evaluate full agent tasks.

#Yuxi #AIagents #RAG #KnowledgeGraph #PrivateDeployment

---

*Source: [xerrors/Yuxi](https://github.com/xerrors/Yuxi)*
