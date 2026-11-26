---
title: "i-have-adhd plugin provides ADHD-friendly output for coding assistants"
slug: "i-have-adhd-plugin-provides-adhd-friendly-output-for-coding-assistants"
description: "The i-have-adhd plugin was released to make AI-powered coding assistants more accessible for users with ADHD. The plugin reformats outputs as numbered action steps, leads with the next action, and..."
date: 2026-11-26T22:08:01+05:30
tags: [ADHD, AIassistant, plugins, accessibility]
categories: ["AI", "AI Assistants", "Accessibility", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/32200675?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# i-have-adhd plugin provides ADHD-friendly output for coding assistants

The i-have-adhd plugin was released to make AI-powered coding assistants more accessible for users with ADHD. The plugin reformats outputs as numbered action steps, leads with the next action, and avoids unnecessary tangents or pleasantries.

## 🧩 How it works
The plugin modifies how a coding assistant responds by:

- Breaking tasks into numbered steps
- Leading with immediate actions
- Ending with one concrete next step
- Making test failures visible
- Using matter-of-fact error messages

## ⚙️ Key details
The plugin is available as a skill that can be installed from https://github.com/ayghri/i-have-adhd. Refer to the repo's AGENTS.md for installation instructions.

| Action | Command |
|--------|----------|
| Uninstall current plugin | `claude plugin uninstall i-have-adhd` |
| Remove from marketplace | `claude plugin marketplace remove i-have-adhd` |
| Add forked version | `claude plugin marketplace add <your-username>/i-have-adhd` |
| Install specific fork | `claude plugin install i-have-adhd@i-have-adhd` |

## 🚀 Availability
The plugin can be installed immediately from the GitHub repository. The instructions require forking, editing `skills/i-have-adhd/SKILL.md`, then swapping your copy in.

## 💡 Why it matters
The approach is loosely based on *The Adult ADHD Tool Kit* by J. Russell Ramsay and Anthony L. Rostain, but adapted for how an LLM should respond rather than human daily organization. The output is ADHD-friendly—no diagnosis needed—and stops coding agents from burying answers in verbose explanations.

#ADHD #AI-assistant #plugins #accessibility

---

*Source: [ayghri/i-have-adhd](https://github.com/ayghri/i-have-adhd)*
