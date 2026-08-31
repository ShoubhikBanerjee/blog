---
title: "LightRAG: Simple and Fast Retrieval-Augmented Generation Now at v1.0+"
description: "LightRAG is an open-source Retrieval-Augmented Generation (RAG) system developed by the HKUDS research group. It is designed for simplicity and speed, and has recently hit a series of milestones..."
date: 2026-08-31T18:56:17+05:30
tags: [RAG, KnowledgeGraph, AI, OpenSource, Retrieval]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/118165258?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LightRAG: Simple and Fast Retrieval-Augmented Generation Now at v1.0+

LightRAG is an open-source Retrieval-Augmented Generation (RAG) system developed by the HKUDS research group. It is designed for simplicity and speed, and has recently hit a series of milestones marked as "NEW" features, indicating first-time enhancements to its core capabilities.

## 🧩 How it works

LightRAG operates on a graph-based approach to RAG, integrating with various storage backends and embedding services to retrieve and generate answers from a knowledge base.

## ⚙️ Key details

*   **Multimodal Support:** As of the June 2025 release, LightRAG integrates with [RAG-Anything](https://github.com/HKUDS/RAG-Anything) for an "All-in-One Multimodal RAG" system. This enables parsing and retrieval across diverse formats including PDFs, images, Office documents, tables, and formulas.
*   **Scalability:** A scalability enhancement in October 2025 eliminated processing bottlenecks to support large-scale datasets efficiently.
*   **Query Performance:** August 2025 updates introduced a default **Reranker** mode to boost performance for mixed queries and a **Document Deletion** feature with automatic knowledge graph regeneration.
*   **Open-Source LLM Focus:** In September 2025, enhancements were made to improve knowledge graph extraction accuracy for open-sourced LLMs like Qwen3-30B-A3B.
*   **Observability:** November 2025 integration added RAGAS for Evaluation and Langfuse for Tracing, updating the API to return retrieved contexts for context precision metrics.
*   **Storage & Setup:** March 2026 brought OpenSearch as a unified storage backend and a setup wizard supporting local Docker deployment for embedding, reranking, and storage services.

## 🚀 Availability

LightRAG is available as a Python package (`lightrag-hku`) on PyPI. The source code is hosted on GitHub, with community support via Discord and WeChat.

## 💡 Why it matters

Recent development activity shows a rapid cadence of new features focused on multimodal integration, scalability, and operational tooling, moving LightRAG from a simple framework to a more comprehensive platform for building RAG applications.

#RAG #KnowledgeGraph #AI #OpenSource #Retrieval

---

*Source: [HKUDS/LightRAG](https://github.com/HKUDS/LightRAG)*
