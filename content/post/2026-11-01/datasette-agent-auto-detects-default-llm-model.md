---
title: "Datasette Agent Auto-Detects Default LLM Model"
slug: "datasette-agent-auto-detects-default-llm-model"
description: "On 31st October 2026, the datasette‑llm plugin received a small user‑experience improvement that lets Datasette Agent automatically pick up the default model used by the underlying LLM."
date: 2026-11-01T22:01:19+05:30
tags: [Datasette, LLM, AI, OpenSource, UX]
categories: ["AI", "Artificial Intelligence", "Data Management", "Software Development"]
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Agent Auto-Detects Default LLM Model

On 31st October 2026, the datasette‑llm plugin received a small user‑experience improvement that lets Datasette Agent automatically pick up the default model used by the underlying LLM.

## 🔍 Overview
- The plugin now detects the default LLM model, removing the need for manual model configuration.

## ⚙️ How it works
- When launching Datasette Agent, the plugin reads the default model setting from the LLM environment.
- If a default model is present, the agent starts without the `-s plugins.datasette-agent.default_model` flag.

## 🚀 Availability
- The change is available as of 31 Oct 2026.
- Example command with the new behavior:
  ```
  uvx --with datasette-agent datasette content.db --internal internal.db
  ```

## 📜 Previous requirement
- Before the update, users had to specify the model explicitly, e.g.:
  ```
  -s plugins.datasette-agent.default_model gpt-6-astra
  ```

## 💡 Why it matters
- Reduces setup steps for users.
- Streamlines the workflow for developers testing Datasette Agent.

#Datasette #LLM #AI #OpenSource #UX

---

*Source: [Release: datasette-llm 0.1a9](https://simonwillison.net/2026/Oct/31/datasette-llm/)*
