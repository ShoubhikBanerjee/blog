---
title: "Using Claude and n8n to Query Ghost Content via API"
slug: "using-claude-and-n8n-to-query-ghost-content-via-api"
description: "I built a workflow that lets me query my Ghost‑hosted posts beyond the built‑in search."
date: 2026-09-09T00:51:34+05:30
tags: [Ghost, Claude, n8n, AIworkflow]
categories: ["AI"]
author: "Shoubhik Banerjee"
draft: false
---

# Using Claude and n8n to Query Ghost Content via API

I built a workflow that lets me query my Ghost‑hosted posts beyond the built‑in search.

## 🔍 Overview
- Problem: I can’t query my published content hosted on Ghost beyond using the basic search capabilities.
- Solution: By connecting the Ghost API endpoint with a Postgres‑hosted SaaS, an n8n sync workflow, a Claude Skill, and Claude Desktop, I can perform richer queries.

## 🧩 How it works
- **Ghost API endpoint** – provides programmatic access to published posts.
- **Postgres‑hosted SaaS** – stores the content for fast querying.
- **n8n sync workflow** – automates data extraction and synchronization.
- **Claude Skill** – interprets natural‑language queries.
- **Claude Desktop** – runs the skill locally for quick responses.

## ⚙️ Key details
- The combined setup enables query capabilities that go beyond Ghost’s native search.
- The workflow was assembled in just a few hours, illustrating how quickly a problem can become a viable solution.
- I am considering reproducing the same design to query content on Micro.blog.

## 🚀 Availability
- The solution is a personal workflow built with publicly available tools; it is not a commercial product.

## 💡 Why it matters
- Demonstrates a practical, low‑effort way to extend the functionality of existing SaaS platforms using AI and automation tools.

![figure](https://cdn.uploads.micro.blog/6803/2026/from-handwritten-notes-to-the-final-diagram.jpg)

#Ghost #Claude #n8n #AIworkflow

---

*Source: [Photos](https://blog.numericcitizen.me/)*
