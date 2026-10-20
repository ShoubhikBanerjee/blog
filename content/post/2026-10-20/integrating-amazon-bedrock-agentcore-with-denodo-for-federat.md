---
title: "Integrating Amazon Bedrock AgentCore with Denodo for Federated Data Access"
slug: "integrating-amazon-bedrock-agentcore-with-denodo-for-federated-data-access"
description: "Amazon Bedrock AgentCore and the Denodo Platform are being used to build and optimize AI agents capable of accessing distributed enterprise data through a semantic layer."
date: 2026-10-20T22:03:21+05:30
tags: [AmazonBedrock, Denodo, DataVirtualization, AIAgents, FederatedQuery]
categories: ["AI", "AI Agents", "Data Management", "Cloud Infrastructure"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21332-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Integrating Amazon Bedrock AgentCore with Denodo for Federated Data Access

Amazon Bedrock AgentCore and the Denodo Platform are being used to build and optimize AI agents capable of accessing distributed enterprise data through a semantic layer.

## 🧩 How it works

Amazon Bedrock AgentCore hosts the agent, manages inbound authentication, and handles the outbound credentials presented to Denodo. The system operates as follows:

* **Planning:** A foundation model on Amazon Bedrock plans and writes queries.
* **Communication:** The agent communicates with the semantic layer using VQL, which is Denodo's SQL dialect.
* **Exposure:** The Denodo MCP Server uses the Model Context Protocol (MCP) to expose governed views to the agent.
* **Reasoning:** Joins, metric definitions, and row and column filters are maintained within the semantic layer rather than the prompt.

## ⚙️ Key details

Denodo implements the semantic layer as a data virtualization platform. This allows the agent to access a source mix that includes both cloud and on-premises data, meaning federation is not bounded by an Amazon Virtual Private Cloud (Amazon VPC).

| Component | Function |
| :--- | :--- |
| Denodo Virtual DataPort (VDP) | The core query engine where semantic-layer objects live, VQL executes, and access policies evaluate. |
| Design Studio | The browser-based authoring surface for VDP. |

### Data Federation Example
In a scenario where data is distributed across different engines without foreign keys spanning them or ETL jobs to build them, Denodo plans the federated query at execution time to reconcile the shared identifier (`cid`):

* **Amazon Aurora (PostgreSQL-compatible):** Customer profile data.
* **Amazon Redshift:** Order history.
* **On-premises PostgreSQL:** Rewards program data (`rewards_account`).

Denodo decides what to push into Aurora and Amazon Redshift, what to fetch from the on-premises cluster, and how to combine results without moving data between sources.

## 🚀 Availability

Denodo on AWS offers two deployment options:
* Agora: A fully managed cloud service.
* Self-managed installation: Deployed on Amazon Elastic Compute Cloud (Amazon EC2) or Amazon Elastic Kubernetes Service (Amazon EKS).

#AmazonBedrock #Denodo #DataVirtualization #AIAgents #FederatedQuery

---

*Source: [Build a semantic layer for agentic AI on AWS with Denodo and Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-semantic-layer-for-agentic-ai-on-aws-with-denodo-and-amazon-bedrock-agentcore/)*
