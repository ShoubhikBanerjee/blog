---
title: "SME Memory Engine Adds Spatial Regions and Explainable Retrieval"
slug: "sme-memory-engine-adds-spatial-regions-and-explainable-retrieval"
description: "A new long-term memory engine for AI applications called SME has been released, featuring self-organizing spatial memory regions, Ebbinghaus-inspired memory dynamics, and an explainable eight-signal..."
date: 2026-11-20T22:08:48+05:30
tags: [AIMemory, RAG, LLM, Embeddings, OpenSource]
categories: ["AI", "Machine Learning", "AI Agents", "Natural Language Processing", "Software Engineering"]
image: "https://avatars.githubusercontent.com/u/200968408?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# SME Memory Engine Adds Spatial Regions and Explainable Retrieval

A new long-term memory engine for AI applications called SME has been released, featuring self-organizing spatial memory regions, Ebbinghaus-inspired memory dynamics, and an explainable eight-signal retrieval system. The system runs offline with zero configuration and works with any OpenAI-compatible LLM or embedding model, whether cloud or local.

## 🔍 Overview
SME organizes all memories into a continuous embedding space where writes automatically form density-driven Memory Regions that dynamically grow, split, and merge. Regions connect via graph links. Memories also maintain six semantic edge types forming a Memory Graph: reference, causal, dialogue, summary, parent-child, and neighbor. Memory dynamics layer Ebbinghaus reinforcement, time decay (without deletion), automatic merging, and long-term compression on top.

## 🧩 How It Works
**Two-stage hybrid retrieval** combines region-led recall with vector/BM25 (Chinese bigram)/metadata hybrid search, optional graph enhancement, and an eight-signal explainable ranking. The 1.3 retrieval update adds min-max hybrid fusion (measured at +2.5 to +4.2 percentage points accuracy across three seed A/B tests, with bias halved) and Personalized PageRank graph expansion following the HippoRAG 2 approach to surface bridging associations. Optional idle-time automatic reorganization (sleep-time compute) and ONNX int8 embeddings are available via the `[onnx]` extra.

**Memory lifecycle** includes configurable reinforcement, decay, merging, and compression. Memories are never deleted due to decay and can be restored from archive.

## ⚙️ Key Details
### Extension Modules (12 total, all disabled by default for base behavior)
| Module | Function |
|---|---|
| Fact extraction | Extracts structured facts from input |
| QA pair replay | Replays question-answer pairs |
| Temporal knowledge graph | Builds time-aware knowledge graphs |
| User profiling | Maintains user profiles |
| Fact version correction | Corrects fact versions over time |
| Noise suppression | Filters noisy inputs |
| WAL incremental persistence | Write-ahead log for durability |
| Storage backend | Pluggable storage |
| REST + SDK | API and Python SDK access |
| Observability | Metrics and monitoring |
| Hierarchical context | Multi-level context management |
| Multi-user isolation | Isolates memory per user |

### Presets (7 configurations)
- Chat assistant
- Knowledge base dynamic
- Knowledge base static
- Embodied robot
- All off
- Static retrieval · UNITED
- Real model · semantic priority

### Interfaces
- Python SDK
- REST API (FastAPI) with official client
- MCP (agent-native, one-line mount)
- Web configuration center (`python -m sme.api` then open browser)

### Chinese-Friendly Features
- Chinese 1-2 gram BM25 keyword channel enabled by default
- Document clause import for legal/medical knowledge base scenarios

### Explainable Retrieval
Every hit includes a `breakdown` of eight signals: semantic, importance, freshness, weight, decay, hit_count, recency, and region.

## 🚀 Availability
**Installation**: Zero-config offline operation. After installing core dependencies, a built-in hashing embedding runs the basic pipeline with no model downloads or API keys.

**Core dependencies**: `numpy`, `httpx`, `fastapi`, `uvicorn`, `networkx`, `python-multipart`, `hnswlib` (in `[ann]` extra). Install via `pip install -r requirements.txt` or `pip install -e .` (with `pip install -e ".[ann]"` for ANN acceleration; region scaling automatically enables ANN, falling back to exact scan otherwise).

**Requirements**: Python ≥ 3.10, Windows or Linux.

## 💡 Why It Matters
- Benchmarked head-to-head against Mem0 and bare RAG
- All 101 configuration items and 7 presets are fully toggleable
- Performance figures: WAL group commit 2,557 writes/sec (1.79×), ONNX int8 batch embedding 7.4×, memory graph hot path O(E)→O(deg) measured 127–159×, hashing retrieval p50 ~4 ms at 2k items
- Runs entirely offline with zero external dependencies for the base path

#AIMemory #RAG #LLM #Embeddings #OpenSource

---

*Source: [jack66g/spatial-memory-engine](https://github.com/jack66g/spatial-memory-engine)*
