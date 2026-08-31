---
title: "Quivr releases quivr-core for building opinionated RAG-based personal assistants"
description: "Quivr has introduced `quivr-core`, the foundational engine behind Quivr.com, designed to facilitate the creation of a personal assistant or 'second brain.' This opinionated RAG (Retrieval-Augmented..."
date: 2026-08-31T22:04:32+05:30
tags: [Quivr, RAG, GenerativeAI, Python, LLM]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/252322352?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Quivr releases quivr-core for building opinionated RAG-based personal assistants

Quivr has introduced `quivr-core`, the foundational engine behind Quivr.com, designed to facilitate the creation of a personal assistant or "second brain." This opinionated RAG (Retrieval-Augmented Generation) system is built to be fast and efficient, allowing developers to focus on product development while Quivr manages the RAG infrastructure.

## 🔍 Overview
Quivr utilizes Generative AI to function as a personal assistant. The release of `quivr-core` allows developers to integrate these capabilities into their own projects by installing the core library. It is designed to work with any LLM and various file types.

## 🧩 How it works
The system is designed for simplicity, allowing users to create a RAG with five lines of code. 

*   **Installation**: Requires Python 3.10 or newer. Users can install the package using `pip install quivr-core`.
*   **Brain Creation**: Developers can initialize a "Brain" from specific files using `Brain.from_files`. 
*   **File Ingestion**: Supports PDF, TXT, and Markdown files. It also integrates with Megaparse for file ingestion and allows for custom parsers.
*   **Interaction**: Once files are ingested, users can ask questions directly to the brain using the `brain.ask` method.

## ⚙️ Key details
Quivr is compatible with a wide range of models and provides several configuration options for fine-tuning retrieval strategies.

*   **Supported LLMs**: Works with APIs from OpenAI, Anthropic, and Mistral, as well as models like Gemma.
*   **Local Models**: Supports local model execution using Ollama.
*   **Extensions**: Users can customize the RAG by adding internet search and various tools.

| Feature or Setting | Specification |
| :--- | :--- |
| Reranker Supplier | Cohere |
| Reranker Model | rerank-multilingual-v3.0 |
| Top N | 5 |
| Temperature | 0.7 |
| Max Input Tokens | 4000 |
| Max History | 10 |

## 🚀 Availability
The `quivr-core` library is available for integration into Python projects. Developers can use it to launch a chat and test different retrieval strategies by changing the configuration file. Future updates will include RAG improvements and additional features.

#Quivr #RAG #GenerativeAI #Python #LLM

---

*Source: [The-Vibe-Company/Quivr](https://github.com/The-Vibe-Company/Quivr)*
