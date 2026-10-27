---
title: "Enterprise agentic retrieval launched for Managed Amazon Bedrock Knowledge Bases"
slug: "enterprise-agentic-retrieval-launched-for-managed-amazon-bedrock-knowledge-bases"
description: "Amazon Bedrock has introduced enterprise agentic retrieval for Managed Knowledge Bases, evolving standard Retrieval Augmented Generation (RAG) into a reasoning-driven system. This update moves beyond..."
date: 2026-10-27T22:02:24+05:30
tags: [AmazonBedrock, AWSCDK, AIagents, RAG, MachineLearning]
categories: ["AI", "Machine Learning", "AI Agents", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21614-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Enterprise agentic retrieval launched for Managed Amazon Bedrock Knowledge Bases

Amazon Bedrock has introduced enterprise agentic retrieval for Managed Knowledge Bases, evolving standard Retrieval Augmented Generation (RAG) into a reasoning-driven system. This update moves beyond single-shot designs to a first-class service capability that uses a reasoning agent for multi-turn planning and tool-driven retrieval.

## 🔍 Overview
Classic RAG systems typically embed a question, fetch chunks from one index, and generate a response in a single turn. Enterprise agentic retrieval addresses several limitations of this design:
* It handles questions spanning two corpora, which previously returned incomplete answers.
* It enables semantic routing, allowing the system to choose the correct knowledge base based on the specific question.
* It allows the system to take a second look at the corpus after reviewing initial results if needed.

## 🧩 How it works
By putting a reasoning agent in the loop, the system decides whether to retrieve, which knowledge base to consult, and whether to refine the search before composing an answer. This process is powered by the AgenticRetrieveStream API, which provides multi-turn planning as a service feature rather than an orchestration layer built by the user.

| Component | Function |
| :--- | :--- |
| Managed Knowledge Base (Type: MANAGED) | Handles ingestion, storage, indexing, and retrieval; includes service-managed embedding and reranking. |
| Amazon Bedrock AgentCore | Provides a Gateway to expose knowledge bases as MCP tools and a Runtime for the reasoning agent. |
| AgenticRetrieveStream API | Performs multi-turn planning, executes retrieval, and returns synthesized, cited answers. |
| Amazon CloudWatch | Monitors behavior across seven layers of telemetry with two provided dashboards. |

## ⚙️ Key details
This solution is delivered as a single AWS CDK application in Python, where one command deploys the entire system. Key technical developments include:
* **Managed Infrastructure:** Amazon Bedrock now offers a Managed Knowledge Base (Type: MANAGED) that owns storage and indexing. Users no longer need to create or pay for OpenSearch Serverless collections or OpenSearch Compute Units (OCUs).
* **Integrated Agentic Loop:** The AgentCore Gateway exposes each knowledge base as a Model Context Protocol (MCP) tool.
* **Observability:** The system includes two Amazon CloudWatch dashboards and supports both on-demand and continuous evaluation from the same deployment.
* **Availability:** Agentic retrieval capabilities are available exclusively on the Managed Knowledge Base.

## 💡 Why it matters
This development simplifies complex RAG implementations. In August 2024, building a RAG solution required manually sequencing CDK stacks for S3, OpenSearch Serverless, and individual data sources. The new managed approach automates these components, replacing raw vector searches with a system that provides grounded, cited answers through internal reranking and automated multi-turn reasoning.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21614-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21614-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/22/ML-21614-3.png)

#AmazonBedrock #AWSCDK #AIagents #RAG #MachineLearning

---

*Source: [Build agentic retrieval on a Managed Amazon Bedrock Knowledge Base with CDK | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-agentic-retrieval-on-a-managed-amazon-bedrock-knowledge-base-with-cdk/)*
