---
title: "SkillEval: Cross-model Skill-Level Assessment Framework for LLMs"
slug: "skilleval-cross-model-skill-level-assessment-framework-for-llms"
description: "We propose **SkillEval**, a new evaluation framework that performs cross‑model, skill‑level analysis."
date: 2026-10-22T22:11:45+05:30
tags: [SkillEval, LLMEvaluation, AIProfiling]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Evaluation Metrics"]
author: "Shoubhik Banerjee"
draft: false
---

# SkillEval: Cross-model Skill-Level Assessment Framework for LLMs

We propose **SkillEval**, a new evaluation framework that performs cross‑model, skill‑level analysis.

## 🔍 Overview
SkillEval is designed to move beyond average‑based scoring by producing reliable, calibrated, and concise profiles of language models.

## 🧩 How it works
- **Meta‑cognitive skill discovery** – the framework leverages the meta‑cognitive capabilities of LLMs to automatically uncover interpretable skills from questions.
- **Cognitive Diagnosis Models (CDMs)** – it applies CDMs from psychometrics to estimate per‑skill abilities for each LLM.

## 📊 Experiments
- Evaluated **3,811 LLMs** on **9,523 items**.
- Benchmarks covered: **MATH, BBH, GPQA, MuSR, IFEval** (five diverse domains).
- Compared with the traditional average‑based evaluation paradigm, SkillEval’s profiles more accurately predict model behavior on unseen items.

## 🚀 Benefits & Applications
- **More calibrated and informative** model profiles while remaining concise.
- **Downstream task 1 – LLM routing**: dynamically routes each query to a capable but efficient model, reducing inference cost by **over 60%** and improving performance.
- **Downstream task 2 – Computerized Adaptive Testing (CAT)**: an unseen model can be efficiently evaluated using a trained CDM.
- **Insight generation**: skill profiles reveal how benchmarks share skills and illustrate differences between instruction‑tuned models and their base counterparts.


#SkillEval #LLMEvaluation #AIProfiling

---

*Source: [SkillEval: Learning Interpretable Ability Profiles of LLMs via Cognitive Diagnosis Models](https://arxiv.org/abs/2610.28767v1)*
*Source: [Our Own Jev: Typed Decisions in One Forward Pass, from an In-House Judge to Open LoRA Models](https://arxiv.org/abs/2610.29052v1)*
