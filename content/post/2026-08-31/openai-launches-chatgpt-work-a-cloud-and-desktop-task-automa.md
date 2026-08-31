---
title: "OpenAI launches ChatGPT Work, a cloud and desktop task‑automation product"
description: "OpenAI announced **ChatGPT Work** on July 9th and has been iterating on it since."
date: 2026-08-31T19:35:04+05:30
tags: [OpenAI, ChatGPTWork, AItools]
categories: [AI]
image: "https://static.simonwillison.net/static/2026/chatgpt-work-card.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI launches ChatGPT Work, a cloud and desktop task‑automation product

OpenAI announced **ChatGPT Work** on July 9th and has been iterating on it since.

## 📦 What is ChatGPT Work
- ChatGPT Work is actually two products.
- The cloud‑based version is accessed via **chatgpt.com** or the ChatGPT mobile apps.
- The desktop version is the app that used to be called **Codex**; installing it gives access to a version of ChatGPT Work that can access files and run programs on your computer.

## 💸 Pricing & Access
- Available only to subscribers paying **$20 / month and up**.
- Free users and $8 / month “Go” users do **not** have access.
- Work sessions are billed against your **Codex allowance**, while Chat sessions have a separate allowance.

## 🎛️ Interface
- The interface uses a **tab selector** that presents Work as an alternative to **Chat**.
- Use **Chat** when you want an answer, explanation, brainstorm, or short draft.
- Use **ChatGPT Work** when you want ChatGPT to complete a task with a clear outcome (e.g., a brief, deck, analysis, recurring update, workflow, or file you can review and use).

## ⚙️ Key Features
- **Code execution environment with Internet access** (the environment can talk to the rest of the internet; Chat cannot).
- **Headless Chrome browser** that can launch a full Chrome instance, load websites, fill out forms, take screenshots, and run JavaScript against the DOM.
- **Persistent filesystem** shared between sessions. Each Work session gets a scratch folder (e.g., `/workspace/scratch/e00a0a017944`) that persists across sessions; the `/workspace` volume is mounted to all running Work sessions, so file edits are instantly visible to others.
- Ability to **publish ChatGPT Sites** and **build and deploy entire websites** using Cloudflare Workers.
- Ability to run **sub‑agent sessions** with **Sol, Luna, and Terra**.
- **Scheduled prompt automations** (may also be available in Chat).
- Can be configured with a specific list of allowed domains; default appears to be open to all.
- When a site requires sign‑in, the browser can prompt you to enter passwords and 2FA codes without those credentials passing through the model.

## 🧩 Model Options
| Model | Reasoning Levels |
|-------|-------------------|
| GPT‑5.6 Sol | Light, Medium, High, Extra High, Max, Ultra |
| GPT‑5.6 Luna | Light, Medium, High, Extra High, Max, Ultra |
| GPT‑5.6 Terra | Light, Medium, High, Extra High, Max, Ultra |
| GPT‑5.5 | Light, Medium, High, Extra High |

- These models appear to be the same models available through the OpenAI API.
- In **Chat**, the selection is different: 5.6 Instant, Medium, High, Extra High, and **Pro** (Pro is exclusive to Chat and only available to $100 / month+ subscribers; $20 / month subscribers cap at High).

## 🌐 Comparison with Chat
- Chat gets a **fresh filesystem** for each chat session.
- Chat cannot install additional software packages or interact with websites/APIs; such access is blocked by the container proxy.
- Claude’s equivalent container has allowed restricted internet access since last September, but ChatGPT Work allows a whole lot more, including open‑internet access by default.

## 🚀 Availability
- Both cloud and desktop flavors of ChatGPT Work are currently limited to paying subscribers at $20 / month and higher.
- Access is via the web, mobile apps, or the desktop app (formerly Codex).

#OpenAI #ChatGPTWork #AItools

---

*Source: [Understanding ChatGPT Work](https://simonwillison.net/2026/Aug/30/understanding-chatgpt-work/)*
