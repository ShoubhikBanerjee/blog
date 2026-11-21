---
title: "MiniRAG v2 Alpha Brings Local-First Hybrid Search to MCP Clients"
slug: "minirag-v2-alpha-brings-local-first-hybrid-search-to-mcp-clients"
description: "MiniRAG v2 is now available as a test pre-release (2.0.0aN), offering a local-first Retrieval-Augmented Generation (RAG) Model Context Protocol (MCP) server written in Python. The update introduces..."
date: 2026-11-21T22:09:40+05:30
tags: [MiniRAG, LocalRAG, MCP, HybridSearch, PrivacyFirst]
categories: ["AI", "AI Agents", "RAG Systems", "Local Computing"]
image: "https://avatars.githubusercontent.com/u/12236835?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# MiniRAG v2 Alpha Brings Local-First Hybrid Search to MCP Clients

MiniRAG v2 is now available as a test pre-release (2.0.0aN), offering a local-first Retrieval-Augmented Generation (RAG) Model Context Protocol (MCP) server written in Python. The update introduces hybrid search capabilities over local documents, allowing MCP clients to access semantic and keyword-based retrieval without external network dependencies for indexing or querying.

## 🧩 How it works
The system uses a Python, MCP-native approach built on fastmcp, fastembed, and LanceDB. It performs hybrid search by fusing vector similarity with keyword ranking via weighted Reciprocal Rank Fusion, ensuring exact identifiers and error codes surface alongside semantically similar passages. An optional cross-encoder can rerank the best results. The server ships a routing policy that directs questions answerable by documents to the index rather than relying on the model's memory.

- **Ingestion:** 12 file formats are ingested via `markitdown`, including PDF, DOCX, PPTX, XLSX, HTML, CSV, EPUB, Jupyter notebooks, Markdown, and plain text. Standalone images and image-only PDFs are processed locally using Tesseract and Apple Vision on macOS.
- **Search Scope:** Keyword search covers both document titles and body text. An informative filename serves as the title if the document's own heading is boilerplate. Struck-through text remains searchable but is marked to prevent citation as current.
- **Privacy:** Nothing leaves the machine during local file ingestion, indexing, or querying. Only one-time model downloads and explicit `ingest_url` calls for web pages touch the network. The embedding, reranker, and labelling models can optionally run in a separate llama.cpp server.

## ⚙️ Key details
The release includes 11 MCP tools and a CLI for managing indexes without an MCP client. The server can host multiple indexes defined in `indexes.toml` over local HTTP, secured by a token. The default embedding model, `intfloat/multilingual-e5-large`, supports approximately 100 languages. Results are returned in small units (transcript windows, headings, slides, or tables) that fit the model's 250-token window, reducing cost. The tool also identifies documents that share significant text with query results, indicating potential versions or template siblings.

## 🚀 Availability
The `minirag-mcp` package version 2.0.0aN is a test pre-release. Installation commands like `pip install minirag-mcp` currently install version 1.1.1, which is documented in its specific README.

#MiniRAG #LocalRAG #MCP #HybridSearch #PrivacyFirst

---

*Source: [sfrangulov/minirag-mcp](https://github.com/sfrangulov/minirag-mcp)*
