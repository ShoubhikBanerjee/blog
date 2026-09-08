---
title: "New Repository Offers AutoGen Tutorials and Diverse AI Agent Examples"
slug: "new-repository-offers-autogen-tutorials-and-diverse-ai-agent-examples"
description: "A new GitHub repository has been released that bundles a variety of AutoGen projects, tutorials, and example agents for SaaS products, along with related resources for other agent frameworks."
date: 2026-09-09T00:51:34+05:30
tags: [AutoGen, AIagents, OpenSource]
categories: ["Artificial Intelligence", "AI Agents", "Open Source Software", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/71527334?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Repository Offers AutoGen Tutorials and Diverse AI Agent Examples

A new GitHub repository has been released that bundles a variety of AutoGen projects, tutorials, and example agents for SaaS products, along with related resources for other agent frameworks.

## 🔍 Overview
- The repo contains multiple projects that demonstrate how AutoGen works, provide prompts and agents for SaaS products, and explore its functionality.
- It also includes examples from other ecosystems such as CrewAI, Claude Code, and local‑agent setups.

## 📂 Content
**AutoGen‑focused items**
- Different projects using AutoGen and tutorials
- Examples including prompts and agents for SaaS products

**Additional agent examples**
- `crewai_flow_workout`
- `crewai_flow_single_llm`
- `crewai_infographic_creation`
- `crewai_docker_example`
- `crewai_flow_recipes`
- `google agent sdk`
- `mem0 with crewai`
- Full local agent setup (ollama, crewai, qdrant docker, crawl4ai, postgres docker)
- `claude_skill_social_me` – a Claude Code skill that researches a topic across YouTube, Instagram, TikTok and X through the Apify MCP server and writes a brief on what to make next (includes the five‑line prompt that builds it)
- `5 AI Agent Projects`
- `agentstack`
- `Lovable 2.0`
- `bolt.new + supabase`
- `replit 2.0`
- `ag2`
- `letta.ai course`
- `.af files`

## ⚙️ Requirements
- **MemGPT**: after the recent update, the OpenAI API key must be set with `memgpt configure`; otherwise MemGPT will not work.
- **FFMPEG**: required to use Whisper AI.
  - macOS installation guide: https://superuser.com/questions/624561/install-ffmpeg-on-os-x
  - Windows installation guide: https://phoenixnap.com/kb/ffmpeg-windows

## 🐞 Known Issues
- Function calling works with the OpenAI API, but when the configuration is switched to a local LM Studio instance, calls are ignored.
- When using LM Studio, the UserAgent must be set to include a default auto‑reply (e.g., "…") to avoid interaction errors.
- An issue about this behavior has been opened: https://github.com/tylerprogramming/ai/issues/1 and https://github.com/cpacker/MemGPT/issues/568

## 🚀 Getting Started
1. Clone the repository.
2. Follow the tutorial folders to see AutoGen prompts and agent definitions.
3. If you plan to use MemGPT, run `memgpt configure` and provide your OpenAI key.
4. Install FFMPEG if you intend to run Whisper‑based components.
5. For LM Studio users, adjust the UserAgent as noted in the issue discussion.

## 📚 References
- Repository description (quoted above) outlines the purpose and included examples.
- Installation links for required dependencies (FFMPEG) are provided.
- Issue threads document the LM Studio function‑calling problem.

#AutoGen #AIagents #OpenSource

---

*Source: [tylerprogramming/ai](https://github.com/tylerprogramming/ai)*
