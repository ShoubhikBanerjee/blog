---
title: "Python Web UI for Mobile File Editing Built with Codex Remote and GPT-6"
slug: "python-web-ui-for-mobile-file-editing-built-with-codex-remote-and-gpt-6"
description: "I built a Python web app on my phone using Codex Remote and GPT-6 Astra Extra High to view and edit files in a folder without routing credentials through the LLM."
date: 2026-10-13T18:11:09+05:30
tags: [Python, Codex, GPT6, Tailscale, WebUI]
categories: ["AI", "Software Development", "Artificial Intelligence", "Web Technologies", "Networking"]
image: "https://static.simonwillison.net/static/2026/web-edit-card.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Python Web UI for Mobile File Editing Built with Codex Remote and GPT-6

I built a Python web app on my phone using Codex Remote and GPT-6 Astra Extra High to view and edit files in a folder without routing credentials through the LLM.

## 🔍 Overview
- Project created on 12th October 2026 from a phone.
- Goal: edit a credentials file directly, avoiding round‑tripping through the LLM.
- Result: a web UI for browsing and editing files in a folder.

## 🛠️ How it works
- Codex Remote and GPT‑6 Astra Extra High generated the Python web app.
- The app runs over a Tailscale network, allowing an agent to start it and a phone to connect securely.
- File browsing interface is provided (see image).
- Editing is powered by **CodeMirror 6**.
- **Monaco** was considered but was rejected because it lacks a great mobile experience.

## ⚙️ Key details
- Uses Python 3.11 (as indicated by the “Hello Python 3.15, goodbye 3.10, and now I can use 3.11” note).
- Designed for mobile use: accessible from a phone via Tailscale.
- Credentials remain on the device; they are not sent through the LLM.

## 🚀 Availability
- Intended to be launched by an agent on the Tailscale network.
- Once running, files can be edited directly from the phone’s browser.


![figure](https://static.simonwillison.net/static/2026/web-edit.webp)

#Python #Codex #GPT6 #Tailscale #WebUI

---

*Source: [Release: web-edit 0.1a0](https://simonwillison.net/2026/Oct/12/web-edit/)*
