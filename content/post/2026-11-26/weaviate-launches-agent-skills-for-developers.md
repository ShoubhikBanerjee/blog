---
title: "Weaviate Launches Agent Skills for Developers"
slug: "weaviate-launches-agent-skills-for-developers"
description: "Weaviate introduces Agent Skills to empower developers building AI applications."
date: 2026-11-26T18:08:23+05:30
tags: [Weaviate, AIagents, DeveloperTools, RAG, AgentSkills]
categories: ["AI", "Machine Learning", "AI Agents", "Developer Tools", "Cloud Services"]
image: "https://avatars.githubusercontent.com/u/37794290?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Weaviate Launches Agent Skills for Developers

Weaviate introduces Agent Skills to empower developers building AI applications.

## 🔍 Overview
- Agent Skills to empower developers building AI applications with Weaviate.
- Agent Skills to help developers build and use AI agents with Weaviate more effectively.
- Each skill is a folder containing instructions, scripts, and resources that agents like Claude Code, Cursor, GitHub Copilot, and others can discover to work more accurately and efficiently.
- The skill is automatically discovered by compatible agents.

## 🧩 How it works
- Works with any agent that supports the [Agent Skills](https://agentskills.io/home#adoption) format.
- Utility functions for the agent to directly interact with a Weaviate database.
- Blueprints for complete end-to-end AI applications with state-of-the art guidelines for agentic infrastructure.
- Use [weaviate-best-practices](skills/weaviate-best-practices/SKILL.md) to write or review Weaviate application code, with guidance on schema design, batch imports, and search.

## ⚙️ Key details
- Each skill is a folder containing instructions, scripts, and resources.
- The scripts and cookbooks rely on widely adopted third-party packages.
- Not responsible for security of third-party components; new vulnerabilities may arise.
- Users should run own security scans before executing any code and review packages flagged for known issues.
- It is recommended to create a free cluster in the [weaviate console](https://console.weaviate.cloud/signin?utm_source=github&utm_campaign=agent_skills).

## 🚀 Availability
- Python 3.11+ required.
- A Weaviate Cloud instance is needed.

## 🛠️ Capabilities
- Create Collections
- Explore Collections (Aggregation, Metadata, Schema)
- Query Collections (Keyword-, Vector-, Hybrid Search) (Support filters)
- Import Data (supports multi-vector and PDF ingestion)
- Multimodal PDF Ingestion
- Data Explorer
- Retrieval Augmented Generation (Basic, Advanced, Agentic)
- Query Agent
- Query Agent Chatbot
- Build a chatbot using the Query Agent
- Build a multimodal RAG app for my PDF documents
- Build an agentic RAG app
- Search my Weaviate documentation for information about HNSW indexing
- List all my Weaviate collections
- Find products similar to 'wireless headphones' in the Products collection

## 📚 Examples
- Search my Weaviate documentation for information about HNSW indexing.
- List all my Weaviate collections.
- Find products similar to 'wireless headphones' in the Products collection.
- Build a chatbot using the Query Agent.

#Weaviate #AIagents #DeveloperTools #RAG #AgentSkills

---

*Source: [weaviate/agent-skills](https://github.com/weaviate/agent-skills)*
