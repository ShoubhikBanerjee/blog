---
title: "Diagram Design Agent Skill Generates HTML and SVG Diagrams for AI Coding Environments"
slug: "diagram-design-agent-skill-generates-html-and-svg-diagrams-for-ai-coding-environments"
description: "A new agent skill named 'diagram-design' has been released, enabling AI coding assistants to generate self-contained HTML and SVG diagrams in a user's brand style."
date: 2026-11-12T22:08:51+05:30
tags: [d, i, a, g, r, a, m, d, e, s, i, g, n, a, g, e, n, t, s, k, i, l, l, s, h, t, m, l, s, v, g, c, o, d, i, n, g, a, s, s, i, s, t, a, n, t, s]
categories: ["AI", "A", "I", "A", "g", "e", "n", "t", "s", ",", "D", "e", "v", "e", "l", "o", "p", "e", "r", "T", "o", "o", "l", "s", ",", "D", "i", "a", "g", "r", "a", "m", "m", "i", "n", "g", ",", "W", "e", "b", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t"]
image: "https://avatars.githubusercontent.com/u/50469282?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Diagram Design Agent Skill Generates HTML and SVG Diagrams for AI Coding Environments

A new agent skill named "diagram-design" has been released, enabling AI coding assistants to generate self-contained HTML and SVG diagrams in a user's brand style.

## 🔍 Overview

The skill supports 48 diagram types and produces self-contained HTML + SVG files. It adheres to design constraints, including no shadows and no Mermaid.

## 🧩 How it works

The agent selects the diagram type, states its plan, and writes one `.html` file that can be opened by double-clicking.

## ⚙️ Key details

*   **Supported Hosts:** The skill works with Cursor, Claude Code, Codex, GitHub Copilot, Qoder, Factory Droid, Pi, Gemini CLI, Cline, Windsurf, and Amp.
*   **Installation Methods:**
    *   When multiple roots resolve, the CLI recommends **Symlink** for a canonical copy linked into each root.
    *   Pass `--copy` for independent copies per host.
    *   A selection resolving to a single directory is copied.
    *   Symlinks are unavailable on Windows without Developer Mode, so the CLI falls back to copies.
*   **Updates and Migration:**
    *   Standalone installs require `npx skills update diagram-design`.
    *   Marketplace installs follow native update paths.
    *   Existing standalone copies must be removed before using marketplace commands to avoid conflicts.
*   **Privacy:** [PRIVACY.md](PRIVACY.md) lists what the skill sends over the network.

## 🚀 Availability

Official builds come only from the repository. LittleMight, Cathryn Lavery's company, publishes the plugin directory listings.

#d #i #a #g #r #a #m #- #d #e #s #i #g #n #, # #a #g #e #n #t #- #s #k #i #l #l #s #, # #h #t #m #l #- #s #v #g #, # #c #o #d #i #n #g #- #a #s #s #i #s #t #a #n #t #s

---

*Source: [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design)*
