---
title: "Claude Code plugin introduces Karpathy-inspired coding guidelines"
description: "A new CLAUDE.md file has been developed to improve Claude Code behavior, based on observations of LLM coding pitfalls."
date: 2026-08-31T19:35:04+05:30
tags: [ClaudeCode, LLM, coding, guidelines, AI, development]
categories: [AI]
image: "https://avatars.githubusercontent.com/u/254743058?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Claude Code plugin introduces Karpathy-inspired coding guidelines

A new CLAUDE.md file has been developed to improve Claude Code behavior, based on observations of LLM coding pitfalls.

## 🔍 Overview
The guidelines are derived from observations on LLM coding pitfalls and are implemented as a single file to enhance Claude Code's performance.

## ⚙️ Key details
The file outlines four principles to address common issues:

- **Explicit reasoning**: Forces the LLM to avoid silently picking an interpretation and running with it.
- **Avoid overengineering**:
  - No features beyond what was asked
  - No abstractions for single-use code
  - No error handling for impossible scenarios
  - Don't refactor things that aren't broken
- **Style and cleanup**:
  - Match existing style, even if you'd do it differently
  - Remove imports/variables/functions that your changes made unused
  - Don't remove pre-existing dead code unless asked
- **Traceability**: Every changed line should trace directly to the user's request.

The guidelines also emphasize strong success criteria to enable independent LLM loops, avoiding weak criteria like "make it work" that require constant clarification.

The "Goal-Driven Execution" principle transforms imperative instructions into declarative goals with verification loops.

## 🚀 Availability
The guidelines are available as a Claude Code plugin. To use them:
- Add the marketplace within Claude Code
- Install the plugin

This installs the guidelines as a plugin, making the skill available across all projects. The repository also includes a committed Cursor project rule (`.cursor/rules/karpathy-guidelines.mdc`) to apply the same guidelines in Cursor.

The guidelines are designed to be merged with project-specific instructions. They can be added to an existing `CLAUDE.md` or used to create a new one.

#ClaudeCode #LLM #coding #guidelines #AI #development

---

*Source: [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills)*
