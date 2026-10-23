---
title: "IskayPet Deploys Corporate Knowledge Assistant Using Amazon Bedrock Managed Knowledge Bases"
slug: "iskaypet-deploys-corporate-knowledge-assistant-using-amazon-bedrock-managed-knowledge-bases"
description: "IskayPet, a leading pet‑care company in Iberia, launched a corporate knowledge assistant that answers employee questions across retail, veterinary, procurement, and onboarding domains in four..."
date: 2026-10-23T12:04:45+05:30
tags: [AI, RAG, AmazonBedrock, EnterpriseAI]
categories: ["AI", "Machine Learning", "Enterprise Software", "Knowledge Management", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21903-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# IskayPet Deploys Corporate Knowledge Assistant Using Amazon Bedrock Managed Knowledge Bases

IskayPet, a leading pet‑care company in Iberia, launched a corporate knowledge assistant that answers employee questions across retail, veterinary, procurement, and onboarding domains in four languages, using Amazon Bedrock Managed Knowledge Bases and without building its own RAG infrastructure.

## 🔍 Overview
- Office teams faced a knowledge challenge: operational answers were hidden in hundreds of SharePoint documents in Spanish, Portuguese, French, and English.
- Searching large, multilingual document stores was time‑consuming and often returned outdated or incorrect information.
- Adding new stores, countries, or procedures continuously grew the problem.
- Retrieval‑Augmented Generation (RAG) is a common approach, but operating RAG in production normally requires managing vector databases, embedding pipelines, and ingestion jobs.
- IskayPet chose Amazon Bedrock Managed Knowledge Bases to provide a managed RAG solution that removes the need for custom infrastructure.

## 🏢 Company Background
- Operates more than 330 stores across Spain, Portugal, and France under the Kiwoko, Tiendanimal, Kivet, Clinicanimal, and Animalis brands.
- Employs over 4,500 staff and serves 7 million customers.
- Business areas include retail, veterinary clinics, animal‑care services, procurement, and people/onboarding, each with its own policies and procedures.

## 🛠️ Architecture & Implementation
- Front‑end: store‑facing interface built with Kiro using Claude Haiku 4.5.
- Backend: Amazon Bedrock Managed Knowledge Bases provides a fully managed RAG stack.
- Data ingestion: Native SharePoint connector pulls documents directly from existing SharePoint libraries, avoiding migration.
- Content processing: Advanced indexing parses text and images embedded in documents.
- Retrieval: Built‑in hybrid search combines semantic and keyword (BM25) search at no extra cost, ensuring exact term matches (e.g., product codes).
- Ranking: Managed reranking reorders retrieved passages by relevance without additional charge.
- Security: Document‑level access control enforces SharePoint permissions at query time, so users only see passages they are allowed to read.
- Flexibility: Model selection can start with a cost‑effective model and be changed later without rewriting infrastructure.
- Quality monitoring: Native RAG evaluation tools let the team measure answer quality at each step.

### Feature Summary
| Feature | Description |
|---|---|
| Managed RAG | Bedrock handles ingestion, multimodal parsing, vector storage, embedding generation, and retrieval. |
| Native SharePoint connector | Ingests documents directly from SharePoint, preserving existing permissions. |
| Advanced indexing | Processes content from embedded images as well as text. |
| Hybrid search (semantic + BM25) | Retrieves both conceptually relevant passages and exact keyword matches. |
| Managed reranking | Reorders results by relevance automatically. |
| Document‑level access control | Enforces source system permissions at retrieval time. |
| Model flexibility | Allows switching models without infrastructure changes. |
| Native RAG evaluation | Built‑in tools for quality measurement throughout the pipeline. |

## 📈 Production Results
- The assistant is accessed through employees’ existing channels.
- When a question is asked, the system retrieves the most relevant passages from the knowledge base, limited to documents the user is permitted to read.
- The solution operates across three countries and four languages, handling retail operations, veterinary care, people/onboarding, and procurement, with no RAG infrastructure to manage.
- The team measured quality at each step using Bedrock’s evaluation tools.



![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21903-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21903-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/16/ML-21903-3.jpg)

#AI #RAG #AmazonBedrock #EnterpriseAI

---

*Source: [How IskayPet unified corporate knowledge with Amazon Bedrock Managed Knowledge Bases | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/how-iskaypet-unified-corporate-knowledge-with-amazon-bedrock-managed-knowledge-bases/)*
