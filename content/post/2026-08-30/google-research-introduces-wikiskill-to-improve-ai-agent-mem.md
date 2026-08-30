---
title: "Google Research introduces WikiSkill to improve AI agent memory and performance"
description: "Google Research has introduced WikiSkill, a framework that enables AI agents to retain procedural memory from past attempts without requiring model retraining. By separating an agent's core..."
date: 2026-08-30T23:12:46+05:30
tags: [Google, AI, MachineLearning, Gemini]
categories: [AI]
image: "https://superpowerdaily.com/podcast/2026-08-30-google-gives-ai-agents-a-memory-of-past-work/opengraph-image"
author: "Shoubhik Banerjee"
draft: false
---

# Google Research introduces WikiSkill to improve AI agent memory and performance

Google Research has introduced WikiSkill, a framework that enables AI agents to retain procedural memory from past attempts without requiring model retraining. By separating an agent's core intelligence from its procedural memory, the system allows models to learn from failed tasks and improve performance through documented, actionable lessons.

## 🔍 Overview
WikiSkill functions like a playbook, allowing AI agents to analyze past performance data to refine their strategy. This approach avoids the need to adjust the model's underlying weights, effectively enabling agents to learn from experience similarly to how a sports team reviews game tape.

## 🧩 How it works
The system operates using three distinct architectural layers:

| Layer | Function |
| :--- | :--- |
| Raw Layer | Records full execution traces including API calls, searched websites, and success or failure data in JSON logs. |
| Wiki Layer | Uses a component called the Wiki Maintainer to distill raw logs into generalized, structured lessons. |
| Skill Layer | Uses a skill proposer to translate Wiki insights into targeted procedural instructions for future tasks. |

## ⚙️ Key details
Every proposed skill is tested in a sandbox environment before implementation. If the instruction leads to a performance decrease, the system automatically rolls back the change. Performance improvements were observed across major agent benchmarks:

*   **Gemini 3.5 Flash:** Average score across five benchmarks increased from 49.5% to 68.1%. On specific tasks, it rose from 33.0% to 72.6% on LiveMath and from 50.5% to 76.6% on SpreadSheet.
*   **Qwen-3.6-27B:** Average score across five benchmarks increased from 39.4% to 63.3%.

![figure](https://beehiiv-images-production.s3.amazonaws.com/uploads/asset/file/a576b1b0-3846-4fdf-81b4-d57e2ea33375/superpower-weekly-7249d301-67ef-4540-9557-1e34b4d2f501-r12.png?t=1788070655)

#Google #AI #MachineLearning #Gemini

---

*Source: [Google gives AI agents a memory of past work | Superpower Daily: The Signal](https://superpowerdaily.com/podcast/2026-08-30-google-gives-ai-agents-a-memory-of-past-work)*
*Source: [Google gives AI agents a memory of past work](https://superpowerdaily.com/posts/google-gives-ai-agents-a-memory-of-past-work)*
