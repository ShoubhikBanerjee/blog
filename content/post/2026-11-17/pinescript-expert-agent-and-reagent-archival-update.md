---
title: "PineScript Expert Agent and ReAgent Archival Update"
slug: "pinescript-expert-agent-and-reagent-archival-update"
description: "Two recent developments in the AI and reinforcement learning space have been noted: the release of a RAG-based Pine Script expert agent built with Pydantic AI, and the official archival of the..."
date: 2026-11-17T22:09:21+05:30
tags: [PineScript, ReinforcementLearning, PydanticAI, TradingView, Meta, RL]
categories: ["AI", "AI Agents", "Reinforcement Learning", "Trading Technology", "Open Source"]
image: "https://avatars.githubusercontent.com/u/156416587?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# PineScript Expert Agent and ReAgent Archival Update

Two recent developments in the AI and reinforcement learning space have been noted: the release of a RAG-based Pine Script expert agent built with Pydantic AI, and the official archival of the ReAgent reinforcement learning platform in favor of Pearl.

## 📗 PineScript Expert Agent

PineScript Expert is a Retrieval-Augmented Generation (RAG) agent developed using Pydantic AI that serves as an expert on Pine Script v6, the programming language used for custom indicators and strategies on TradingView. The system leverages vector search technology and large language models to provide accurate, context-aware answers and generate working code examples.

### Key Features

*   **Comprehensive Knowledge**: Accesses the entire Pine Script v6 documentation through natural language queries using a custom crawler.
*   **Code Generation**: Creates custom indicators and strategies based on specific user requirements.
*   **Interfaces**: Offers a web-based UI built with Streamlit (with persistent chat history) and an interactive command-line interface.
*   **Multi-Provider Support**: Utilizes either OpenAI or OpenRouter models as the LLM backend.
*   **Vector Search**: Uses pgvector for efficient semantic retrieval of relevant documentation.

### Technical Requirements

*   Python 3.11+
*   PostgreSQL with pgvector extension (configured to run on port 54322)
*   OpenAI API key (required for embeddings and default LLM)
*   OpenRouter API key (optional, for alternative LLM providers)
*   Docker (optional, for running PostgreSQL with pgvector)

## 🛑 ReAgent Archival

ReAgent, an open-source end-to-end platform for applied reinforcement learning developed and used at Facebook, is officially archived and no longer maintained. For latest support on production-ready reinforcement learning, the developers direct users to Pearl, a production-ready RL AI Agent Library developed by the Applied Reinforcement Learning team at Meta.

### Platform Details

*   **Architecture**: Built in Python, using PyTorch for modeling/training and TorchScript for model serving.
*   **Use Case**: Designed for large-scale, distributed recommendation/optimization tasks where a simulator is not accessible, relying on offline training on batches of data.
*   **Methodology**: Utilizes off-policy algorithms because policies update slowly and in batches.
*   **Key Tools**: Includes counterfactual policy evaluation (CPE) to test new policies without deployment, a Domain Analysis Tool to assess suitability for batch RL, and Behavior Cloning to bootstrap learning safely.
*   **License**: Released under a BSD 3-Clause license.

#PineScript #ReinforcementLearning #PydanticAI #TradingView #Meta #RL

---

*Source: [FaustoS88/Pydantic-AI-Pinescript-Expert](https://github.com/FaustoS88/Pydantic-AI-Pinescript-Expert)*
*Source: [facebookresearch/ReAgent](https://github.com/facebookresearch/ReAgent)*
