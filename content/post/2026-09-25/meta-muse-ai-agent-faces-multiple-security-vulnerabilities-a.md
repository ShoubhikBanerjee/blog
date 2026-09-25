---
title: "Meta Muse AI Agent Faces Multiple Security Vulnerabilities and Data Leaks"
slug: "meta-muse-ai-agent-faces-multiple-security-vulnerabilities-and-data-leaks"
description: "Meta's new consumer-facing AI agent, Muse, has encountered two security disclosures in a single week, including an exploit allowing account hijacking and a leak of its root filesystem."
date: 2026-09-25T12:04:19+05:30
tags: [Meta, Muse, Cybersecurity, AIAgents, DataPrivacy]
categories: ["AI", "AI Agents", "Cybersecurity", "Artificial Intelligence"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/STKB394_MUSE_AI_CVIRGINIA_A.png?quality=90&strip=all&crop=0%2C9.9676601489831%2C100%2C80.064679702034&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Meta Muse AI Agent Faces Multiple Security Vulnerabilities and Data Leaks

Meta's new consumer-facing AI agent, Muse, has encountered two security disclosures in a single week, including an exploit allowing account hijacking and a leak of its root filesystem.

## 🔍 Security Issues

* **Filesystem Leak:** Peter James and Jonny L. Saunders independently coaxed Muse into sharing its entire root filesystem, including Ubuntu system files, internal documentation, and app templates. Saunders noted that Muse had "Almost no prompt injection resistance."
* **Account Hijacking:** Security researcher Patrick Wardle discovered a zero-day vulnerability that allows attackers to hijack the AI agent, redirect transcription processing, and gain complete control of a user's Muse account. Meta issued a hotfix for this issue.

## 🧩 How it Works

* **Infrastructure:** Muse runs in persistent Linux virtual machines for each user. Zuckerberg stated these are "isolated linux computer[s] with a browser, CPU, memory, and storage."
* **Data Handling:** The agent stores its memory in plain Markdown files and performs a nightly "dream" review of recent conversations to create guidance for future interactions.
* **Capabilities:** Many capabilities are hard-coded, such as the ability to cancel subscriptions and the "machinery that manages runaway agent spawning."
* **Integrations:** James found references to "Meta Home Link," which appears to provide Muse access to devices on a home network.

## ⚙️ Key Details

Researchers James and Saunders gained access to JSON and Markdown files describing "Hatch" (the internal name for Muse), which detail how the system:
* Processes requests
* Handles data
* Connects to services like Gmail

## 💡 Why it Matters

Meta representatives have responded to the filesystem leaks as follows:

| Representative | Perspective |
| :--- | :--- |
| Daniel Roberts (Spokesperson) | Compared it to a laptop, stating "of course you can see the files" and that exporting VM data provides no privileged access to Meta infrastructure or other users' data. |
| Nat Friedman (Superintelligence Labs) | Tweeted that this was "intended behavior." |
| David Singleton (Superintelligence Labs) | Suggested users view Muse as a "free computer in the cloud" where they can do almost anything they could with a computer under their desk. |

## 🚀 Availability

According to an Apptopia estimate, Muse has 600,000 daily active users in the US and topped the App Store charts shortly after its release.

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/09/STKB394_MUSE_AI_CVIRGINIA_A.png?quality=90&strip=all&crop=0.95588235294118%2C0%2C98.088235294118%2C100&w=2400)

#Meta #Muse #Cybersecurity #AIAgents #DataPrivacy

---

*Source: [Muse will apparently let you download its entire filesystem](https://www.theverge.com/ai-artificial-intelligence/1000222/meta-muse-ai-filesystem)*
*Source: [Muse sure looks a lot like OpenClaw](https://www.theverge.com/report/1000180/muse-openclaw-instinct-lookalike)*
