---
title: "Google Research introduces WikiSkill to give AI agents persistent memory"
description: "Google Research has introduced a framework called WikiSkill, which separates an AI model's core intelligence from its procedural memory. By allowing agents to record and learn from their past..."
date: 2026-08-30T23:04:28+05:30
tags: [GoogleResearch, AI, MachineLearning, AIAgents, Gemini]
categories: [AI]
image: "https://superpowerdaily.com/podcast/2026-08-30-google-gives-ai-agents-a-memory-of-past-work/opengraph-image"
author: "Shoubhik Banerjee"
draft: false
---

# Google Research introduces WikiSkill to give AI agents persistent memory

Google Research has introduced a framework called WikiSkill, which separates an AI model's core intelligence from its procedural memory. By allowing agents to record and learn from their past performance, the system enables models to improve task execution without requiring fine-tuning or changes to the model's parametric memory.

## 🧩 How it works

The WikiSkill system functions through three distinct layers:

* Raw layer: Silently records detailed execution traces of tasks, including API calls, searched websites, and success or failure data.
* Wiki layer: Utilizes a 'Wiki Maintainer' to analyze raw logs and distill them into generalized lessons stored in a structured wiki.
* Skill proposer: Translates wiki insights into targeted procedural instructions, known as skills, which are provided to the agent only when relevant.

## ⚙️ Key details

The system employs a gating mechanism to maintain performance quality. Before a new skill is implemented, it is tested against a validation dataset. If performance decreases compared to the baseline, the skill is rejected and rolled back.

## 📊 Performance impact

| Model | Baseline Score | Post-WikiSkill Score |
| :--- | :--- | :--- |
| Gemini 3.5 Flash | 49.5 | 68.1 |
| Qwen 3.627b | 39.4 | 63.3 |

#GoogleResearch #AI #MachineLearning #AIAgents #Gemini

---

*Source: [Google gives AI agents a memory of past work | Superpower Daily: The Signal](https://superpowerdaily.com/podcast/2026-08-30-google-gives-ai-agents-a-memory-of-past-work)*
