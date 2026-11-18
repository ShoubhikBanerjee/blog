---
title: "Convex Integrates Mastra for AI Workflow Development"
slug: "convex-integrates-mastra-for-ai-workflow-development"
description: "Convex has introduced a new integration with Mastra, enabling developers to build and run AI workflows directly on its hosted backend platform. This integration allows users to create agents, define..."
date: 2026-11-18T22:09:17+05:30
tags: [Convex, Mastra, AIWorkflows, Serverless, Agents]
categories: ["AI", "AI Development", "Backend Platforms", "Serverless Computing", "AI Agents"]
image: "https://avatars.githubusercontent.com/u/81530787?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Convex Integrates Mastra for AI Workflow Development

Convex has introduced a new integration with Mastra, enabling developers to build and run AI workflows directly on its hosted backend platform. This integration allows users to create agents, define workflows, and execute them asynchronously using Convex serverless functions, while leveraging Convex's reactivity, storage, and vector capabilities.

## 🧩 How it Works

The Mastra component for Convex provides full support for durable workflows, including:

- Asynchronous execution from serverless functions (mutations or actions)
- Tracking workflow status via reactive queries
- Resuming workflows after suspension for user input
- Step forking, joining, and triggering
- Storage and vector integrations for agent memory and RAG

To use the component, developers must:

- Have an existing Convex project
- Install the `@convex-dev/mastra` package
- Manually install and export `@libsql/client` due to bundling issues
- Call `storage.setCtx(ctx)` and `vector.setCtx(ctx)` before using storage or vector features in actions

## ⚙️ Key Details

The integration enables:

- Running workflows from both `mastra dev` and `convex dev` for rapid iteration
- Using Convex for agent memory with storage and vector features
- Supporting agentic workflows involving user input, multiple LLM calls, and third-party integrations
- Custom mutation steps for transactional operations with guaranteed completion
- Helper functions to securely export actions for browser usage

#Convex #Mastra #AIWorkflows #Serverless #Agents

---

*Source: [convex/mastra](https://github.com/convex/mastra)*
