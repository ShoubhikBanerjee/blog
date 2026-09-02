---
title: "Analysis of the OpenAI Codex desktop application runtime components"
description: "The OpenAI Codex desktop application, which has been rebranded to ChatGPT, includes a large runtime environment containing a variety of bundled software dependencies."
date: 2026-09-02T22:08:32+05:30
tags: [OpenAI, Codex, ChatGPT, SoftwareArchitecture]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# Analysis of the OpenAI Codex desktop application runtime components

The OpenAI Codex desktop application, which has been rebranded to ChatGPT, includes a large runtime environment containing a variety of bundled software dependencies.

## ⚙️ Key details

The application maintains a 1.7GB folder titled codex-primary-runtime. This directory includes the following software components:

| Component | Description |
| :--- | :--- |
| Python | Full installation |
| Node.js | Full installation |
| Poppler | Native binary |
| git | Native binary |
| LibreOffice | Open source office suite (forked from OpenOffice.org in 2010) |

## 🧩 How it works

The application utilizes specific plugin scripts to interface with these bundled tools. The directory ~/.cache/codex-runtimes/codex-primary-runtime/plugins/openai-primary-runtime/plugins/documents contains skills that instruct the system on how to locate and execute these binaries.

![figure](https://static.simonwillison.net/static/2026/codex-primay-runtime.webp)

#OpenAI #Codex #ChatGPT #SoftwareArchitecture

---

*Source: [Codex bundles LibreOffice](https://simonwillison.net/2026/Sep/1/codex-libreoffice/)*
