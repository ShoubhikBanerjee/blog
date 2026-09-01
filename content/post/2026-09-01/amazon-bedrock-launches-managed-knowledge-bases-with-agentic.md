---
title: "Amazon Bedrock Launches Managed Knowledge Bases with Agentic Retrieval"
description: "Amazon Bedrock Knowledge Bases has introduced managed knowledge bases, evolving from traditional RAG to agentic retrieval. This new capability enables multi-turn planning, iterative retrieval, and..."
date: 2026-09-01T12:02:28+05:30
tags: [AmazonBedrock, AgenticRetrieval, KnowledgeBases, AWS, RAG, AI]
categories: [AI]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/27/ML-21427-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Launches Managed Knowledge Bases with Agentic Retrieval

Amazon Bedrock Knowledge Bases has introduced managed knowledge bases, evolving from traditional RAG to agentic retrieval. This new capability enables multi-turn planning, iterative retrieval, and grounded answers with citations, all managed by Amazon Bedrock.

## 🔍 Overview
- Amazon Bedrock now offers a Managed Knowledge Base (Type: MANAGED) that handles ingestion, storage, indexing, and retrieval, including embedding and reranking with service-managed models.
- The solution eliminates the need to provision, scale, or patch a vector database.
- It supports multimodal content, including text, vectors, metadata, and structured content like CSV and Excel files.

## 🧩 How it works
- A user sends a question to an agent hosted on the Amazon Bedrock AgentCore runtime.
- The runtime auto-instruments every step with OpenTelemetry spans, making the reason-and-act loop observable from the first call.
- The agent’s reasoning model plans the task and performs cross-knowledge-base routing, selecting the tool (e.g., financial or weather) whose topic matches the question.
- The selected tool call is brokered by the Amazon Bedrock AgentCore Gateway over the Model Context Protocol (MCP), invoking the knowledge base’s `AgenticRetrieveStream` API.
- `AgenticRetrieveStream` decomposes the question into sub-queries, retrieves iteratively from the managed datastore (ingested from corpora in Amazon S3), and synthesizes a grounded, cited answer that streams back through the Gateway.
- The runtime emits spans, token usage, and metrics to Amazon CloudWatch and AWS X-Ray, populating seven observability layers and feeding evaluation scores.

## ⚙️ Key details
- Classic RAG performs one retrieval and one generation, while agentic retrieval uses a reasoning agent to decide whether and what to retrieve, refine through multiple retrievals, choose relevant knowledge bases (semantic routing), and compose a grounded answer with citations.
- The solution deploys as four native AWS CloudFormation stacks, each wiring its outputs into the next:
  - `01-knowledge-bases`: Creates an Amazon S3 bucket, two Managed Knowledge Bases (financial and weather corpora), their data sources, IAM, and an ingestion custom resource.
  - `02-agentic-gateway`: Stands up an Amazon Bedrock AgentCore Gateway with AWS_IAM auth and MCP.
- The solution includes two CloudWatch dashboards spanning seven layers of telemetry, plus on-demand and continuous evaluation, all provisioned by the same templates.
- Direct ingestion via a custom connector allows documents to become retrievable within seconds.
- The `AgenticRetrieveStream` API runs an agentic workflow that decides how to respond to a question, performing single or multi-hop retrievals as needed.

## 🚀 Availability
- The service manages ingestion, storage, embedding, and ranking, with no infrastructure to provision or capacity to monitor.
- Built-in agentic retrieval uses iterative planning and multi-hop retrievals to answer complex questions while honoring access permissions on every hop.

## 💡 Why it matters
- Agentic retrieval introduces reasoning agents that refine retrievals, route across knowledge bases, and produce grounded, cited answers.
- Observability and evaluation are built in from the start, with telemetry and metrics integrated into AWS CloudWatch and AWS X-Ray.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/architecture_v2-Page-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/27/ML-21427-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/27/ML-21427-3.png)

#AmazonBedrock #AgenticRetrieval #KnowledgeBases #AWS #RAG #AI

---

*Source: [Build observable enterprise agentic retrieval using Managed Amazon Bedrock Knowledge Base with AWS CloudFormation | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-observable-enterprise-agentic-retrieval-using-managed-amazon-bedrock-knowledge-base-with-aws-cloudformation/)*
*Source: [Build multi-tenant agentic chat applications on enterprise data with Amazon Bedrock Managed Knowledge Base | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-multi-tenant-agentic-chat-applications-on-enterprise-data-with-amazon-bedrock-managed-knowledge-base/)*
