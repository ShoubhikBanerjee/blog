---
title: "Schema‑Free Enterprise Data Synthesis with Synthesis Through Simulation"
slug: "schemafree-enterprise-data-synthesis-with-synthesis-through-simulation"
description: "Tool‑calling agents have become central to enterprise AI, yet training and evaluating them at scale remains severely constrained by business and legal restrictions on enterprise systems, data, and..."
date: 2026-10-09T18:05:31+05:30
tags: [AIagents, DataSynthesis, LLM, EnterpriseAI]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Enterprise Computing", "Data Generation"]
author: "Shoubhik Banerjee"
draft: false
---

# Schema‑Free Enterprise Data Synthesis with Synthesis Through Simulation

Tool‑calling agents have become central to enterprise AI, yet training and evaluating them at scale remains severely constrained by business and legal restrictions on enterprise systems, data, and database schemas. Existing tabular data synthesis methods either struggle with structural validity and schema availability, or sacrifice distributional fidelity without per‑domain authoring.

## 🔍 Overview
Synthesis Through Simulation (STS) introduces a **schema‑free** data synthesis paradigm. An LLM agent generates data by executing operations against policy‑enforcing APIs within simulated enterprise environments.

## 🧩 How it works
- The simulated environment encodes the enterprise’s validity rules. By generating data **through the same environment**, STS guarantees structural validity **by construction**.
- Validity enforcement is **decoupled** from distribution modeling, allowing each aspect to be addressed independently.
- The **Generalist Populator (GP)**, a domain‑agnostic LLM agent, handles distributional fidelity and scalability.

## ⚙️ Key details
- **Central challenge**: tool‑calling agents are limited by data‑access and schema restrictions.
- **STS advantage**: no need for database schemas; validity is ensured by the simulation.
- **Generalist Populator performance**:
  - 0.88 average marginal fidelity
  - 100 % constraint satisfaction across all ten environments
  - Operates **without access to DB schemas**
- **Baseline comparisons**:
  - Statistical synthesizers are **inapplicable to seven** environments because they require seed data.
  - Schema‑privileged agents fail **82 % of trajectories** on the airline environment’s tightly coupled workflows due to brittle task composition.

| Method                     | Applicability                               | Performance Metric                              |
|----------------------------|---------------------------------------------|-------------------------------------------------|
| Generalist Populator (GP) | All 10 simulated environments (no schemas)  | 0.88 marginal fidelity, 100 % constraint sat. |
| Statistical synthesizers   | Inapplicable to 7 environments (needs seed) | –                                               |
| Schema‑privileged agents   | Airline environment (tight workflows)      | 82 % trajectory failure                        |

## 🚀 Availability
The full STS framework, all ten simulated environments, and the generated datasets have been **open‑sourced** at the provided URL.

## 💡 Why it matters
- Removes the bottleneck of schema access for training enterprise AI agents.
- Guarantees structurally valid synthetic data, enabling larger‑scale evaluation.
- Separates validity enforcement from distribution modeling, simplifying both research and deployment in regulated enterprise settings.


#AIagents #DataSynthesis #LLM #EnterpriseAI

---

*Source: [Synthesis Through Simulation: Generating Coherent Enterprise Data via Scalable Agent-System Interaction](https://arxiv.org/abs/2610.10549v1)*
*Source: [When Interfaces Speak: Data-Aware Generative UI Harness for Active Interaction](https://arxiv.org/abs/2610.11123v1)*
*Source: [TaReD: Tool-Aware Recursive Decomposition for Long-Horizon Tasks](https://arxiv.org/abs/2610.11268v1)*
