---
title: "Voice‑Driven Coding Adds Newsletters Page to Blog with GPT‑6 Astra"
slug: "voicedriven-coding-adds-newsletters-page-to-blog-with-gpt6-astra"
description: "I shipped a new feature for my blog today: the Newsletters page, which offers an index of all of the newsletters I’ve sent out, both my free weekly Substack and my monthly sponsors‑only updates."
date: 2026-10-09T22:05:01+05:30
tags: [ChatGPT, VoiceCoding, Django, AIProductivity]
categories: ["AI", "Artificial Intelligence", "Software Development", "Web Development", "Productivity Tools"]
image: "https://static.simonwillison.net/static/2026/newsletters-card.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Voice‑Driven Coding Adds Newsletters Page to Blog with GPT‑6 Astra

I shipped a new feature for my blog today: the Newsletters page, which offers an index of all of the newsletters I’ve sent out, both my free weekly Substack and my monthly sponsors‑only updates.

## 🎙️ Voice‑Driven Development
- Built almost entirely using my voice while cooking dinner.
- Used the ChatGPT desktop app, Codex tab, voice conversation mode, connected to a local development environment.
- Started the session with the command “Start dev server and open in browser”.
- Clicked the **Start new voice chat** button (the one to the right of the microphone) and placed the laptop in the kitchen.
- Model used: **GPT‑6 Astra High**.
- The model replied, asked occasional clarifying questions, and edited code live.
- Voice interaction lasted about half an hour (the time it took to cook dinner), followed by another half‑hour of typing‑based prompting to finalize the changes.

## 🗞️ Feature Overview
- An index page at `/newsletters/` that mixes the most recent Substack weekly newsletters and GitHub sponsors‑only monthly newsletters in reverse chronological order.
- Year‑by‑year archive pages (e.g., `/newsletters/2026/`).
- Newsletters appear on day and month archive pages but not on tag pages or the homepage.
- Weekly Substack newsletters link back to Substack; archived monthly newsletters have their own dedicated pages.
- Integrated with the site’s search engine.

## ⚙️ Technical Implementation
- Added a new Django model and migration to represent imported newsletters, plus Django Admin configuration.
- Created view code, templates, and import functions to populate the database from external sources.
- Data sources imported:
  | Source | Import Method |
  |---|---|
  | Most recent Substack items | RSS |
  | All other Substack items | Undocumented API `/api/v1/archive` (pagination discovered via Karen Spinner article) |
  | Published monthly newsletters | GitHub repository `simonw/monthly-newsletter-archive` |
  | Private sponsors‑only newsletter | Private GitHub repository (requires new API key) |
- Astra offered to export data for production import; I chose to keep the existing import‑script pattern.
- After the voice session, Codex created a Git branch and opened a pull request.
- Reviewed the PR, replaced a subprocess‑based Git call with an API‑based import using typing‑based prompts.
- Merged the PR to deploy the feature to production.

## 💡 Why It Matters
- Demonstrates a complete development workflow driven largely by voice, from model definition to deployment.
- Shows how a large language model can discover undocumented APIs, handle pagination, and generate Django code with minimal manual intervention.
- Highlights the practicality of integrating AI‑assisted coding into everyday tasks (e.g., cooking) without sacrificing code quality.


![figure](https://static.simonwillison.net/static/2026/codex-voice.webp)

![figure](https://static.simonwillison.net/static/2026/newsletters-page.webp)

#ChatGPT #VoiceCoding #Django #AIProductivity

---

*Source: [A new feature for my blog, built using my voice](https://simonwillison.net/2026/Oct/9/built-using-my-voice/)*
