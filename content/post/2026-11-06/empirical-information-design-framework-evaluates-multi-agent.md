---
title: "Empirical Information Design Framework Evaluates Multi-Agent LLM Disclosure Policies"
slug: "empirical-information-design-framework-evaluates-multi-agent-llm-disclosure-policies"
description: "Researchers have introduced empirical information design, an experimental framework created to systematically compare disclosure policies across economic markets populated by LLM agents."
date: 2026-11-06T18:03:32+05:30
tags: [LLMs, MultiAgentSystems, InformationDesign, ArtificialIntelligence, Economics]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# Empirical Information Design Framework Evaluates Multi-Agent LLM Disclosure Policies

Researchers have introduced empirical information design, an experimental framework created to systematically compare disclosure policies across economic markets populated by LLM agents.

## 🔍 Overview

The performance of multi-agent LLM systems depends on the capabilities of underlying models as well as information-sharing policies governing what agents observe and at what level of detail. Empirical information design holds interaction rules and models fixed to test whether providing agents with more detailed information improves collective outcomes or paradoxically degrades efficiency.

The framework evaluated ten frontier LLMs across three market environments—multi-resource trade, bilateral bargaining, and double auctions—using ground-truth utilities to decouple identified opportunities from realized outcomes. Results indicate that finer information disclosure yields highly model-dependent outcomes.

## ⚙️ Key details

The impact of disclosing exact or full information varied significantly by model and market format:

| Model | Market Setting | Effect of Finer/Full Information Disclosure |
| --- | --- | --- |
| GPT-6 Sol | Multi-resource trade | Realized gains reduced from 98% to 91% of maximum |
| Claude Sonnet 5 | Multi-resource trade | Realized gains increased from 72% to 86% of maximum |
| Grok 4.7 | Bilateral bargaining | Produced less balanced agreements |
| Claude Opus 5.5 | Bilateral bargaining | Divided gains symmetrically |
| Gemini 3.1 Pro | Double auctions | Price demands inflated, triggering market breakdown and dropping welfare from 97% to 78% |
| Claude Opus 5.5 | Double auctions | Price demands inflated, triggering market breakdown and dropping welfare from 94% to 64% |
| Grok 4.7 | Double auctions | Price demands inflated, triggering market breakdown and dropping welfare from 97% to 62% |

## 💡 Why it matters

These findings suggest that model selection and information design must be co-optimized for multi-agent applications. Large language models vary in how their strategic responses to information influence overall system objectives, demonstrating that increased transparency does not automatically yield better economic efficiency.

#LLMs #MultiAgentSystems #InformationDesign #ArtificialIntelligence #Economics

---

*Source: [Who Should Know What? Empirical Information Design for Multi-Agent LLM Economies](https://arxiv.org/abs/2611.07667v1)*
