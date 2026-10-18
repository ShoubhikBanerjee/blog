---
title: "codebase-memory-mcp Adds 3D Architecture Mapping and Persistent Knowledge Graphs for AI Agents"
slug: "codebase-memory-mcp-adds-3d-architecture-mapping-and-persistent-knowledge-graphs-for-ai-agents"
description: "codebase-memory-mcp is a local Model Context Protocol (MCP) server that provides AI coding agents with a persistent code knowledge graph. It indexes functions, classes, imports, and relationships..."
date: 2026-10-18T22:01:16+05:30
tags: [MCP, CodeIntelligence, AItools, SoftwareArchitecture, KnowledgeGraph]
categories: ["AI", "Artificial Intelligence", "Software Development", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/81762164?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# codebase-memory-mcp Adds 3D Architecture Mapping and Persistent Knowledge Graphs for AI Agents

codebase-memory-mcp is a local Model Context Protocol (MCP) server that provides AI coding agents with a persistent code knowledge graph. It indexes functions, classes, imports, and relationships across 162 languages, allowing tools like Claude Code and Codex to explore software architecture without relying on hosted services or API keys.

## 🔍 Overview

The tool is a high-performance code intelligence server delivered as a single static binary with zero dependencies. It indexes codebases into a persistent knowledge graph, with average repositories being indexed in milliseconds. This system is designed to help developers understand unfamiliar code, perform rescue engineering on inherited projects, or manage large volumes of AI-generated code.

## 🧩 How it works

The native C backend exposes 17 MCP tools and supports 45 automatic or conditional client integrations. A Hybrid LSP provides semantic type resolution for a variety of popular programming languages.

| Feature | Supported Details |
| :--- | :--- |
| Semantic Resolution | Python, TypeScript, JavaScript, JSX/TSX, PHP, C#, Go, C, C++, Java, Kotlin, Rust, Perl |
| Language Support | 162 languages |
| Core Components | Native C backend, Hybrid LSP, CBM Lens Beta UI |
| Privacy | Local source analysis, local graph storage, on-device browser AI inference |

## ⚙️ Key details

Backend benchmarks indicate high-speed performance, reporting that the Linux kernel (28 million lines of code) can be indexed in approximately 3 minutes. Relationship queries on an Apple M3 Pro are reported to run in under 1 ms. 

Efficiency gains include:
*   Approximately 120× fewer tokens in a five-query comparison (~3,400 vs ~412,000 for file-by-file exploration).
*   A reported 10× lower token use and 2.1× fewer tool calls across a 31-repository agent comparison.
*   Answer-quality scores of 83% for CBM compared to 92% for file-by-file exploration in separate backend results.

## 🚀 Availability

CBM Lens Beta is a new addition to the project, introduced via PR #2068. It is not included in the current v0.11.0 release installer, which ships the previous graph UI. To access the new interface and 3D features now, the software must be built from source. The installer is capable of writing agent configurations for selected clients.

## 💡 Why it matters

The software introduces several visualization tools to maintain code quality and understand dependencies. The CBM Lens interface includes an IDE-style source reader, local code chat, and a 3D architecture map. 

Users can explore the code knowledge graph in 3D through the following visual cues:
*   **Galaxy graph:** A view showing how code fits together.
*   **Blocks:** Files and symbols are represented as selectable blocks.
*   **Height:** Indicates the source size of the file or symbol.
*   **Hotspot gravity:** Reflects static fan-in.
*   **Edge pulses:** Show relationship direction without representing live execution.
*   **Architecture decisions:** These are stored alongside the project's index to maintain context as the codebase grows.

#MCP #CodeIntelligence #AItools #SoftwareArchitecture #KnowledgeGraph

---

*Source: [DeusData/codebase-memory-mcp](https://github.com/DeusData/codebase-memory-mcp)*
