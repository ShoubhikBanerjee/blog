---
title: "Serverless Model Context Protocol Server Enables Shared Enterprise Data Access for AI Agents"
slug: "serverless-model-context-protocol-server-enables-shared-enterprise-data-access-for-ai-agents"
description: "Organizations building applications powered by artificial intelligence (AI) face a recurring challenge: giving large language model (LLM) agents access to enterprise data lakes without duplicating..."
date: 2026-11-07T18:01:21+05:30
tags: [AIAgents, ModelContextProtocol, AWS, EnterpriseData]
categories: ["AI", "Artificial Intelligence", "Enterprise Computing", "Cloud Services", "Data Engineering"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-20343-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Serverless Model Context Protocol Server Enables Shared Enterprise Data Access for AI Agents

Organizations building applications powered by artificial intelligence (AI) face a recurring challenge: giving large language model (LLM) agents access to enterprise data lakes without duplicating integration logic across every agent and application.

## 🔍 Overview
- "Most teams begin by wiring agents directly to databases and APIs, with no shared gateway such as a Model Context Protocol (MCP) server in between."
- Each new dataset demands custom code, and each agent reimplements its own access control.
- As the number of datasets or agents grows, permission enforcement drifts, and onboarding a new data source becomes a multi‑day engineering effort.
- Our team supports Amazon’s North America Sort Center (NASC) network, where planning teams rely on operational data to manage capacity, labor, and package flow.
- To give those teams conversational access to that data, we built a serverless Model Context Protocol (MCP) server on Amazon Elastic Container Service (Amazon ECS) with AWS Fargate.

## 🧩 How it works
1. **Client layer** – users submit a query from a client application (web chat, Slack, an IDE plugin, or an external agent). The request resolves through Amazon Route 53, reaches an Application Load Balancer in a public subnet (HTTPS + AWS WAF), then routes to Amazon Cognito for authentication and enrichment. Authenticated traffic enters a private subnet where the client layer runs on Amazon ECS Fargate, stores session state in Amazon DynamoDB, and forwards requests through an internal ALB to the MCP server layer.
2. **MCP server layer** – an AI agent powered by Amazon Bedrock orchestrates tools built with FastMCP (a Python framework for building MCP servers). Amazon Bedrock Guardrails is applied to every model interaction.
3. **Tools layer** – Amazon Athena and Amazon Redshift execute SQL against the data lake; Amazon Bedrock Knowledge Bases (RAG) handles semantic search. AWS Lambda ingests data into Amazon S3 and the knowledge bases.
4. **Knowledge‑base refresh layer** – a metadata catalog stores schema descriptions, column‑level semantics, and table relationships. It is refreshed continuously, indexing new dataset metadata as it arrives.
5. When a context specifies tables, the MCP server narrows its search of the metadata catalog to those tables, reducing noise and improving SQL generation accuracy.

## ⚙️ Key details
- "Adding a dataset requires only a metadata file, not code."
- Access control is enforced at the MCP server layer, providing a single audit point.
- The metadata catalog underpins the tools layer, allowing the agent to derive schema knowledge at query time – no hard‑coded table structures or redeployment when schemas change.
- The architecture separates concerns into four layers (client, MCP server, tools, and knowledge‑base refresh), each independently scalable and deployable.
- In testing, this scoping keeps end‑to‑end interaction latency in the **15–20 second range**.
- The data lake contains **thousands of datasets** spanning operational metrics, business analytics, and domain‑specific data.

## 🚀 Availability & Deployment
- The MCP server is deployed serverlessly on Amazon ECS Fargate, eliminating the need for provisioned servers.
- Public‑to‑private subnet routing ensures secure handling of authenticated traffic.
- Amazon Route 53, Application Load Balancers, AWS WAF, Amazon Cognito, DynamoDB, Athena, Redshift, Bedrock Guardrails, and Lambda are all managed services that contribute to a fully managed solution.
- FastMCP provides the framework for building MCP servers in Python, and Amazon Bedrock supplies the underlying LLM capabilities.

This implementation removes duplicated integration code, centralizes access control, and shortens onboarding of new datasets from multi‑day efforts to a simple metadata file drop.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-20343-1.jpeg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-20343-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/04/ML-20343-3.jpg)

#AIAgents #ModelContextProtocol #AWS #EnterpriseData

---

*Source: [Serverless MCP server for AI agent data lake access on Amazon ECS Fargate | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/serverless-mcp-server-for-ai-agent-data-lake-access-on-amazon-ecs-fargate/)*
