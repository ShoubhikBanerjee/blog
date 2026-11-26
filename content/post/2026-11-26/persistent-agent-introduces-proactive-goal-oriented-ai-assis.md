---
title: "Persistent Agent introduces proactive, goal-oriented AI assistant for Slack teams"
slug: "persistent-agent-introduces-proactive-goal-oriented-ai-assistant-for-slack-teams"
description: "Persistent Agent has been introduced as a proactive, always-on, goal-oriented AI assistant designed to integrate into Slack teams. Built on Managed Deep Agents (MDA), the system functions as a..."
date: 2026-11-26T12:19:42+05:30
tags: [PersistentAgent, AIAgents, Slack, LangSmith, Automation]
categories: ["AI", "AI Agents", "Productivity Tools", "Software Development"]
image: "https://avatars.githubusercontent.com/u/245194860?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Persistent Agent introduces proactive, goal-oriented AI assistant for Slack teams

Persistent Agent has been introduced as a proactive, always-on, goal-oriented AI assistant designed to integrate into Slack teams. Built on Managed Deep Agents (MDA), the system functions as a background agent capable of managing workflows, conducting research, and handling tasks to support team productivity.

## 🧩 How it works

Persistent Agent operates through a series of specialized capabilities:

* Personal memory: Remembers individual user preferences and decisions.
* Goals: Tracks user goals and advances them in the background.
* Dreaming: Executes a nightly job to consolidate and clean up memory.
* Playbooks: Enables the adoption of specific workflows and organizational knowledge.
* Watch mode: Monitors channel messages and intervenes only when assistance is requested or relevant.
* Background work: Runs asynchronous subagents for research and review.
* Browser use: Interacts with websites directly through a browser.

## ⚙️ Key details

The system utilizes various integrations and configurations to function:

| Integration | Purpose |
| :--- | :--- |
| LangSmith Tool Gateway | Accesses tools like Gmail, GitHub, Slack, and Linear |
| Model provider API | Authorizes and pays for model calls (Anthropic or OpenAI) |
| LangSmith API key | Authenticates the CLI for deployment and development |
| Connected app account | Allows tools to access external accounts (Google, Linear, GitHub) |

## 🚀 Availability

To deploy Persistent Agent, users require:

* A LangSmith workspace on a Plus or Enterprise plan.
* An Anthropic or OpenAI API key, or the LangSmith LLM Gateway.
* A Slack workspace for app installation.
* Deployment via the command: `uv run mda deploy`.
* Configuration using `AGENT_MODEL=anthropic:claude-opus-5-5`.

#PersistentAgent #AIAgents #Slack #LangSmith #Automation

---

*Source: [langchain-samples/Persistent-Agent](https://github.com/langchain-samples/Persistent-Agent)*
