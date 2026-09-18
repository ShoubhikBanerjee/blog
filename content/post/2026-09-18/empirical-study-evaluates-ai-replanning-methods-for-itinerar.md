---
title: "Empirical Study Evaluates AI Replanning Methods for Itinerary Disruptions"
slug: "empirical-study-evaluates-ai-replanning-methods-for-itinerary-disruptions"
description: "A systematic empirical study has been conducted to compare three AI approaches for handling itinerary disruptions: LLM-Z3 full replanning, IPyHOPPER hierarchical repair, and the iTIMO local-revision..."
date: 2026-09-18T12:08:53+05:30
tags: [AI, Planning, LLM, Benchmarking]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Empirical Study Evaluates AI Replanning Methods for Itinerary Disruptions

A systematic empirical study has been conducted to compare three AI approaches for handling itinerary disruptions: LLM-Z3 full replanning, IPyHOPPER hierarchical repair, and the iTIMO local-revision adapter. The research utilized two benchmark sets derived from TREK, covering 500 single-disruption cases and 200 feasible simultaneous compound-disruption cases.

## ⚙️ Key details

The study evaluated performance based on effectiveness, plan stability, and computational cost. The following table summarizes the operational differences noted during the evaluation:

| Method | Approach | Key Characteristic |
| :--- | :--- | :--- |
| LLM-Z3 | Full replanning | Used compact one-call inference |
| IPyHOPPER | Hierarchical repair | Used no LLM inference |
| iTIMO | Local-revision adapter | Consumed substantially more tokens |

## 💡 Why it matters

Performance metrics indicated distinct trade-offs between the tested methods:

* LLM-Z3 with Gemini achieved the highest observed success rate for compound disruptions.
* IPyHOPPER nearly matched LLM-Z3 in single-disruption overall success.
* Hierarchical and local repair methods (IPyHOPPER and iTIMO) were more efficient at preserving accepted itineraries, requiring fewer edits than full replanning.

#AI #Planning #LLM #Benchmarking

---

*Source: [Replan, Repair, or Edit? A Unified Empirical Evaluation of Travel Agents for Itinerary Revision under Resource Disruptions](https://arxiv.org/abs/2609.19654v1)*
