---
title: "New Benchmark DSB-IFEval Evaluates Implicit Instruction Following in Full-Duplex Voice Agents"
description: "Full-duplex voice assistants must constantly decide when to listen, back‑channel, interrupt, handle overlaps, take the floor, and yield. Existing benchmarks rely on explicit turn‑management..."
date: 2026-09-04T12:10:15+05:30
tags: [voiceagents, benchmark, fullduplex, turntaking, LLM]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# New Benchmark DSB-IFEval Evaluates Implicit Instruction Following in Full-Duplex Voice Agents

Full-duplex voice assistants must constantly decide when to listen, back‑channel, interrupt, handle overlaps, take the floor, and yield. Existing benchmarks rely on explicit turn‑management instructions, yet deployed agents are often driven by roles or personas that require the system to infer the appropriate behavior.

## 🔍 Overview
- **DSB‑IFEval** (DuplexSpeechBench‑IFEval) is introduced to evaluate implicit instruction‑following in real‑time spoken interaction.
- The benchmark contains **1,038 test cases** covering **eight diverse assistant roles**.
- It tests five conditioning protocols:
  1. Default behavior
  2. Explicit behavioral instructions
  3. Persona‑implied behavior
  4. Combined persona‑rule conditioning
  5. Instruction conflict
- Two evaluation metrics are defined:
  - **Instruction Adherence Score (IAS)** – deterministic measure of real‑time floor management.
  - **Persona Adherence Score (PAS)** – LLM‑judged consistency of content with the assigned persona.

## 🧩 How It Works
- The benchmark measures how well a system can infer behavior from a role, execute it at the correct conversational moment, and resolve competing instructions.
- A **rule‑based event‑guided data transformation** serializes human‑human spoken dialogues into finite‑state‑machine (FSM) tapes by classifying turn‑taking events and applying deterministic mapping rules. This provides scalable supervision without LLM‑generated annotations.
- The **Source‑Aware Calibrated (SAC) Loss** jointly calibrates the long‑tailed distribution of state‑transition tokens and channels each data source toward the capability it best supervises.
- Experiments demonstrate substantial improvements in turn‑taking proficiency while preserving the foundational LLM’s semantic capability.

## ⚙️ Key Details
- **Architecture comparison** (six real‑time speech systems):
  - Full‑duplex models **F‑Actor** and **PersonaPlex** show a drop in adherence when only persona information is provided, indicating sensitivity to explicit instructions.
  - Models **GPT‑Realtime**, **MiniCPM‑o**, and **Fun‑Audio‑Chat** maintain strong persona‑consistent content but show limited adaptation in floor‑management behavior across instruction types.
  - All systems struggle to override conflicting directives when a safety conflict is present, even if they follow persona‑specific instructions.
- **Neural Finite State Machine (NFSM)** offers a pragmatic path to full‑duplex dialogue by serializing turn‑taking control and response generation onto a single causal tape under the standard next‑token prediction objective, preserving semantic prowess at low fine‑tuning cost. Its limitation: reliance on synthetic text data, which cannot fully capture fine‑grained acoustic dynamics of human speech.

## 📊 Results Summary
| Model          | Adherence drop under persona‑only conditioning |
|----------------|-----------------------------------------------|
| F‑Actor        | 9.7 %                                         |
| PersonaPlex    | 4.5 %                                         |

- The table reflects the architecture‑dependent trade‑offs observed in DSB‑IFEval.
- Despite strong persona adherence, GPT‑Realtime, MiniCPM‑o, and Fun‑Audio‑Chat do not adjust floor‑management behavior across explicit vs. persona‑only instructions.

## 🚀 Outlook
- The decoupled data approach—learning turn‑taking from real human‑human speech while shaping semantic behavior through configurable human‑agent text dialogues—offers a scalable route to more natural full‑duplex voice agents.
- Public release of the code and model (available at the provided URL) enables the community to build on these findings and further narrow the gap between acoustic realism and LLM semantic strength.


#voiceagents #benchmark #fullduplex #turntaking #LLM

---

*Source: [DuplexSpeechBench-IFEval: Evaluating Implicit Instruction Following in Full-Duplex Voice Agents](https://arxiv.org/abs/2609.03423v1)*
*Source: [Decoupling Turn-Taking from Semantics: A Decoupled Data Approach for Finite-State-Machine-Based Full-Duplex Dialogue](https://arxiv.org/abs/2609.03321v1)*
