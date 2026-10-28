---
title: "Lightweight Multi‑Agent System Automates Construction Safety Bulletins"
slug: "lightweight-multiagent-system-automates-construction-safety-bulletins"
description: "Construction safety management still struggles to produce daily safety bulletins (DSBs), structured daily communications that identify site‑specific hazards, convey safety protocols, and set..."
date: 2026-10-28T22:03:50+05:30
tags: [ConstructionAI, SafetyAutomation, MultiAgentSystems, LLM, RAG]
categories: ["AI", "Construction Technology", "Artificial Intelligence", "Natural Language Processing", "AI Agents"]
author: "Shoubhik Banerjee"
draft: false
---

# Lightweight Multi‑Agent System Automates Construction Safety Bulletins

Construction safety management still struggles to produce daily safety bulletins (DSBs), structured daily communications that identify site‑specific hazards, convey safety protocols, and set preventive measures for workers. Manual DSB creation takes 2–3 hours daily and yields inconsistent quality, with 25 % of crews never conducting pre‑task planning (Olson et al., 2016), diverting safety personnel from field supervision.

## 🔍 Overview
- Difficulty producing daily safety bulletins on construction sites.
- Manual creation requires 2–3 hours per day and is inconsistent.
- 25 % of crews skip pre‑task planning, pulling safety staff away from supervision.

## 🛠️ How It Works
- LM‑DSB integrates retrieval‑augmented generation (RAG) with a locally deployable Large Language Model (LLM) that runs on consumer‑grade personal computers.
- A hierarchical architecture coordinates three specialized agents:

| Agent | Role |
|-------|------|
| Planner | Generates site‑specific hazard lists and safety protocols |
| Researcher | Retrieves relevant information from a knowledge base of 37 HSE documents |
| Writer | Synthesizes retrieved content into a coherent daily safety bulletin |

- The system is fine‑tuned on construction safety documentation and grounded in 37 health, safety, and environment (HSE) documents.

## 📊 Validation
- **Phase 1 – Comparative Evaluation** (multi‑agent RAG using Llama 3‑8B) outperformed all alternative configurations.
  - TF‑IDF: 0.70
  - BLEU: 0.39
  - ROUGE‑1: 0.66
  - Length ratio: 1.01 (vs. 0.39 for single‑agent RAG)
- **Phase 2 – Expert Evaluation** (N = 40 safety experts) confirmed practical acceptability with mean scores of 3.50–4.20 on a 5‑point scale.
  - Regulatory compliance: 4.20
  - Factual accuracy: 4.10

## ✅ Key Results
- Architectural design enables lightweight models to handle safety‑critical documentation on consumer‑grade hardware.
- Demonstrates a step toward technology democratization in construction safety management.

## ⚠️ Limitations
- Scope of the knowledge base is limited.
- Language constraints restrict applicability.
- No validation in real‑world field deployments.

## 🔮 Future Work
- Incorporate multimodal integration (e.g., images, sensor data).
- Study workflow adoption and field deployment strategies.


#ConstructionAI #SafetyAutomation #MultiAgentSystems #LLM #RAG

---

*Source: [LM-DSB: A Lightweight Multi-agent System for Automated Daily Safety Bulletin Generation in Construction](https://arxiv.org/abs/2610.36433v1)*
