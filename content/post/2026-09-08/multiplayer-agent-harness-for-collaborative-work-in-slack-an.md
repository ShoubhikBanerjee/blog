---
title: "Multiplayer Agent Harness for Collaborative Work in Slack and Web"
slug: "multiplayer-agent-harness-for-collaborative-work-in-slack-and-web"
description: "A new multiplayer agent harness for work has been introduced, enabling employees to work independently in isolated workspaces or collaborate with an agent in projects, group messages, and Slack..."
date: 2026-09-09T00:31:26+05:30
tags: [AIagents, Slack, TypeScript, Productivity, SoftwareDevelopment]
categories: ["AI Agents", "Software Engineering", "Enterprise Software"]
image: "https://avatars.githubusercontent.com/u/153323858?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Multiplayer Agent Harness for Collaborative Work in Slack and Web

A new multiplayer agent harness for work has been introduced, enabling employees to work independently in isolated workspaces or collaborate with an agent in projects, group messages, and Slack channels.

## 🔍 Overview

The system allows users to customize their own agent while maintaining the ability to work collaboratively. Identity and configuration are consistent between the web app and Slack. Key capabilities include:

* **Internal Search:** Search across the web, databases, documents, email, and internal notes.
* **Inbox Management:** Triage inboxes on a schedule with reply drafts and labels by learning a user's writing voice from past sends.
* **Development Workflow:** Work in existing repositories to monitor CI, run tests, check system logs, and open PRs.
* **Project Tracking:** Post follow-ups and updates in shared channels to track projects.
* **App Creation:** Build and publish custom internal apps to specific people.

## 🧩 How it works

Each person and room is provided with its own scoped memory, permissions, files, keychain view, durable sandbox, crons, and web apps. 

* **Core Architecture:** The core runs TypeScript on Node and uses Fastify for HTTP. A Postgres persistence layer manages session history, user data, and other durable state.
* **Integration:** The web UI, public portal, and admin panel are optional plugins over the core's HTTP API. Slack is an optional in-process plugin supervised through a direct service client.
* **Tooling:** The agent uses a small, fixed tool surface. The `execute` tool allows the agent to run commands in its own isolated, durable sandbox where installed tools remain installed.
* **Tech Stack:** The Slack plugin uses Bolt, while the web UI utilizes Vite for builds and Lit for rendering.
* **Vendor Neutrality:** The core is driven by Pi, OpenCode, Codex, and Claude Code, meaning deployments are not tied to a single vendor.

## ⚙️ Key details

Administrators can set a security posture, org-level configuration, and determine available models and harnesses. 

| Security Posture | Description |
| :--- | :--- |
| Strict | Every harness tool call requires human approval, except for two no-effect turn enders. |
| Auto (default) | A classifier screens tool results and provenance-labelled external data; deployments can use their own screening proxy. |
| Dangerous | No pauses between tool calls and no content screening. |

Regardless of the posture, a predeclared command policy applies to provide hard denials and approval rules for destructive SQL or recursive deletes. 

Additional technical specifications include:
* **Deployment:** Every company's specific configuration, infrastructure, custom tools, skills, and sandbox image live in a deployment directory validated and deployed via the qm CLI. Each deployment runs in the operator's own cloud account.
* **Skills:** Skills are scope-owned and shareable by grant. Skill packs can be imported from git repositories, and admin-gated promotion to the whole org is available.
* **Automation:** Inbound webhooks, watches, and crons run work independently.
* **Memory:** Built-in notebooks are available, though memory can be routed by scope to external providers.

#AIagents #Slack #TypeScript #Productivity #SoftwareDevelopment

---

*Source: [yc-software/qm](https://github.com/yc-software/qm)*
