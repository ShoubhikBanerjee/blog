---
title: "Spawn Game Uses Autonomous AI Agents to Ship Code Hourly"
slug: "spawn-game-uses-autonomous-ai-agents-to-ship-code-hourly"
description: "Spawn, a massively multiplayer gaming environment, is being built and updated by a swarm of AI agents that modify live code and ship changes every hour."
date: 2026-10-30T22:02:41+05:30
tags: [AIAgents, GameDevelopment, AutonomousCoding, SoftwareEngineering]
categories: ["AI", "Artificial Intelligence", "Game Development", "Software Engineering"]
image: "https://static.simonwillison.net/static/2026-10-29/IMG_9406.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Spawn Game Uses Autonomous AI Agents to Ship Code Hourly

Spawn, a massively multiplayer gaming environment, is being built and updated by a swarm of AI agents that modify live code and ship changes every hour.

## 🔍 Overview
- Players interact with an in‑game agent called **Savi** by sending prompts that modify the game world.
- A user report describes creating a castle, summoning a dragon, and riding the dragon around the castle on a phone.

## 🤖 Autonomous Development
- Development is driven by a swarm of **Fable‑powered agents** that cost **over $3 million in tokens per month** ("we spend 30x payroll on AI tokens").
- The agents **change the live code directly** and ship to production **hourly**.
- **60 %** of work originates from a production error, a Savi bug report, an odd log entry, or a feature request.
- **Savi files bugs herself**; when a bug is hit, it is routed to an agent that decides whether it is a real bug, something not to fix, or an intentional design decision.
- Usually the resulting change is delivered to the user **within an hour**, accompanied by a message in the same chat.
- An hour without a ship is treated as a **SEV‑0** incident, the most severe kind of incident.
- Agents can retain only a **few hours of work** in their “head”; shipping faster helps them stay coherent.
- A broken change can be **rolled back in 30 seconds**, exactly where it broke and nowhere else.
- When a monitor or log alert fires, it starts or wakes an agent that owns the incident, and the team sometimes **breaks things on purpose** to verify recovery paths.

## 📊 Model Variants
| Model | Outcome |
|---|---|
| Fable 5 / 5.1 | Enabled the current level of autonomy (as cited by Jacob). |
| Opus 5.5 | Not sufficient for their needs ("doesn't quite hack it for them"). |
| GPT‑6 Astra | Applied security fixes by turning off every feature, leaving the product non‑functional. |

## ⚙️ Incident Handling Loop
- An alert triggers or awakens an agent responsible for the incident.
- The agent evaluates the bug, classifies it, and either ships a fix or decides on another action.
- The rapid ship‑and‑rollback capability keeps the production environment tight and responsive.

## 💡 Why It Matters
- The system creates a **continuous, hour‑long feedback loop** that only works because shipping never stops.
- It demonstrates that a game can serve as a substrate for testing the limits of today’s coding agents.
- The author notes uncertainty about applying this style to higher‑stakes software, but observes that it is **surprisingly effective for a game**.
- Extreme experiments, such as the GPT‑6 Astra security overhaul, highlight both the potential and the risks of autonomous code modification.


#AIAgents #GameDevelopment #AutonomousCoding #SoftwareEngineering

---

*Source: [Building a multiplayer game world with autonomous Fable-class models](https://simonwillison.net/2026/Oct/29/how-i-built-the-most-ai-pilled-company-in-the-world/)*
