---
title: "Claude Code edits Obsidian vaults directly via file system"
slug: "claude-code-edits-obsidian-vaults-directly-via-file-system"
description: "Claude Code can edit an Obsidian vault without a special plugin. Because an Obsidian vault is just a local folder of plain‑text .md files, the agent reads and writes those files directly."
date: 2026-10-11T18:05:47+05:30
tags: [Obsidian, ClaudeCode, AIAgents, Productivity]
categories: ["AI", "Productivity Tools", "Artificial Intelligence", "Software Integration"]
image: "https://horadecodar.com.br/wp-content/uploads/2026/08/claude-code-obsidian.png"
author: "Shoubhik Banerjee"
draft: false
---

# Claude Code edits Obsidian vaults directly via file system

Claude Code can edit an Obsidian vault without a special plugin. Because an Obsidian vault is just a local folder of plain‑text .md files, the agent reads and writes those files directly.

## 🔍 Overview
- No magical integration; works because the vault is a folder with .md files.
- No official API, secret API, or mandatory plugin.

## 🧩 How it works
- Claude Code runs in a terminal opened inside the vault folder.
- The agent can create a note, rewrite a note, and add wikilinks directly in the vault.
- Actions require tool approval (Read, Edit, Write) or can be auto‑approved with `acceptEdits` mode.
- Edits can be undone with the `/rewind` command.

## ⚙️ Key details
- **Vault**: a folder on the file system.
- **Notes**: individual `.md` files, plain text, markdown syntax.
- **Configuration**: JSON files in `.obsidian` inside the vault; plugins store their `data.json` in their own folders.
- **Internal links**: use the wikilink syntax `[[link]]`; the graph view is just brackets in files.
- **Obsidian behavior**: detects external saves and reindexes the note automatically, even while the app is open.
- **Concurrent edits**: unsaved changes are merged automatically; Obsidian shows an external‑modification warning.
- **Permissions**: the agent is limited to the working directory and its subfolders; writing elsewhere needs explicit permission.
- No need to close Obsidian each time the agent runs.

## 🚀 Usage tips
- Open a terminal in the vault directory, start Claude Code, and treat the vault as a set of markdown files.
- Enable `acceptEdits` to stop prompting for each file change.
- Use `/rewind` to revert unwanted edits.

![figure](https://horadecodar.com.br/wp-content/uploads/2026/08/4c1b592e33e635326865081845fe2281-300x191.webp)

![figure](https://horadecodar.com.br/wp-content/uploads/2026/08/limite-de-uso-do-claude-code-300x158.png)

#Obsidian #ClaudeCode #AIAgents #Productivity

---

*Source: [Claude Code Obsidian: como o agente edita seu vault](https://horadecodar.com.br/claude-code-obsidian-2/)*
