---
title: "Amazon Quick adds unified conversational AI over structured and unstructured data"
slug: "amazon-quick-adds-unified-conversational-ai-over-structured-and-unstructured-data"
description: "Amazon Quick addresses this with a unified experience."
date: 2026-11-04T22:02:53+05:30
tags: [AmazonQuick, ConversationalAI, DataIntegration]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Data Management", "Enterprise Software"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/27/ML-22035-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Quick adds unified conversational AI over structured and unstructured data

Amazon Quick addresses this with a unified experience.

## 🔍 Overview
Amazon Quick lets you connect structured data through enriched datasets and unstructured data through S3‑backed knowledge bases, then query both through a single conversational AI agent.

## 🧩 How it works
- **Unstructured content** (documents, PDFs, reports) is stored in Amazon S3 and indexed through a knowledge base.
- **Structured data** (metrics, sales figures, operational KPIs) is loaded as enriched datasets with semantic descriptions that the agent uses to translate questions into SQL.
- A **Space** brings both data types together into a single workspace. The Space references your knowledge base for unstructured queries and your datasets for structured queries, and can also include dashboards, file uploads, and action connectors.
- A **custom chat agent** links to the Space, uses it as its knowledge source, determines whether to query the knowledge base, the dataset, or both, and returns a combined response with citations.
- **AI guardrails** such as content‑safety screening are applied to chat interactions.
- Adding a new data source to the Space makes it instantly usable by the linked agent, while responses respect the permissions of the requesting user.

## ⚙️ Key Details
- An Amazon Quick account with an **Enterprise subscription** is required to create datasets.
- In the admin console, an administrator chooses **Permissions → AWS resources → Amazon S3 → Select S3 buckets**; selected buckets have read‑only permissions by default.
- Permissions are needed to create integrations, knowledge bases, datasets, spaces, and chat agents.
- Setup steps:
  1. **Start by connecting Amazon Quick to your S3 bucket.**
  2. In the Amazon Quick console, select **Knowledge** in the left navigation panel.
  3. Choose the **Amazon S3** connector and click **Add**.
  4. Provide the **S3 bucket URL** (the bucket must be in the same Region as Amazon Quick).
  5. Decide whether to use ACLs before creating the knowledge base (cannot be changed later).
  6. A success banner confirms the integration and the knowledge base begins indexing in the background.
  7. Load a structured file (e.g., `Product_Sales.csv`) as a **dataset**.
  8. Enrich the dataset with semantic descriptions, custom instructions, and correct data types so the AI can translate natural‑language questions into SQL.
- The layer where data from different sources converges into a unified context is the **Space**.

## 🗂 Component Summary
| Component | Purpose |
|---|---|
| Knowledge Base | Indexes unstructured content stored in Amazon S3 for AI‑powered search |
| Enriched Dataset | Holds structured data with semantic descriptions; enables SQL translation |
| Space | Workspace that references both the knowledge base and datasets; may include dashboards, file uploads, action connectors |
| Custom Chat Agent | Links to a Space, decides which source(s) to query, returns combined response with citations |
| Permissions | Controls access to S3 buckets, datasets, and ensures responses respect user permissions |

## 🚀 Availability
- Requires an **Enterprise subscription** for dataset creation.
- The S3 bucket must reside in the same AWS Region as Amazon Quick.
- All components (knowledge bases, datasets, spaces, chat agents) are created through the Amazon Quick console.



#AmazonQuick #ConversationalAI #DataIntegration

---

*Source: [Bring structured and unstructured data together with Amazon Quick | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/bring-structured-and-unstructured-data-together-with-amazon-quick/)*
*Source: [How Gen Digital built Norton Revamp’s AI-curated News Engine with Amazon Bedrock AgentCore Web Search | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-gen-digital-built-norton-revamps-ai-curated-news-engine-with-amazon-bedrock-agentcore-web-search/)*
*Source: [Build a semantic layer for agentic AI with EDB Postgres AI and Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-semantic-layer-for-agentic-ai-with-edb-postgres-ai-and-amazon-bedrock-agentcore/)*
