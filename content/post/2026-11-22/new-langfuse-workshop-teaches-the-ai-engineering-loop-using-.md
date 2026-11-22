---
title: "New Langfuse Workshop Teaches the AI Engineering Loop Using a TypeScript Agent"
slug: "new-langfuse-workshop-teaches-the-ai-engineering-loop-using-a-typescript-agent"
description: "An end-to-end, step-by-step Langfuse workshop has been introduced to teach the full AI engineering loop using a TypeScript sample application. Based on hands-on concepts from the Langfuse Academy,..."
date: 2026-11-22T12:09:58+05:30
tags: [Langfuse, TypeScript, LLMOps, AIagents]
categories: ["AI", "Developer Tools", "AI Engineering", "Software Development"]
image: "https://avatars.githubusercontent.com/u/134601687?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Langfuse Workshop Teaches the AI Engineering Loop Using a TypeScript Agent

An end-to-end, step-by-step Langfuse workshop has been introduced to teach the full AI engineering loop using a TypeScript sample application. Based on hands-on concepts from the Langfuse Academy, this workshop focuses on tracing, prompt management, monitoring, datasets, experiments, and evaluation.

## 🧩 How it works
The workshop is built around a small sample web chat application called the Dad IT Support Agent. 
* **The Agent:** Named "Specs", the agent answers with step-by-step instructions when a dad opens the chat to get iPhone help.
* **Under the Hood:** It runs on a standard OpenAI tool-calling loop with two local tools.
* **Implementation:** The `main` branch contains the complete reference application and workshop docs, which can be used to inspect the finished implementation or compare work. Exercises themselves start from checkpoint tags.

## ⚙️ Lesson breakdown
The self-guided learner lessons are located in `docs/learner/` and guide participants through the following stages:
* **Logging Traces:** Log the first trace from a real LLM application to understand the output.
* **Prompt Management:** Move a prompt into Langfuse to ensure changes are versioned and linked to traces.
* **Production Monitoring:** Analyze production traces for cost, latency, error analysis, and signals.
* **Evaluation and Experiments:** Build an evaluation dataset, run experiments, and evaluate changes with evidence.
* **Reference Implementation:** Inspect a complete TypeScript reference implementation to copy patterns for other projects.

## 🚀 Ways to run the workshop
The workshop can be completed independently or delivered as a guided session:
* **Self-Guided Mode:** The learner lessons are complete enough to run the workshop without an instructor.
* **Instructor-Facilitated:** Facilitators can use notes in `docs/instructor/` for live workshops, walkthroughs, or team sessions. These notes include teaching points, demo rhythm, setup reminders, and common pitfalls.
* **Preparation Materials:** Pre-made slides and guides are available in `docs/preparation_and_materials/`.

To get the latest features described in the workshop, participants should use Langfuse Cloud and ensure that AI Features are enabled under Organization Settings → General → AI Features.

#Langfuse #TypeScript #LLMOps #AIagents

---

*Source: [langfuse/langfuse-workshop](https://github.com/langfuse/langfuse-workshop)*
