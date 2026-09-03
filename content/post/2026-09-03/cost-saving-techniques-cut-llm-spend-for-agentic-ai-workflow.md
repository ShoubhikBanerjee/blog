---
title: "Cost‑saving techniques cut LLM spend for agentic AI workflows"
description: "ProjectDiscovery applied this to their security testing agent Neo in April 2026."
date: 2026-09-03T18:04:33+05:30
tags: [LLM, AgenticAI, PromptCaching, CostOptimization]
categories: [AI]
image: "https://www.getreadyforagents.com/blog/agent-token-economics-cost-efficiency-production-hero.png"
author: "Shoubhik Banerjee"
draft: false
---

# Cost‑saving techniques cut LLM spend for agentic AI workflows

ProjectDiscovery applied this to their security testing agent Neo in April 2026.
The result was a 59 percent reduction in LLM costs within the first few days, reaching 70 percent by day ten.

## 🔍 Overview
- "An agent runs a loop: it reasons, calls a tool, reads the result, updates its plan, and repeats."
- "Every iteration carries the full conversation history forward."
- "By step five of a ten-step task, the model is reading everything that came before it on every single call."
- "Context length grows with each step, and cost scales with context length."

## 📊 Cost Challenge
- "According to research from Antino and Zylos, LLM API calls account for 70 to 85 percent of total agentic AI cost, and agents make three to ten times more LLM calls than simple chatbots."
- "Unoptimized production agents regularly reach $10 to $100 per session in API spend."
- "That ceiling matters because 88 percent of organisations are experimenting with agents, but only 23 percent are actively scaling, and Gartner projects 40 percent of agentic AI projects will be cancelled by 2027."

## 📏 Measuring First
- "You cannot optimise what you have not measured."
- "Instrument every LLM call before you write a single optimisation."
- "Record input tokens, output tokens, model name, task type, and step number."
- "Aggregate by task run, not by request, so you can see the full cost of one unit of work."
- "If your cost‑per‑task spikes after step three, that tells you the context is accumulating faster than the task is progressing, which points directly at context compaction as the right fix."
- "Store these records somewhere you can query them by task type."
- "After one week of load testing, you will have a cost distribution per task type that you can use to set per‑task budgets and to forecast monthly spend at your target volume."

## 💾 Prompt Caching
- "If your system prompt is long, your agent pays full price for it on every call."
- "Prompt caching lets the model provider store the computed representation of a static prefix and charge a fraction of the normal input rate for subsequent calls that reuse it."
- "The technique requires that the cacheable content sits at the start of the prompt and stays stable across calls, so structure your prompts with the static system instructions first and the variable task context after."
- "One developer account dropped from $720 per month to $72."

## 🧩 Model Routing
- "Not every step in an agentic workflow needs a frontier model."
- "Planning and synthesis benefit from the best reasoning available."
- "Classification, intent detection, filtering, and repeated sub‑tasks often produce equally reliable results from a model that costs a tenth as much."
- "Build a routing layer that maps task types to model tiers."
- "The decision criterion is whether the step requires open‑ended reasoning or whether it fits inside a well‑defined scope where a smaller model can be reliable."
- "Test each route with representative inputs before you trust it in production."

## 🛠️ Context Summarisation
- "The most direct attack on the quadratic growth problem is to stop the context from growing unchecked."
- "At each step, summarise completed sub‑tasks into a compact record and drop the raw turn history."
- "This requires a small summarisation call, which adds a modest cost at each checkpoint, but that cost is fixed per step rather than proportional to total history length."
- "For tasks beyond five or six steps, compaction almost always pays for itself."

#LLM #AgenticAI #PromptCaching #CostOptimization

---

*Source: [Agent Token Economics: Engineering Cost Efficiency Before Your First Production Deployment — Agentic Ready](https://www.getreadyforagents.com/blog/agent-token-economics-cost-efficiency-production/)*
