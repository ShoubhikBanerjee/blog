---
title: "LightRAG Integrates RAG-Anything for Multimodal Data Handling"
slug: "lightrag-integrates-rag-anything-for-multimodal-data-handling"
description: "LightRAG has merged with RAG-Anything, an all-in-one multimodal RAG system, to enable seamless processing and RAG capabilities for text, images, tables, and equations."
date: 2026-09-17T00:50:10+05:30
tags: [LightRAG, RAG, MultimodalAI, OpenSearch, LLM]
categories: ["AI", "Machine Learning", "Information Retrieval", "Software Development"]
image: "https://avatars.githubusercontent.com/u/118165258?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LightRAG Integrates RAG-Anything for Multimodal Data Handling

LightRAG has merged with RAG-Anything, an all-in-one multimodal RAG system, to enable seamless processing and RAG capabilities for text, images, tables, and equations.

## ⚙️ Key details

**Data Processing and Extraction**
* Multimodal content parsing and extraction via MinerU / Docling services.
* Smart Heading recognition for word documents.
* Enhanced knowledge graph extraction accuracy for open-sourced LLMs, such as Qwen3-30B-A3B.
* Document Deletion with automatic KG regeneration.

**Configuration and Storage**
* Integrated OpenSearch as a unified storage backend for all four LightRAG storage.
* Support for local deployment of storage backends, embedding, and reranking via Docker.
* Introduction of a setup wizard.

**System Performance and Evaluation**
* Reranker support is now the default query mode, boosting performance for mixed queries.
* Integration of RAGAS for Evaluation and Langfuse for Tracing.
* API updates to return retrieved contexts with query results to support context precision metrics.
* Elimination of processing bottlenecks to support large-scale datasets efficiently.

## 🧩 How it works

**Text Chunking Strategies**

| Strategy | Description |
| :--- | :--- |
| Fix | Selectable text chunking strategy |
| Recursive | Selectable text chunking strategy |
| Vector | Selectable text chunking strategy |
| Paragraph | Selectable text chunking strategy |

**Role-Specific LLM Configurations**

| Role | Function |
| :--- | :--- |
| EXTRACT | Independent LLM settings |
| QUERY | Independent LLM settings |
| KEYWORDS | Independent LLM settings |
| VLM | Independent LLM settings |

#LightRAG #RAG #MultimodalAI #OpenSearch #LLM

---

*Source: [HKUDS/LightRAG](https://github.com/HKUDS/LightRAG)*
