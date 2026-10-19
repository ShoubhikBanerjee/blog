---
title: "Updated llm-echo Debug Plugin Simulates Token Usage for Tool Calls and System Prompts"
slug: "updated-llm-echo-debug-plugin-simulates-token-usage-for-tool-calls-and-system-prompts"
description: "A developer has enhanced the llm-echo debug plugin to simulate token usage tracking for additional components in LLM interactions. The update enables more accurate cost and performance testing during..."
date: 2026-10-19T06:06:00+05:30
tags: [AIDevelopment, LLMTools, Debugging, TokenUsage]
categories: ["AI", "Artificial Intelligence", "Software Development", "Tools"]
author: "Shoubhik Banerjee"
draft: false
---

# Updated llm-echo Debug Plugin Simulates Token Usage for Tool Calls and System Prompts

A developer has enhanced the llm-echo debug plugin to simulate token usage tracking for additional components in LLM interactions. The update enables more accurate cost and performance testing during development.

## 🔍 Overview
The llm-echo plugin acts as a non-LLM "model" that repeats input prompts verbatim. It serves as a testing tool for validating prompt structures and token accounting without invoking actual language models.

## ⚙️ Key details
- Now tracks tokens for: **tool calls**, **system prompts**, and **reasoning steps**
- Provides simulated input/output token counts in usage reports
- Maintains existing functionality for echoing prompts and context

## 🧩 Example usage
```bash
uvx --with llm-echo llm -m echo 'hi there' -o thinking 1 --usage
```
**Output**:
```
First I consider the prompt, then I decide what to say.
{
  "prompt": "hi there",
  "system": "",
  "attachments": [],
  "stream": true,
  "previous": []
}
Token usage: 2 input, 24 output
```

## 💡 Why it matters
This update allows developers to debug token consumption across more interaction elements, improving cost estimation and prompt optimization before deploying to real models.

#AIDevelopment #LLMTools #Debugging #TokenUsage

---

*Source: [Release: llm-echo 0.5](https://simonwillison.net/2026/Oct/18/llm-echo/)*
