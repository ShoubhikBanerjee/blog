---
title: "Bayer launches Agentic Decision Engine to simplify ML workflow queries"
slug: "bayer-launches-agentic-decision-engine-to-simplify-ml-workflow-queries"
description: "Bayer Crop Science has added the Agentic Decision Engine (ADE), a multi‑agent natural‑language interface that sits on top of its Connected Decision Engine (CDE) and runs on Amazon Bedrock AgentCore...."
date: 2026-10-23T22:04:00+05:30
tags: [Bayer, AIAgents, MachineLearning, AWS]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing", "Agriculture Technology"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/23/How-Bayer-Crop-Science-built-an-agentic-decision-engine-on-Amazon-Bedrock-AgentCore-with-AWS-Unified-Operations.png"
author: "Shoubhik Banerjee"
draft: false
---

# Bayer launches Agentic Decision Engine to simplify ML workflow queries

Bayer Crop Science has added the Agentic Decision Engine (ADE), a multi‑agent natural‑language interface that sits on top of its Connected Decision Engine (CDE) and runs on Amazon Bedrock AgentCore. ADE lets breeders, analysts, researchers, data scientists and data engineers ask questions about ML workflows in plain language and receive answers without navigating the underlying operational stack.

## 🔍 Overview
- Plant breeding decisions depend on data that spans genomics, field trials, imagery, environmental conditions, and model outputs.
- Bayer’s Connected Decision Engine (CDE) deploys, orchestrates, monitors and reuses hundreds of ML model configurations across crops, regions and teams while preserving execution history and operational controls.
- As CDE adoption grew, the bottleneck shifted from running workflows to understanding them. Users had to piece together context from APIs, documentation, metadata stores, dashboards and logs.
- The Agentic Decision Engine (ADE) was built to close that gap with a natural‑language, multi‑agent interface.

## 🧩 Problem
- Explaining a result required knowing which system held the relevant information.
- Users needed to know where to inspect when a workflow failed, what a model did, or where a result originated.

## ⚙️ Architecture
ADE is organized into four layers:
1. **User experience** – React web front end with identity proxy for Microsoft Entra ID.
2. **Agent orchestration** – GitHub Actions builds container images, pushes to Amazon ECR, and deploys to the AgentCore runtime. LangGraph provides explicit graph‑based control flow and checkpointing.
3. **Specialist agents** – Supervisor Agent routes each question to a specialist agent; specialist agents retrieve context from the appropriate backend system.
4. **Tools & data sources** –
   - Amazon DynamoDB stores LangGraph checkpoint state.
   - Amazon Aurora PostgreSQL stores session records, user feedback and analytics.
   - Amazon ElastiCache caches agent responses (TTL).
   - Amazon S3 holds domain content embedded with Amazon Titan Text Embeddings V2 and indexed in Amazon OpenSearch Serverless for Retrieval‑Augmented Generation.
   - Amazon CloudWatch captures runtime and application telemetry.
   - AgentCore Gateway exposes backend APIs to agents as Model Context Protocol (MCP) tools, keeping authentication and authorization outside agent code via IAM‑scoped access.

## 🚀 Capabilities
- Natural‑language interface over CDE.
- Supervisor agent classifies requests, selects a specialist, and aggregates results when a question spans domains.
- In its first phase, ADE resolves about **80 %** of user questions without an engineer in the loop.
- Runs on Amazon Bedrock AgentCore, which provides:
  - Managed runtime that isolates each user session.
  - IAM‑scoped tool access through AgentCore Gateway.
  - Framework‑agnostic design allowing use of LangGraph and any model.

## 🤝 Collaboration & Operations
- Bayer engaged AWS Unified Operations for launch and ongoing support.
- A designated Technical Account Manager (TAM) provided strategic advice aligned with Bayer’s operating model and business priorities.
- A generative AI Domain Specialist Engineer (DSE) contributed AWS generative‑AI expertise and built knowledge of the ADE workload.
- The team held three technical stand‑ups each week to review design decisions.

## 💡 Why it matters
- Gives breeders and data teams a consistent way to run analytics while preserving execution history and operational controls.
- Reduces the need for engineers to manually trace workflow failures or model behavior.
- Accelerates decision‑making in plant breeding by making complex ML context accessible through simple language queries.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21834-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21834-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21834-3.jpg)

#Bayer #AIAgents #MachineLearning #AWS

---

*Source: [How Bayer Crop Science built an agentic decision engine on Amazon Bedrock AgentCore with AWS Unified Operations | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-bayer-crop-science-built-an-agentic-decision-engine-on-amazon-bedrock-agentcore-with-aws-unified-operations/)*
