---
title: "Flexible GraphRAG v0.11.0 Release Introduces New Desktop App and State Options"
slug: "flexible-graphrag-v0-11-0-release-introduces-new-desktop-app-and-state-options"
description: "The v0.11.0 release introduces an early version of a Desktop App built with Tauri and Rust alongside various backend and architectural updates."
date: 2026-11-21T22:09:40+05:30
tags: [GraphRAG, Python, Tauri, LlamaIndex, FastAPI]
categories: ["AI", "Artificial Intelligence", "Software Development", "Database Systems"]
image: "https://avatars.githubusercontent.com/u/921792?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Flexible GraphRAG v0.11.0 Release Introduces New Desktop App and State Options

The v0.11.0 release introduces an early version of a Desktop App built with Tauri and Rust alongside various backend and architectural updates.

## 🚀 Availability

- New v0.11.0 release on 11/16/26.
- Includes an early version of a Desktop App (Tauri/Rust) around the React, Vue, or Angular UI with 5 Flexible GraphRAG tabs.
- Adds browsing, ingesting, searching, and graph viewing (5th tab) of local files and folders with auto-sync support.

## ⚙️ Key details

- The backend is written in Python, utilizing LlamaIndex and LangChain as peer frameworks.
- LlamaIndex serves as the default for each pipeline stage, while LangChain can be selected per stage via environment configuration.
- The API is built as a REST FastAPI service.
- Frontend options include Angular, React, and Vue TypeScript frontends, alongside an included MCP server.
- An optional lighter Docker-free configuration uses SQLite as the auto-sync incremental update state store (`INCREMENTAL_STATE_STORE=sqlite`) along with embedded stores such as LanceDB, BM25, and LadybugDB.
- Databases and dashboards can be enabled using the provided Docker Compose layout.

## 🧩 Capabilities and Integrations

- Supports 14 data sources (10 with incremental auto-sync).
- Supports 15 property graph databases, 4 RDF triple stores, 10 vector databases, OpenSearch, Elasticsearch, BM25 search, Alfresco, and Nuxeo.
- File and folder browser available via **Browse...** in the Alfresco, Nuxeo, CMIS, SharePoint, OneDrive, Box, S3, Azure Blob, GCS, and Google Drive data source forms for both desktop and web UIs.
- Optional ingest pipeline, hybrid search, and AI query can run through customizable Langflow visual flows utilizing 12 custom Langflow components.
- Optional ingest can run on a CocoIndex (Rust engine) pipeline reusing the same sources, targets, parsers, and KG extractors, adding step-level memoization and automatic delete reconciliation.
- Optional integration with Hyland OpenArch as a search and vector store, as well as a store for data sources and document state.

#GraphRAG #Python #Tauri #LlamaIndex #FastAPI

---

*Source: [stevereiner/flexible-graphrag](https://github.com/stevereiner/flexible-graphrag)*
