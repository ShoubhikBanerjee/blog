---
title: "New Benchmark Evaluates LLM Agents in Enterprise Environments"
slug: "new-benchmark-evaluates-llm-agents-in-enterprise-environments"
description: "LLM agents for enterprise systems of record cannot be evaluated on customer production data, and no existing substitute provides ground truth. To address this, researchers present the Era by Eon..."
date: 2026-09-11T12:15:38+05:30
tags: [A, I, A, g, e, n, t, s, B, e, n, c, h, m, a, r, k, E, n, t, e, r, p, r, i, s, e, D, a, t, a, b, a, s, e, L, L, M]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "A", "I", "A", "g", "e", "n", "t", "s", ",", "D", "a", "t", "a", "b", "a", "s", "e", "M", "a", "n", "a", "g", "e", "m", "e", "n", "t", ",", "S", "o", "f", "t", "w", "a", "r", "e", "E", "n", "g", "i", "n", "e", "e", "r", "i", "n", "g"]
author: "Shoubhik Banerjee"
draft: false
---

# New Benchmark Evaluates LLM Agents in Enterprise Environments

LLM agents for enterprise systems of record cannot be evaluated on customer production data, and no existing substitute provides ground truth. To address this, researchers present the Era by Eon Benchmark for evaluating LLM agents that use enterprise tools.

## 🔍 Overview

The benchmark is built around a complete fictional company. It includes product simulators, company-specific internal databases, benchmark questions, and computed answer keys. Industry, company size, business model, application portfolio, and a seed define each company. One seeded entity graph supplies shared company data to simulators of Salesforce, Zendesk, Slack, Gong, and other products.

### Company Definition Attributes

| Attribute | Role in Benchmark |
| :--- | :--- |
| Industry | Defines the sector |
| Company Size | Defines the scale |
| Business Model | Defines revenue generation |
| Application Portfolio | Defines the software stack |
| Seed | Defines the starting state |

## ⚙️ How it works

A questionconditioned generator creates the schemas and records for internal databases. It takes shared entities, keys, and values from the same graph before generating database-specific facts. Both mechanisms therefore describe one consistent enterprise estate. Every expected answer is computed from the final records, so grading is exact. Design and answer-key checks validate the internal databases. A realism scorecard and adversarial detector validate the entity graph.

## 📊 Results

Across 23 generated companies, the mean realism score rose from 61.8 to 97.0, with zero records flagged as synthetic. In the reported simulator-track comparison, nine models answered the same 33 questions three times each. Accuracy estimates ranged from 42.4% to 76.8%, and three of 36 pairwise differences remained supported after correction.

## 💾 Database Normalization

We introduce a Database Normalization Benchmark (DNBENCH), comprising 3,275 samples for evaluating LLM-driven database normalization from 1NF to BCNF. DNBENCH uses a three-axis protocol to measure semantic equivalence, structural accuracy, and logical validity. Across Single, Complex, and Real World levels, DNBENCH uncovers recurring failures in dependency inference, schema decomposition, and inter-table constraint reconstruction.

## 🤖 Multi-Agent Reasoning

We further propose Multi-Agent Reasoning for Schemas (MARS), which separates evidence extraction, violation diagnosis, and decomposition planning from schema generation and verification. MARS improves the DNB-SCORE by 82.0% over the single-prompt baseline.

#A #I # #A #g #e #n #t #s #, # #B #e #n #c #h #m #a #r #k #, # #E #n #t #e #r #p #r #i #s #e #, # #D #a #t #a #b #a #s #e #, # #L #L #M

---

*Source: [The Era by Eon Benchmark: A Generated Enterprise Estate with Exact Ground Truth for Benchmarking LLM Agents](https://arxiv.org/abs/2609.09853v1)*
*Source: [Can LLMs Normalize Databases? A Benchmark and Multi-Agent Framework for Schema Normalization](https://arxiv.org/abs/2609.11141v1)*
