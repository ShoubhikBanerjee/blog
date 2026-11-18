---
title: "NornicDB combines graph and vector search with sub-millisecond latency"
slug: "nornicdb-combines-graph-and-vector-search-with-sub-millisecond-latency"
description: "NornicDB is a distributed, low-latency database that integrates Graph and Vector capabilities with Temporal MVCC. It is designed to provide sub-millisecond performance for HNSW search, graph..."
date: 2026-11-18T12:19:35+05:30
tags: [GraphDatabase, VectorSearch, Cypher, NornicDB, GoLang]
categories: ["AI", "Databases", "Data Infrastructure", "Search Technology", "Open Source"]
image: "https://avatars.githubusercontent.com/u/1736223?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# NornicDB combines graph and vector search with sub-millisecond latency

## 🔍 Overview

NornicDB is a distributed, low-latency database that integrates Graph and Vector capabilities with Temporal MVCC. It is designed to provide sub-millisecond performance for HNSW search, graph traversal, and writes.

## 🧩 How it works

The system allows users to query connected data using Cypher with compatible Bolt drivers. It supports combining graph traversal with vector and full-text retrieval. Historical state can be modeled using MVCC and retained history.

## ⚙️ Key details

- Interfaces: Supports Neo4j Bolt/Cypher and qdrant's gRPC, allowing switching without changes.
- Features: Includes schemas, managed embeddings, reranking, LLM integration, GPU acceleration, Auto-TLP, Policy-based Memory Decay, and an MCP server.
- Architecture: Multi-arch support includes CPU, CUDA, Metal, and Vulkan.
- Integration: Can be embedded in Go applications and supports HTTP interfaces.

## 🚀 Availability

NornicDB is available via Docker images and native installers.

| Platform | Instructions |
| :--- | :--- |
| NVIDIA CUDA | Use image `timothyswt/nornicdb-amd64-cuda-bge:latest` |
| Vulkan | Use image `timothyswt/nornicdb-amd64-vulkan-bge:latest` |
| macOS | Docker does not expose Metal acceleration; native install or local build required for GPU acceleration. Download `.pkg` installer (arm64 for Apple Silicon, amd64 for Intel) or use Homebrew. |
| Windows | Run `.\bin\nornicdb.exe serve` |

Users can access the admin UI at `http://localhost:7474`. Benchmark results depend on workload and hardware.

#GraphDatabase #VectorSearch #Cypher #NornicDB #GoLang

---

*Source: [orneryd/NornicDB](https://github.com/orneryd/NornicDB)*
