---
title: "LlamaIndex shifts focus to document parsing and agentic OCR platform"
slug: "llamaindex-shifts-focus-to-document-parsing-and-agentic-ocr-platform"
description: "LlamaIndex has shifted its primary focus toward building an AI-powered engine for document parsing and extraction, moving away from its original emphasis on a broad set of orchestration tools for RAG..."
date: 2026-11-20T12:08:10+05:30
tags: [LlamaIndex, DocumentParsing, AgenticOCR, RAG, AIAgents]
categories: ["AI", "AI Agents", "Natural Language Processing", "Open Source", "Enterprise Software"]
image: "https://avatars.githubusercontent.com/u/130722866?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# LlamaIndex shifts focus to document parsing and agentic OCR platform

LlamaIndex has shifted its primary focus toward building an AI-powered engine for document parsing and extraction, moving away from its original emphasis on a broad set of orchestration tools for RAG and agent applications. The company, which launched its open-source framework three years ago in 2023, is now prioritizing enterprise document processing capabilities alongside free, fast parsing tools and open benchmarking efforts.

## 🔍 Overview

The evolution of the LlamaIndex ecosystem reflects a strategic shift in how agents interact with unstructured data. The core belief driving this change is that agents are the new consumers of documents and need specialized tools to accurately and cheaply unlock context from complex files at scale. This shift impacts AI startups and enterprises looking to automate document workflows.

*   **LlamaParse**: An enterprise platform for agentic OCR, parsing, extraction, and indexing.
*   **LiteParse**: A free, fast, and cheap text parser designed to be the best in the market.
*   **ParseBench and ExtractBench**: Benchmarks representing a commitment to open benchmarking for parsing and extraction.

The original LlamaIndex framework remains available as an open toolkit for developers to build agentic applications, but it is no longer the primary focus of the company's development efforts.

## 🧩 How it works

LlamaParse operates as a standalone platform focused on document agents and agentic OCR, though it can also be integrated with the LlamaIndex framework. The platform includes several distinct modules for handling document data:

| Module | Functionality |
| :--- | :--- |
| Parse | Agentic OCR and document parsing supporting 130+ formats |
| LlamaAgents | Deployed document agents |
| Extract | Structured data extraction from documents |
| Index | Ingest, index, and RAG pipelines |
| Split | Split large documents into subcategories |
| Agents | Build end-to-end document agents with Workflows and Agent Builder |

## ⚙️ Key details

For developers using the LlamaIndex framework in Python, the library is namespaced to distinguish between core functionality and integrations. Import statements that include `core` imply the use of the core package, while statements without `core` imply the use of an integration package.

*   **Starter Package**: The `llama-index` package includes core LlamaIndex and a selection of integrations.
*   **Customized Setup**: The `llama-index-core` package allows users to install the core and add specific integration packages from the integrations page.
*   **Integrations**: There are over 300 LlamaIndex integration packages that work seamlessly with the core, enabling compatibility with preferred LLM, embedding, and vector store providers.

## 🚀 Availability

LlamaParse is available as an enterprise platform where users can sign up to create an account and obtain an API key. It can be used either with the LlamaIndex framework or standalone. The LlamaIndex framework itself remains open-source, serving as an open toolkit for building agentic applications.

#LlamaIndex #DocumentParsing #AgenticOCR #RAG #AIAgents

---

*Source: [run-llama/llama_index](https://github.com/run-llama/llama_index)*
