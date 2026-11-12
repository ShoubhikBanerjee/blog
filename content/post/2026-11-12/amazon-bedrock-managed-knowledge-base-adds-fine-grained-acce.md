---
title: "Amazon Bedrock Managed Knowledge Base adds fine-grained access control and migration tools"
slug: "amazon-bedrock-managed-knowledge-base-adds-fine-grained-access-control-and-migration-tools"
description: "Amazon Bedrock now provides a Managed Knowledge Base service that handles ingestion, storage, indexing, and retrieval. This service includes built-in features such as hybrid search, a managed..."
date: 2026-11-12T22:08:51+05:30
tags: [AmazonBedrock, GenerativeAI, CloudComputing, DataSecurity]
categories: ["AI", "Artificial Intelligence", "Cloud Services", "Data Management"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-22176-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Bedrock Managed Knowledge Base adds fine-grained access control and migration tools

Amazon Bedrock now provides a Managed Knowledge Base service that handles ingestion, storage, indexing, and retrieval. This service includes built-in features such as hybrid search, a managed reranker, and multimodal file parsing, with infrastructure that scales automatically based on content volume.

## 🧩 How it works

Managed Knowledge Base simplifies content management by handling technical infrastructure, while allowing teams to retain control over their content and applications. The service integrates with Amazon Bedrock AgentCore Gateway to expose knowledge bases as tools for agents.

| Feature | Function |
| :--- | :--- |
| ACL awareness | Filters retrieval results based on user permissions |
| Agentic retrieval | Handles multi-part questions and iterative searching |
| Deletion safeguard | Protects against accidental bulk removal of indexed content |
| Native connectors | Ingests from S3, SharePoint, and Confluence |

## ⚙️ Key details

*   **Migration Support:** A new migration guide in the Agent Toolkit for AWS helps teams migrate from customer-managed knowledge bases to the managed service. The process includes read-only discovery, planning, and the generation of infrastructure-as-code templates.
*   **Access Control:** The system supports Access Control List (ACL) awareness, which ingests document permissions alongside content. When integrated with AgentCore Gateway, the system can inject verified user attributes into tool calls to ensure users only access authorized documents.
*   **Security Layers:** Security is maintained through a combination of request interceptors that define user context, Cedar policies within AgentCore, and resource-based policies that restrict access to the gateway execution role.
*   **Pricing:** The service uses usage-based pricing, with costs metered directly based on stored and retrieved content.

## 🚀 Availability

*   Supports up to 200 data sources per knowledge base.
*   Supports up to 10,000 knowledge bases per account, per Region.
*   Integration with AgentCore Gateway and resource-based policies are exclusive to Managed Knowledge Base.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-22176-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-22176-2.png)

#AmazonBedrock #GenerativeAI #CloudComputing #DataSecurity

---

*Source: [Migrate to Amazon Bedrock Managed Knowledge Base with your coding agent | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/migrate-to-amazon-bedrock-managed-knowledge-base-with-your-coding-agent/)*
*Source: [Fine-grained access control for Amazon Bedrock Managed Knowledge Base tools | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/fine-grained-access-control-for-amazon-bedrock-managed-knowledge-base-tools/)*
