---
title: "Amazon Quick defines a four‑question taxonomy for AI agents and triggers"
slug: "amazon-quick-defines-a-fourquestion-taxonomy-for-ai-agents-and-triggers"
description: "Over the past year, Amazon Quick’s agents have moved from answering questions to taking actions such as scheduling meetings, running research, and generating reports."
date: 2026-11-07T18:01:21+05:30
tags: [Amazon, AIAgents, Automation, LLM, AgenticAI]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Automation", "Machine Learning"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21505-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Quick defines a four‑question taxonomy for AI agents and triggers

Over the past year, Amazon Quick’s agents have moved from answering questions to taking actions such as scheduling meetings, running research, and generating reports.

## 🔍 Taxonomy
- The taxonomy decomposes agentic work into four plain questions: **When?**, **What?**, **Who?**, and **How?**
- **When** and **What** are carried by a *trigger* that starts the work and describes the task.
- **Who** is the *agent* that takes on the trigger.
- **How** is the set of *capabilities* (tools, skills, and workflows) the agent uses to perform the task.

## ⚙️ Triggers
- **Human‑initiated** – a person opens a conversation and asks the agent to do something.
- **Agent‑delegated** – one agent, mid‑task, invokes another to handle a sub‑problem.
- **Scheduled** – time‑based activation, e.g., “run financial research every Monday at 9 am.”
- **Event‑driven** – a signal from an external system such as a new email, a Slack mention, a file change, or a webhook.
- The trigger type influences execution style; a scheduled background task may stay conservative (do nothing if uncertain), while a human‑initiated trigger is responsive (ask rather than stop).

## 🤖 Agents
- An *agent* is defined as a **persistent, learning actor**.
- Two agents given identical input can differ because they carry different **instructions**, **capabilities**, and **histories**.
- The agent is the entity that **interprets** instructions; it is not the instructions themselves.
- **Instructions** are standing guidance that defines persona, role, context files, and operating principles.
- Everything else (LLM model, conversation history, triggers) is considered **extrinsic** and can be swapped without changing the agent.

## 🛠️ Capabilities
| Capability | Description |
|------------|-------------|
| **Tools** | Atomic operations with a typed schema (e.g., send an email, query a database, read a file). The caller sees a uniform interface: name, description, parameters, result. |
| **Skills** | Structured guidance with room for judgment; includes instructions plus resources (templates, scripts, examples). Loaded through progressive disclosure, allowing deep expertise without constant cost. |
| **Workflows** | Deterministic coordination of declared steps, control flow, branching, and error handling. Decision logic resides in code, not model inference. Example: a purchase‑approval route (budget check → manager sign‑off → finance) with fixed order but agent judgment inside each step. |
- Capabilities span a spectrum from fully agentic to fully deterministic.
- They are updated dynamically; for example, a charting library can be added in one session and removed the next.
- **Learned context** is memory that accumulates through use, such as queries that work for a tool, user‑preferred formatting, and edge cases they care about.

## 📚 Why it matters
- A request like “I want an agent that monitors my Slack and sends a digest every morning” is typically satisfied by **adding a trigger** to an existing agent rather than creating a new agent or workflow.
- This approach keeps the system modular: triggers activate work, agents interpret and act, and capabilities provide the concrete means.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21505-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21505-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/11/03/ML-21505-3.jpg)

#Amazon #AIAgents #Automation #LLM #AgenticAI

---

*Source: [Taxonomy of agentic primitives in Amazon Quick | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/taxonomy-of-agentic-primitives-in-amazon-quick/)*
