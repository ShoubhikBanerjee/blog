---
title: "Banks Test LLM Harnesses for Compliance with EU‑style Rules"
slug: "banks-test-llm-harnesses-for-compliance-with-eustyle-rules"
description: "Banks are validating language models not in isolation but inside *harnesses*—software wrappers that choose what the model sees, which external tools it may call, and who reviews its actions. An..."
date: 2026-11-05T18:02:42+05:30
tags: [AICompliance, BankingAI, LLMTesting]
categories: ["AI", "Machine Learning", "AI Governance", "Financial Services", "Risk Management"]
author: "Shoubhik Banerjee"
draft: false
---

# Banks Test LLM Harnesses for Compliance with EU‑style Rules

Banks are validating language models not in isolation but inside *harnesses*—software wrappers that choose what the model sees, which external tools it may call, and who reviews its actions. An internal study examined whether these harnesses affect compliance with banking conduct rules when the underlying model is held constant.

## 🔍 Overview
- Four open‑weight large language models (LLMs) were each paired with five distinct harness designs.
- The models tackled 156 pre‑registered customer cases in a simulated retail bank.
- The bank’s rule set comprised 11 families that paraphrase EU consumer‑credit, payments, investor‑protection, data‑protection, and anti‑money‑laundering provisions.
- In total, 3 120 two‑turn episodes (156 cases × 5 harnesses × 4 models) were executed and scored deterministically from the tool trace, separating *violations* from *over‑refusals*.

## 🧩 How the Harnesses Work
| Harness | Description |
|---|---|
| Structured‑decision pipeline | A single, rule‑driven decision flow that produces a structured output. |
| ReAct‑style tool loop | The model interleaves reasoning and tool use in a loop, following the ReAct paradigm. |
| Search‑only policy loop | The policy is reachable only through a search operation inside the loop. |
| Long benign‑memory loop | The loop includes an extended, harmless customer memory to provide context. |
| Same‑model compliance reviewer | The model itself is invoked a second time to review its own actions for compliance. |

## ⚙️ Key Findings
- **Overall impact**: Across all models the harness shifted the correct‑case rate only modestly, ranging from **87.3 %** to **92.1 %**.
- **Model‑specific effect**: For one model the spread between its best and worst harness was **11.5 percentage points**, enough to move it from first to last place among the four models. For another model, the harness made no detectable difference.
- **Same‑model reviewer**: Adding a reviewer reduced violations from **9.6 %** to **6.4 %** without increasing over‑refusals, contrary to the pre‑registered expectation.
- **Date‑arithmetic rules**: Every harness failed on rules that required date calculations.
- **Blind check insight**: An exploratory analysis with two LLM judges and a blind human reviewer found that **26 %** of flagged violations were accompanied by a customer message denying the action, which a transcript‑only review would have marked as a correct refusal.

## 💡 Why It Matters
- **Risk‑management unit**: The study suggests that validation should focus on the *model‑harness pair* rather than the model alone.
- **Testing methodology**: Conduct testing should read the full action log (the tool trace) instead of relying solely on the conversational transcript.
- **Compliance tooling**: Harness design can materially affect a model’s adherence to regulatory rules, indicating a lever for banks to improve AI‑driven customer service without changing the underlying model.

#AICompliance #BankingAI #LLMTesting

---

*Source: [The Harness Is the Model: Agent Scaffolding Changes a Fixed LLM's Compliance with Banking Conduct Rules, Unevenly Across Models](https://arxiv.org/abs/2611.06116v1)*
