---
title: "Comparison of Two-Agent and One-Call AI Screening for Résumés"
slug: "comparison-of-two-agent-and-one-call-ai-screening-for-resumes"
description: "Researchers have studied a two-agent AI alternative for résumé screening where employer-side and candidate-side agents exchange evidence and update judgments to decide which applications advance."
date: 2026-09-18T12:08:53+05:30
tags: [AIagents, LLM, recruitment, GPT55, ClaudeOpus]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Human Resources Technology"]
author: "Shoubhik Banerjee"
draft: false
---

# Comparison of Two-Agent and One-Call AI Screening for Résumés

Researchers have studied a two-agent AI alternative for résumé screening where employer-side and candidate-side agents exchange evidence and update judgments to decide which applications advance.

## 🧩 How it works
- The system utilizes two separate agents representing the employer and the candidate.
- These agents exchange evidence and update their judgments before making a final decision on who advances.

## ⚙️ Key details
- The procedures were compared using 600 constructed résumé-job pairs.
- The study utilized two models:
    - GPT-5.5
    - Claude Opus 4.7

## 📊 Results
Two-agent screening resulted in higher advancement rates compared to one-call procedures:

| Model | One-Call Rate | Two-Agent Rate |
| :--- | :--- | :--- |
| GPT-5.5 | 33.3% | 39.3% |
| Opus 4.7 | 34.0% | 35.5% |

Additional findings include:
- In a borderline pool of 191 pairs across three runs, pass-instance rates rose from 4.5% to 26.2% for GPT-5.5 and from 6.5% to 16.1% for Opus 4.7.
- Two-agent screening changes decisions in both directions, rejecting some applications that one-call procedures would advance.
- No one-call threshold consistently recovers applications selected by two-agent screening.
- Among discovery-selected cases in fresh runs, two-agent-only selections recur less often than shared selections (clearly under GPT-5.5 and less certainly under Opus 4.7), whereas a separate one-call follow-up shows no comparable decline.

#AIagents #LLM #recruitment #GPT5.5 #ClaudeOpus

---

*Source: [When Hiring Becomes Agent-Mediated: Evaluating Access and Recurrence in Two-Agent Résumé Screening](https://arxiv.org/abs/2609.19530v1)*
