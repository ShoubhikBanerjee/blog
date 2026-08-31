---
title: "New AI agent skills for real engineering workflows"
description: "A new set of AI agent skills has been introduced to address common failure modes in AI-assisted software development, focusing on alignment and process control."
date: 2026-08-31T22:29:11+05:30
tags: [AIagents, ClaudeCode, softwaredevelopment, engineering, workflow, skills]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/28293365?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New AI agent skills for real engineering workflows

A new set of AI agent skills has been introduced to address common failure modes in AI-assisted software development, focusing on alignment and process control.

## 🔍 Overview
The skills are designed to be small, easy to adapt, and composable, working with any model. They are based on decades of engineering experience and aim to fix misalignment between developers and agents, a frequent issue in AI-assisted development.

## 🧩 How it works
The skills are available in two formats:
- **Claude Code plugin**: Installs as a managed, read-only bundle that updates automatically when new versions are shipped. Users subscribe rather than fork.
- **[skills.sh](https://skills.sh/mattpocock/skills)**: Copies editable skill files into the project, allowing users to modify and customize them.

Installation options include:
- `claude plugins install mattpocock-skills`
- `/plugin install mattpocock-skills` (from inside a session)
- `npx skills@latest add mattpocock/skills`

The installer lets users select which skills to adopt, with `setup-matt-pocock-skills` recommended as one of them. For the editable version, skills are written as ordinary files in the repository, and updates are pulled manually via `npx skills update`.

## ⚙️ Key details
The skills address two primary challenges:
- **Misalignment**: A communication gap between users and agents, where the agent fails to understand requirements. The fix is a "grilling session" using:
  - `/grill-me`: For non-code use cases.
  - `/grill-with-docs`: Adds documentation to improve alignment.
- **Jargon**: Agents often struggle with project-specific terminology. `/grill-with-docs` includes a shared language document to help agents decode jargon.

The installer also configures project-specific settings, such as:
- Issue tracker (GitHub, Linear, or local files).
- Labels for ticket triage (used by `/triage`).
- Location for generated documentation.

## 🚀 Availability
- The Claude Code plugin is available in the official marketplace, with automatic updates.
- A native Codex plugin is planned (roadmap referenced in [`.agents/adr/0002-ship-as-a-claude-code-plugin.md`](./.agents/adr/0002-ship-as-a-claude-code-plugin.md)).
- Users can join a newsletter with ~60,000 other developers to stay updated on new skills and changes.

## 💡 Why it matters
The skills aim to improve AI-assisted development by:
- Reducing misalignment between users and agents.
- Providing composable, adaptable tools for real engineering workflows.
- Offering flexibility in installation and customization.

#AIagents #ClaudeCode #softwaredevelopment #engineering #workflow #skills

---

*Source: [mattpocock/skills](https://github.com/mattpocock/skills)*
