---
title: "Langfuse Releases Agent Skills for AI Coding Assistants"
slug: "langfuse-releases-agent-skills-for-ai-coding-assistants"
description: "Agent Skills for Langfuse have been released as an open-source toolkit that teaches AI coding assistants like Claude Code and Cursor how to work with Langfuse, the open-source LLM engineering..."
date: 2026-11-26T22:08:01+05:30
tags: [Langfuse, AI, LLM, Observability, Evals, CodingAssistants]
categories: ["AI", "AI Development", "Machine Learning", "Software Engineering", "Cloud Computing"]
image: "https://avatars.githubusercontent.com/u/134601687?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Langfuse Releases Agent Skills for AI Coding Assistants

Agent Skills for Langfuse have been released as an open-source toolkit that teaches AI coding assistants like Claude Code and Cursor how to work with Langfuse, the open-source LLM engineering platform for tracing, prompt management, and evaluation.

## 🧩 What are Agent Skills?
- Skills are capabilities that enable AI coding assistants to interact with Langfuse
- They teach assistants to query and manage traces, prompts, datasets, and scores via the Langfuse API
- They help look up documentation and apply best practices

## 🔍 Main Skill
- The primary skill works with Langfuse to handle core operations through the API
- It supports looking up documentation and applying best practices in mind

## 🔄 Migration Support
- The skills include functionality to migrate from other LLM observability platforms (LangSmith, Arize, Braintrust, etc.) to Langfuse
- The migration process interviews users about scope
- It handles live tracing cutover and transfers historical traces, datasets, prompts, and evaluators

## ⚙️ Installation Options
- Install as a Cursor plugin: `/add-plugin langfuse`
- Install via the skills CLI: `npx skills add langfuse/skills --skill "langfuse"`
- Clone the repo and symlink: `git clone https://github.com/langfuse/skills.git /path/to/langfuse-skills` and `ln -s /path/to/langfuse-skills/skills/langfuse /path/to/skills-directory/langfuse`

## 🔑 Requirements
- A Langfuse account (cloud at cloud.langfuse.com, us.cloud.langfuse.com, or self-hosted)
- API keys: `LANGFUSE_PUBLIC_KEY`, `LANGFUSE_SECRET_KEY`, and `LANGFUSE_BASE_URL`
- API keys are found in Langfuse project under Settings > API Keys

## 🚀 Automatic Usage
- The agent automatically uses these skills when relevant, including:
  - Setting up Langfuse tracing in a project
  - Setting up CI/CD experiment gates with `langfuse/experiment-action`
  - Auditing existing instrumentation
  - Preparing an application and Langfuse project for the v4 platform migration
  - Migrating prompts to Langfuse prompt management
  - Querying traces, prompts, or datasets via the API
  - Looking up Langfuse docs, SDK usage, or integration guides

## 💡 Getting Involved
- Want to improve a skill or add a new one? See CONTRIBUTING.md
- For issues or new skill requests, start a discussion on GitHub

#Langfuse #AI #LLM #Observability #Evals #CodingAssistants

---

*Source: [langfuse/skills](https://github.com/langfuse/skills)*
