---
title: "New list catalogs tools for tracing and evaluating AI agents"
slug: "new-list-catalogs-tools-for-tracing-and-evaluating-ai-agents"
description: "A new curation of tools, standards, and benchmarks has been published for tracing and evaluating AI products. The list targets LLM apps, agents, coding-agent harnesses, Agent Skills, and MCP servers...."
date: 2026-11-16T22:14:27+05:30
tags: [AIAgents, LLMEvaluation, MCP, OpenTelemetry, AIEngineering]
categories: ["AI"]
image: "https://avatars.githubusercontent.com/u/107818450?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New list catalogs tools for tracing and evaluating AI agents

## 📝 Overview
A new curation of tools, standards, and benchmarks has been published for tracing and evaluating AI products. The list targets LLM apps, agents, coding-agent harnesses, Agent Skills, and MCP servers. Evaluations in this ecosystem are graded by LLM judges or deterministic checks.

## 🎯 Target Audience
The resource is designed for engineers who build or run AI agents and need to monitor:
* What a run did
* What it cost
* Whether it was correct

## 🧩 Scope and Coverage
The list covers several areas of AI infrastructure:
* OpenTelemetry conventions
* Tracing platforms
* Coding-agent telemetry
* Eval frameworks
* Agent and harness benchmarks
* Skill and MCP server testing
* Guardrails

## ⚙️ Curation and Verification Standards
Every entry in the list is held to specific requirements:
* Must be alive and maintained
* Must be at least 8 weeks old
* New entries are run hands-on before addition
* Entries describe what a project does rather than its marketing claims
* Licenses are noted if a project is not plainly open source

Projects that were dormant, end-of-life, out of scope, or too young to judge were excluded from the list.

## 🧪 Verification Methodology
The list's claims regarding execution are based on specific audits:
* **2026-10-04 Audit**: Most entries were installed or built and run against a mock backend. Some entries could not be run due to dependencies on Docker or hosted accounts (e.g., Kong, SigNoz). The list does not claim every entry was exercised.
* **2026-11-15 Expansion**: Entries added during the evals expansion and the follow-up that day were run on a Linux box with local models or mocks only. Commands and output are stored in `evidence/`.
* **Ongoing Monitoring**: A weekly job re-checks that each repository still exists, is not archived, and has a recent commit.
* **Recipes**: Short patterns using tools on the list were run on a Linux box with local models only, with commands and output in `evidence/recipes.md`.

## 💡 Technical Patterns
The evidence highlights specific implementation patterns for observation and testing:
* **Proxy Tracing**: Point CLI tools (Claude Code, OpenCode, Pi, or others accepting custom Anthropic/OpenAI-compatible base URLs) at a LiteLLM proxy with the `otel` callback writing into an OpenTelemetry Collector. This generates spans with per-request input/output token counts, model, latency, and user agent without harness-specific instrumentation.
* **MCP Testing**: Point MCP Conformance at the proxy or gateway in front of the server, not just the server itself, to surface buffering and protocol bugs in the middle layer that direct runs might miss.
* **Sandbox Requirements**: Harbor and Inspect SWE expect container sandboxes.

Note: Claude Code's own monitoring can send to the same collector, but on local models it may report phantom costs and only session-level metrics.

#AIAgents #LLMEvaluation #MCP #OpenTelemetry #AIEngineering

---

*Source: [anhermon/awesome-agent-observability](https://github.com/anhermon/awesome-agent-observability)*
