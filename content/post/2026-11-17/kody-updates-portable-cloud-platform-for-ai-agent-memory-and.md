---
title: "Kody Updates Portable Cloud Platform for AI Agent Memory and Automations"
slug: "kody-updates-portable-cloud-platform-for-ai-agent-memory-and-automations"
description: "Kody has introduced new updates to its portable agents' cloud, designed to manage the memory, keys, code, and automations of AI agents across Model Context Protocol (MCP) hosts. Built on Cloudflare..."
date: 2026-11-17T22:09:21+05:30
tags: [Kody, ModelContextProtocol, CloudflareWorkers, AIAgents, Monorepo]
categories: ["AI", "AI Agents", "Cloud Computing", "Software Development"]
image: "https://avatars.githubusercontent.com/u/344017445?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Kody Updates Portable Cloud Platform for AI Agent Memory and Automations

Kody has introduced new updates to its portable agents' cloud, designed to manage the memory, keys, code, and automations of AI agents across Model Context Protocol (MCP) hosts. Built on Cloudflare Workers, this source-available platform supports both individuals and teams by providing account isolation and a flexible development environment.

## 🔍 Overview
Kody provides an MCP-first architecture intended to work across compatible AI agent hosts, with ChatGPT serving as a likely primary host target. Rather than functioning as a general-purpose agent harness, Kody focuses on enabling portability for an agent's critical assets. Each account on the platform represents an isolated environment holding its own packages, jobs, credentials, memories, and related state. To maintain security, no account is given privileged status at runtime.

## 🧩 How it works
Instead of managing a large, static tool catalog, Kody prioritizes a compact MCP surface area designed around powerful flows. Key behaviors and request flows include:

* **Flow Preferences**: The platform favors powerful `search` and Code Mode `execute` flows.
* **Request Ordering**: OAuth requests are processed first, followed by MCP requests, and finally static assets.
* **Webhook Processing**: Webhook ingress, including GET subscription challenges, is handled in the Worker `fetch` path before being routed to TanStack Start.
* **Web Application**: The remaining website requests are routed through TanStack Start at `packages/worker/start/http-entry.ts`.
* **Client Assets**: Assets are bundled into `packages/worker/public/` and served via the `ASSETS` binding.

## ⚙️ Key details
The project utilizes an Nx monorepo structure following several epicflare starter conventions. Shared modules and worker roles are organized as follows:

| Module / Package Path | Description / Role |
| --- | --- |
| `packages/shared` (`@kody-internal/shared`) | Shared modules used across the repository |
| `packages/worker` | The origin app worker, with its entrypoint at `packages/worker/src/index.ts` |
| `packages/platform-worker` | Sibling worker managing platform services |
| `packages/runtime-worker` | Sibling worker managing runtime tasks |
| `packages/jobs-worker` | Sibling worker managing automated jobs |
| `packages/mock-servers/*` | Mock Workers for local testing and simulation |

For contributors getting started with development, the local dev server runs on `localhost:3742` by default. The command-line interface automatically selects the next free port if that one is occupied, and Wrangler manages both the local Cloudflare Workers runtime and the D1 database automatically. Developers and agents can refer to `AGENTS.md` for repository-specific guidelines, while `docs/contributing/project-intent.md` explains the core intent of the repository.

#Kody #ModelContextProtocol #CloudflareWorkers #AIAgents #Monorepo

---

*Source: [kody-hq/kody](https://github.com/kody-hq/kody)*
