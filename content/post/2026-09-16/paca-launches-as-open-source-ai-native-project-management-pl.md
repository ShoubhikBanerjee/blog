---
title: "Paca Launches as Open-Source AI-Native Project Management Platform"
slug: "paca-launches-as-open-source-ai-native-project-management-platform"
description: "Paca is a new self-hosted project management platform designed for Scrum teams where humans and AI agents collaborate as equals on the same boards and sprints."
date: 2026-09-17T00:45:10+05:30
tags: [Paca, OpenSource, AIagents, Scrum, ProjectManagement]
categories: ["AI", "AI Agents", "Software Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/269367978?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Paca Launches as Open-Source AI-Native Project Management Platform

Paca is a new self-hosted project management platform designed for Scrum teams where humans and AI agents collaborate as equals on the same boards and sprints.

## 🔍 Overview
Paca is an AI-native, open-source alternative to platforms such as Jira, Trello, ClickUp, and Monday. Unlike chatbots that are bolted on the side, AI agents in Paca are integrated teammates that participate in the Scrum process.

## 🧩 How it works
AI agents in Paca function as equal teammates within the Scrum process through the following capabilities:
* Appearance on the Scrumban board alongside human teammates.
* Assignment to sprints.
* Picking up tasks from the backlog and updating status in real time.
* Collaborating on BDD specs to help Product Owners and BAs write Gherkin scenarios.
* Contributing to System Design Documents.
* Probing, sensing, and responding to emerging complexity.

## ⚙️ Key details
Paca ships as a small, focused core where the UI, data model, and workflows are configurable and extendable.

* **Configuration**: Project-level configuration files drive board layouts, sprint rules, field definitions, statuses, workflows, and agent behavior.
* **Plugins**: Any part of the platform can be extended or replaced via plugins. 
    * Backend plugins are compiled to WebAssembly (WASM) and can be written in Go, Rust, AssemblyScript, or any language with a WASM target.
    * Frontend plugins use standard module bundles.
    * Plugins run in a sandboxed environment utilizing a capability-based permission model.
* **Plugin Marketplace**: Users can browse and install community plugins via the UI by navigating to Settings $\rightarrow$ Plugins $\rightarrow$ Marketplace.

## 🚀 Availability
* **License**: 100% open-source (Apache 2.0).
* **Cost**: Free forever.
* **Deployment**: Self-hosted, ensuring users own everything.

#Paca #OpenSource #AIagents #Scrum #ProjectManagement

---

*Source: [Paca-AI/paca](https://github.com/Paca-AI/paca)*
