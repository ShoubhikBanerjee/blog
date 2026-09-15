---
title: "Unified Knowledge Graph RAG Stack Brings GraphRAG and LightRAG to AWS"
slug: "unified-knowledge-graph-rag-stack-brings-graphrag-and-lightrag-to-aws"
description: "A new open-source project named `unified-kg-rag-on-aws` (licensed under Apache-2.0) integrates two distinct knowledge-graph Retrieval-Augmented Generation (RAG) methodologies—Microsoft's GraphRAG and..."
date: 2026-09-15T12:03:19+05:30
tags: [RAG, AWS, KnowledgeGraph, GraphRAG, LightRAG]
categories: ["AI", "Machine Learning", "Cloud Computing", "Artificial Intelligence"]
image: "https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/08/Screenshot-2026-09-08-at-2.36.24 PM-1139x630.png"
author: "Shoubhik Banerjee"
draft: false
---

# Unified Knowledge Graph RAG Stack Brings GraphRAG and LightRAG to AWS

A new open-source project named `unified-kg-rag-on-aws` (licensed under Apache-2.0) integrates two distinct knowledge-graph Retrieval-Augmented Generation (RAG) methodologies—Microsoft's GraphRAG and HKUDS's LightRAG—onto a single shared stack. Built on Amazon Bedrock, Amazon Neptune, and Amazon OpenSearch Service, this implementation allows users to choose their retrieval methodology per query while sharing the underlying ingestion, indexing, caching, and multilingual handling layers.

## 🔍 Overview

Knowledge-graph RAG is built to reason over the structured connections within a document corpus. It first turns a corpus into a graph of entities and relationships, then reasons over that structure. 

In contrast, standard vector-only RAG retrieves chunks by embedding similarity, meaning it judges each chunk in isolation. While vector-only RAG shines when an answer sits in a single passage that can be found by similarity, its top-k nearest-neighbor retrieval returns locally similar text rather than the connective structures required to answer broader questions. 

This project features clean-room re-implementations of both methodologies directly from their respective papers. No upstream code was copied, and all attribution is documented in the project's `THIRD_PARTY_LICENSES`.

## 🧩 How it works

| Methodology | Core Bet | Indexing Process | Retrieval Process |
| :--- | :--- | :--- | :--- |
| **Microsoft GraphRAG** (arXiv:2404.16130) | Spend expensive reasoning once at indexing time to keep queries cheap. | An LLM extracts an entity-and-relationship graph from the corpus. Leiden community detection then identifies "communities" (clumps of entities referencing each other far more than anything else). An LLM writes summaries of each community and parent clusters, producing a tree of thematic summaries. | **Global questions** fan out across community summaries, gather answers, and map-reduce them into one response (never touching raw documents). **Local questions** start from named entities and walk outward along their relationships to collect neighbors and text. |
| **HKUDS LightRAG** (arXiv:2410.05779) | Keep indexing cheap and do the thinking when the question arrives. | Extracts an entity-and-relationship graph but stops there, performing no community detection or community summarization. | Extracts two kinds of keywords from the query. Low-level keywords (concrete things) are matched against entity descriptions ("what things are" layer). High-level keywords (abstract concepts) are matched against relationship descriptions ("how things connect" layer). |

## ⚙️ Key Details

This project exposes GraphRAG through multiple query execution strategies:

*   **Simple**: One of the core exposed retrieval strategies.
*   **Local**: Starts from the entities named in the question and walks outward along their relationships to collect neighboring nodes and text.
*   **Global**: Fans out across community summaries to perform map-reduce over topics.
*   **Drift**: One of the core exposed retrieval strategies.
*   **Auto**: Employs an LLM router to dynamically select the optimal strategy per query.

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/08/01-hexagonal-architecture.png)

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/08/02-ingestion-pipeline.png)

![figure](https://d2908q01vomqb2.cloudfront.net/ca3512f4dfa95a03169c5a670a4c91a19b3077b4/2026/09/08/04-retrieval-pipeline.png)

#RAG #AWS #KnowledgeGraph #GraphRAG #LightRAG

---

*Source: [Unified Knowledge Graph RAG on AWS: GraphRAG and LightRAG on one stack | Amazon Web Services](https://aws.amazon.com/blogs/opensource/unified-knowledge-graph-rag-on-aws-graphrag-and-lightrag-on-one-stack/)*
