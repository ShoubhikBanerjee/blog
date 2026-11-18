---
title: "Parseltongue v1.7.2 Adds TreeSitter Code Analysis API and Rust Graph Algorithms"
slug: "parseltongue-v1-7-2-adds-treesitter-code-analysis-api-and-rust-graph-algorithms"
description: "Parseltongue released v1.7.2 on 2026-02-12, a stable version designed to parse codebases using TreeSitter for 12 languages and expose dependency analysis via an HTTP API. The tool builds dependency..."
date: 2026-11-18T12:19:35+05:30
tags: [Parseltongue, CodeAnalysis, DependencyGraph, TreeSitter, HTTPAPI]
categories: ["AI", "Static Analysis", "Developer Tools", "Graph Computing"]
image: "https://avatars.githubusercontent.com/u/183183660?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Parseltongue v1.7.2 Adds TreeSitter Code Analysis API and Rust Graph Algorithms

Parseltongue released v1.7.2 on 2026-02-12, a stable version designed to parse codebases using TreeSitter for 12 languages and expose dependency analysis via an HTTP API. The tool builds dependency graphs in CozoDB and executes graph algorithms in Rust, providing endpoints for impact analysis, complexity scoring, and community detection.

## 🔍 Overview
The release supports incremental reindexing through a file watcher and provides a query interface consisting of 26 HTTP endpoints. The system parses codebases using TreeSitter for 12 languages and stores the resulting dependency graph in CozoDB.

## 🧩 How it works
Users index a codebase using the `parseltongue pt01-folder-to-cozodb-streamer` command and start the HTTP server with `parseltongue pt08-http-code-query-server` on default port 7777. The architecture includes several specific implementation details:
*   Graph algorithms run in Rust rather than in CozoDB natively.
*   Search operates as an O(n) full-scan without secondary indices for reverse lookups.
*   Unresolved import references are mixed with production code.
*   The schema includes temporal fields that are currently underutilized.

## ⚙️ Key details
The HTTP API returns responses in the format `{"success": bool, "endpoint": str, "data": {…}, "tokens": int}`. Entity keys follow the pattern `language:type:name:file_path:line_range` (e.g., `rust:fn:main:src_main_rs:1-50`). All query endpoints accept an optional `?scope=L1||L2` parameter to filter by folder.

Key available endpoints include:

| Endpoint | Description |
| :--- | :--- |
| `/codebase-statistics-overview-summary` | Entity count, edge count, languages |
| `/code-entities-list-all` | Lists all entities with total count and data array |
| `/blast-radius-impact-analysis` | Transitive impact analysis (default 2 hops) |
| `/circular-dependency-detection-scan` | Identifies circular dependency cycles |
| `/complexity-hotspots-ranking-view` | Ranks most coupled entities (default top 10) |
| `/strongly-connected-components-analysis` | Tarjan SCC cycle detection |
| `/technical-debt-sqale-scoring` | ISO 25010 SQALE debt scores |
| `/centrality-measures-entity-ranking` | Entity importance via pagerank or betweenness |
| `/leiden-community-detection-clusters` | Leiden community detection |
| `/smart-context-token-budget` | Optimal code context within a token budget |
| `/incremental-reindex-file-update` | Reindex a single file (POST) |

## 🚀 Availability
The latest stable binary v1.7.2 is available for download. V2.0 development is scheduled to begin in May 2026. Users can copy a system prompt block into their LLM agent that contains every endpoint with exact parameter names.

#Parseltongue #CodeAnalysis #DependencyGraph #TreeSitter #HTTPAPI

---

*Source: [that-in-rust/parseltongue-rust-LLM-companion](https://github.com/that-in-rust/parseltongue-rust-LLM-companion)*
