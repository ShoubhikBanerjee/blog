---
title: "OpenAI launches GPT‑6 Sol and Luna with new non‑conversational plugin flag"
slug: "openai-launches-gpt6-sol-and-luna-with-new-nonconversational-plugin-flag"
description: "On 22 September 2026 OpenAI released two new GPT‑6 model families, GPT‑6 Sol and GPT‑6 Luna, and introduced a plugin flag that lets models opt out of conversational history."
date: 2026-09-23T06:05:34+05:30
tags: [OpenAI, GPT6, AIPlugins, LLM]
categories: ["AI", "Machine Learning", "Large Language Models", "AI Platforms", "AI Market"]
author: "Shoubhik Banerjee"
draft: false
---

# OpenAI launches GPT‑6 Sol and Luna with new non‑conversational plugin flag

On 22 September 2026 OpenAI released two new GPT‑6 model families, GPT‑6 Sol and GPT‑6 Luna, and introduced a plugin flag that lets models opt out of conversational history.

## 🔍 Overview
- New model identifiers: `gpt-6-sol` (GPT‑6 Sol) and `gpt-6-luna` (GPT‑6 Luna).
- Plugins can now declare `supports_conversation = False` for models that only accept single‑turn prompts.
- When such a model receives assistant or tool history, the LLM raises `llm.ConversationNotSupported` and the chat system rejects the session before it starts.
- The first plugin to use this flag is **llm-typesafe**.
- Reasoning traces in the Markdown output of LLM logs are now wrapped in `<details><summary>` tags.
- The release is noted alongside Claude Opus 5.5 and a new price war on the same date.

## 🧩 Model Variants
| Model Identifier | Model Name |
|------------------|------------|
| `gpt-6-sol`      | GPT‑6 Sol |
| `gpt-6-luna`     | GPT‑6 Luna |

## ⚙️ Plugin Conversation Flag
- Plugins set `supports_conversation = False` to indicate single‑turn only capability.
- If a model with this flag receives multi‑turn history, the LLM throws `llm.ConversationNotSupported`.
- The chat interface blocks the session before it begins.
- **llm-typesafe** is the inaugural plugin using this functionality.

## 📄 Reasoning Trace Formatting
- Reasoning traces embedded in LLM logs are now enclosed in HTML `<details><summary>` blocks, improving readability in Markdown outputs.

## 💰 Market Context
- The announcement coincides with mentions of Claude Opus 5.5, GPT‑6 Sol, GPT‑6 Luna, and a new price war on 22 September 2026.

#OpenAI #GPT6 #AIPlugins #LLM

---

*Source: [Release: llm 0.36](https://simonwillison.net/2026/Sep/22/llm/)*
