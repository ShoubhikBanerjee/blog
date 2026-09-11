---
title: "State-Path Tool Menus Improve Online Agent Success on ToolBench"
slug: "state-path-tool-menus-improve-online-agent-success-on-toolbench"
description: "Researchers have introduced the State-Path Tool Menu, a framework designed to improve how online agents interact with large tool libraries by providing a short, ordered subset of tools prior to..."
date: 2026-09-11T12:15:38+05:30
tags: [AIagents, ToolBench, LargeLanguageModels, SoftwareEngineering]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# State-Path Tool Menus Improve Online Agent Success on ToolBench

Researchers have introduced the State-Path Tool Menu, a framework designed to improve how online agents interact with large tool libraries by providing a short, ordered subset of tools prior to execution.

## 🔍 Overview
Practical agents often face libraries containing thousands of interfaces. Current constructors typically rank tools by request relevance, which may surface a final action while omitting or delaying the necessary producer tools required to create its inputs. The State-Path Tool Menu addresses this by treating the menu as an execution prior over routes from the observable request state to the desired outcome.

## 🧩 How it works
The framework utilizes three primary components to organize the tool menu:

* **Encoder**: Represents which tools can run from the current state, how outputs satisfy later inputs, and which orders recur in training paths.
* **Retriever**: Covers an executable entry, the final action, and the missing-input producers.
* **Reranker**: Ensures producers are placed before consumers in the menu.

## ⚙️ Key details
Testing on ToolBench demonstrated the following results:

* **Success Rate**: Online success increased from 0.737 to 0.898.
* **Efficiency**: The State-Path menu covered more complete chains with 32 tools than the official list covered with 128.
* **Compatibility**: Success gains persisted across executor families with different model capacities.
* **Performance**: The system outperformed baselines involving routing, generation, reranking, and retrieval without requiring changes to the agent.

#AIagents #ToolBench #LargeLanguageModels #SoftwareEngineering

---

*Source: [The Menu Is an Execution Prior: State-Path Tool Menus for Online Agents](https://arxiv.org/abs/2609.09395v1)*
*Source: [RobustSGPO: Search-Space Control for Agent Harness Evolution](https://arxiv.org/abs/2609.09646v1)*
*Source: [Auto-RecSys: Harnessing Autonomous Research Agents for Industry-Scale Recommender System](https://arxiv.org/abs/2609.10922v1)*
*Source: [Overview of the NLPCC 2026 Shared Task 11: Agent-Based Experiment Reproduction from Scientific Papers](https://arxiv.org/abs/2609.11117v1)*
