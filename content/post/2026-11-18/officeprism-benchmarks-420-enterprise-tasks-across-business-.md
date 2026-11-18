---
title: "OfficePrism Benchmarks 420 Enterprise Tasks Across Business Functions"
slug: "officeprism-benchmarks-420-enterprise-tasks-across-business-functions"
description: "OfficePrism has been introduced as an evaluation framework designed to assess AI performance in enterprise environments. The system addresses the difficulty of localizing failures when broad..."
date: 2026-11-18T18:09:03+05:30
tags: [OfficePrism, AIBenchmarking, EnterpriseAI, LLMEvaluation, SyntheticData]
categories: ["AI", "AI Evaluation", "Machine Learning", "Enterprise Software", "Benchmarking"]
author: "Shoubhik Banerjee"
draft: false
---

# OfficePrism Benchmarks 420 Enterprise Tasks Across Business Functions

OfficePrism has been introduced as an evaluation framework designed to assess AI performance in enterprise environments. The system addresses the difficulty of localizing failures when broad workplace scores mix competence within a single business function with the costs of coordinating across multiple functions and systems. To resolve this, OfficePrism evaluates prerequisites through a structured set of tasks that isolate specific domains while maintaining shared organizational context.

## 🔍 Overview

The framework is built to test models on realistic enterprise workflows. It moves beyond generic benchmarks by using a shared synthetic organization that defines the context for each test case. This approach allows for a clearer distinction between functional competence and coordination overhead.

## 🧩 How it works

The evaluation pipeline constructs test scenarios using grounded records, business rules, and tool schemas. This process jointly creates:
*   A Chinese-language ticket
*   A hidden executable reference witness
*   An expected response

Each of the 420 single-domain enterprise tasks is executed in a fresh environment. This environment combines the shared synthetic organization with one function-specific domain and typed state access. The tasks are filtered automatically and curated by humans before inclusion in the final set. The evaluation spans seven business functions and uses three benchmark-defined task-structure levels: L1, L2, and L3.

## ⚙️ Key details

The same task set is evaluated using two different configuration packages: full-schema and search-and-dispatch. The results across 124 model-harness-package configurations show significant variance in performance:

| Metric | Result |
| :--- | :--- |
| Per-case joint pass rate range | 22.6% to 76.4% |
| Median pass rate | 67.9% |
| L1 performance | Highest in all 124 configurations |
| L2 vs. L3 performance | L2 exceeds L3 in 122 out of 124 configurations |

When comparing configurations that share the same harness and model labels across both packages, the search-and-dispatch package scored higher in 30 instances, tied in one, and scored lower in 19 instances compared to the full-schema package.

#OfficePrism #AIBenchmarking #EnterpriseAI #LLMEvaluation #SyntheticData

---

*Source: [OfficePrism: Benchmarking Agents on Single-Domain Operations Across Enterprise Business Functions](https://arxiv.org/abs/2611.22262v1)*
