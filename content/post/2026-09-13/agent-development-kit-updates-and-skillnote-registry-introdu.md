---
title: "Agent Development Kit Updates and SkillNote Registry Introduction"
slug: "agent-development-kit-updates-and-skillnote-registry-introduction"
description: "The Agent Development Kit (ADK) has released version 2.0, introducing breaking changes to its agent API, event model, and session schema. Simultaneously, the new open-source SkillNote registry has..."
date: 2026-09-13T06:06:36+05:30
tags: [AI, Python, Agents, OpenSource, DeveloperTools]
categories: ["AI", "Artificial Intelligence", "Software Development", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/1342004?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Agent Development Kit Updates and SkillNote Registry Introduction

The Agent Development Kit (ADK) has released version 2.0, introducing breaking changes to its agent API, event model, and session schema. Simultaneously, the new open-source SkillNote registry has been introduced to manage skill libraries for AI coding agents.

## 🛠️ ADK 2.0 Updates
ADK is an open-source, code-first Python toolkit designed for building, evaluating, and deploying AI agents. Key updates and features include:

- Workflow Runtime: A graph-based engine supporting routing, loops, retry logic, state management, and human-in-the-loop workflows.
- Task API: Facilitates structured agent-to-agent delegation and multi-turn task modes.
- Compatibility: Sessions from ADK 2.0 are readable by version 1.28+, though incompatible with older 1.x versions.
- Deployment: Optimized for Gemini but model-agnostic, with options for Cloud Run or Vertex AI Agent Engine.
- Development: Allows code-first configuration using `Agent` and `Workflow` classes, alongside a no-code Agent Config feature.

## 📋 SkillNote Overview
SkillNote is an open-source, self-hosted registry for managing `SKILL.md` files used by AI coding agents like Claude Code, Cursor, and OpenHands. It addresses description character limits and provides centralized management.

| Feature | Function |
| :--- | :--- |
| Scope | Per-project collections of up to 15 skills |
| Sync | Live browser edits update connected agents within 60 seconds |
| Feedback | Agents rate skills 1-5 with comments |
| Hosting | Self-hosted via Docker and Node.js 20+ |

## 🚀 Deployment Details
SkillNote can be initialized using `npx skillnote start`, which deploys a web, API, and Postgres stack. The system supports:

- CLI commands: `start`, `stop`, `restart`, `status`, and `logs`.
- Infrastructure: Requires Docker and Node.js 20+; compatible with Podman 4+.
- Visibility: Web UI accessible at `http://localhost:3000` and API at `http://localhost:8082`.

#AI #Python #Agents #OpenSource #DeveloperTools

---

*Source: [google/adk-python](https://github.com/google/adk-python)*
*Source: [luna-prompts/skillnote](https://github.com/luna-prompts/skillnote)*
