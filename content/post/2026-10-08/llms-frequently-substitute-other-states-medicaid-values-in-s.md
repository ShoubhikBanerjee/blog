---
title: "LLMs Frequently Substitute Other States’ Medicaid Values in State‑Specific Queries"
slug: "llms-frequently-substitute-other-states-medicaid-values-in-statespecific-queries"
description: "A new study examined how large language models (LLMs) answer state‑specific Medicaid income‑eligibility questions and found that the models often return a value that is correct for a different state..."
date: 2026-10-08T18:03:50+05:30
tags: [LLM, Medicaid, AIEvaluation, PolicyAI, CrossState]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Evaluation"]
author: "Shoubhik Banerjee"
draft: false
---

# LLMs Frequently Substitute Other States’ Medicaid Values in State‑Specific Queries

A new study examined how large language models (LLMs) answer state‑specific Medicaid income‑eligibility questions and found that the models often return a value that is correct for a different state rather than the asked state.

## 🔍 Overview
- When an LLM answers a state‑specific policy question wrongly, it may be hallucinating, or it may be returning a real value that holds in another state.

## 🧩 How it works
- The question wording is fixed and only the jurisdiction varies across the 50 U.S. states and the District of Columbia (51 jurisdictions).
- Three exactly defined Medicaid income‑eligibility quantities are tested.
- Gold values come from an official data book and agree with an independent source in 101 of 102 checked cells.

## ⚙️ Key details
- Under a pre‑registered protocol, Claude Sonnet 5.5 reproducibly gives another state’s current value, identical across two independent repeats, for 10 of 153 items.
- Under the same protocol, GPT‑5.6 reproducibly gives another state’s current value, identical across two independent repeats, for 25 of 153 items.
- Attribution is fragile.
- Crediting any wrong answer that equals another state’s value yields 3‑5× more reproducible substitutions than checking every number in the asked state’s own records, because many apparent cross‑state answers are the asked state’s own values under another convention or from an earlier year.
- Claims about cross‑jurisdiction error need a complete same‑state reference set.

| Model | Items showing another state’s value (out of 153) |
|-------|-----------------------------------------------|
| Claude Sonnet 5.5 | 10 |
| GPT‑5.6 | 25 |

## 🚀 Availability
- The protocol, gold table, and all model outputs will be released.

## 💡 Why it matters
- To evaluate cross‑jurisdiction error reliably, a complete same‑state reference set is required.

#LLM #Medicaid #AIEvaluation #PolicyAI #CrossState

---

*Source: [Right Number, Wrong State? Measuring Cross-Jurisdiction Substitution in LLM Recall of State Policy](https://arxiv.org/abs/2610.09458v1)*
