---
title: "PandaProbe Releases Open Source Agent Engineering Platform"
slug: "pandaprobe-releases-open-source-agent-engineering-platform"
description: "PandaProbe is an open source agent engineering platform designed to help teams collaboratively trace, evaluate, monitor, and debug AI agents."
date: 2026-09-23T12:05:26+05:30
tags: [PandaProbe, AIagents, OpenSource, AgentEngineering]
categories: ["AI", "AI Agents", "Developer Tools", "Open Source"]
image: "https://avatars.githubusercontent.com/u/211257412?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# PandaProbe Releases Open Source Agent Engineering Platform

PandaProbe is an open source agent engineering platform designed to help teams collaboratively trace, evaluate, monitor, and debug AI agents.

## 🔍 Overview

PandaProbe provides traces, evals, and metrics to debug and improve AI agents. It integrates with several tools, including:

* LangGraph
* CrewAI
* Claude Agent SDK

## 🧩 How it works

The platform utilizes the following technical workflows:

| Action | Process Flow |
| :--- | :--- |
| Authentication | Auth validates with provider; API interacts with Identity for users, organizations, and projects. |
| Tracing | Client sends X-API-Key and X-Project-Name; API posts to Trace; Redis enqueues job; Worker persists trace and spans to DB. |
| Retrieval | API requests GET /traces or /sessions; Trace queries DB with filters and returns a paginated response. |
| Evaluation | API posts to Eval; Redis enqueues eval job; Worker performs an LLM-as-a-judge call for verdict and score. |

## ⚙️ Key details

For those choosing to self-host, the following requirements and steps apply:

* **Prerequisites:** Docker must be installed and running.
* **Installation:**
  1. `git clone https://github.com/chirpz-ai/pandaprobe.git`
  2. `cd pandaprobe`
  3. `./start.sh`
* **Access:**
    * Dashboard: http://localhost:3000
    * API reference: http://localhost:8000/scalar

## 🚀 Availability

Users can access the service via two deployment options:

* **PandaProbe Cloud:** Managed deployment by the PandaProbe team featuring a generous free-tier with no credit card required.
* **Self-hosted:** Open source installation via GitHub.

Client library documentation is available for quickstarts and advanced integrations.

#PandaProbe #AIagents #OpenSource #AgentEngineering

---

*Source: [chirpz-ai/pandaprobe](https://github.com/chirpz-ai/pandaprobe)*
