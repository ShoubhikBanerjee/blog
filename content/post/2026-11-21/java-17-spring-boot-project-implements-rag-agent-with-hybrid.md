---
title: "Java 17 Spring Boot project implements RAG agent with hybrid search and observability"
slug: "java-17-spring-boot-project-implements-rag-agent-with-hybrid-search-and-observability"
description: "This update describes a Java 17 AI agent service built on Spring Boot 3.5 and LangChain4j 0.34. Designed for enterprise knowledge Q&A and intelligent customer service, the project implements a..."
date: 2026-11-21T18:08:57+05:30
tags: [Java, SpringBoot, RAG, AIAgents, LangChain4j]
categories: ["AI", "AI Agents", "Search and Retrieval", "Machine Learning", "Software Development"]
image: "https://avatars.githubusercontent.com/u/275442820?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Java 17 Spring Boot project implements RAG agent with hybrid search and observability

This update describes a Java 17 AI agent service built on Spring Boot 3.5 and LangChain4j 0.34. Designed for enterprise knowledge Q&A and intelligent customer service, the project implements a complete engineering pipeline that covers document ingestion, hybrid retrieval, and offline evaluation.

## 🔍 Overview

The system focuses on production-grade reliability, addressing common challenges like imprecise recall, uncontrolled costs, and lack of observability. It is not just a prompt demo; it features a full stack including semantic caching, multi-model routing, and end-to-end monitoring.

## 🧩 How it works

The request flow handles multiple scenarios to balance accuracy and cost:

- **Caching**: A request first checks the semantic cache; if a match is found, it returns immediately to reduce API costs.
- **Processing**: Unmatched queries trigger a ReAct loop or Adaptive RAG (query routing, rewriting, multi-turn retrieval) combined with tool calling.
- **Long Context**: A LongContextManager handles extended sessions via sliding windows and summary compression.
- **Delivery**: Results are written back to the cache and delivered using Server-Sent Events (SSE).

## ⚙️ Key details

- **Hybrid Search**: Combines Milvus vector search and BM25 keyword search, fused using Reciprocal Rank Fusion (RRF) with a k=60 constant.
- **Semantic Cache**: Uses embedding cosine similarity with a 0.92 threshold and a 24-hour time-to-live (TTL).
- **Evidence Gating**: Validates evidence levels before answering; if evidence is insufficient, the system routes the query to a human operator.
- **Multi-model Routing**: Routes requests across various providers including DeepSeek, Qwen, Doubao, Qwen3-Flash, and local Ollama instances.
- **Safety Measures**: The ReAct loop includes safeguards against infinite loops, timeouts, and step count limits.
- **Observability**: Integrates Micrometer, Prometheus, and Grafana to track latency across chat, retrieval, and ingestion stages.

### Performance and Testing

| Metric | Value | Context |
|---|---|---|
| FAQ Retrieval (R@1) | 98.3% | Multi-gold evaluation across 120 cases and 6 categories |
| Single Gold Baseline | R@1 47.5% / R@5 62.5% | Used for regression comparison between versions |
| FAQ Latency (P95) | 181ms | Multi-gold evaluation |
| Code Coverage | 64% | JaCoCo line coverage (exceeds the 45% gate) |
| Test Suite | 372 | Unit and integration tests |


#Java #SpringBoot #RAG #AIAgents #LangChain4j

---

*Source: [888newstep/ai-agent-platform](https://github.com/888newstep/ai-agent-platform)*
