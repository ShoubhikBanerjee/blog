---
title: "Study Finds Limited Authorship Impersonation by Leading LLMs, Highlights Copying Risks"
slug: "study-finds-limited-authorship-impersonation-by-leading-llms-highlights-copying-risks"
description: "A new arXiv study evaluated how well six widely used large language models can impersonate a target author when generating short product‑review texts. The results show that genuine stylistic mimicry..."
date: 2026-11-05T18:02:42+05:30
tags: [LLM, AuthorshipImpersonation, ForensicAI]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Ethics", "Forensic Analysis"]
author: "Shoubhik Banerjee"
draft: false
---

# Study Finds Limited Authorship Impersonation by Leading LLMs, Highlights Copying Risks

A new arXiv study evaluated how well six widely used large language models can impersonate a target author when generating short product‑review texts. The results show that genuine stylistic mimicry remains difficult, and the most successful model relied heavily on direct textual reuse.

## 🔍 Overview
- Investigated authorship impersonation capacity of six LLMs: Gemini 3 Pro, Claude Opus, GPT 5.2, GPT 5.2 Pro, DeepSeek 3.2, and Grok 4.1 Fast.
- Focused on short product‑review excerpts selected for high within‑author style consistency.
- Authorship mimicry assessed with a cosine‑distance metric to the training data and visual analysis of embedding distributions.

## 🧩 Methodology
- **Prompt types**: 
  - Simple prompt with minimal instruction.
  - Complex prompt that supplied explicit stylometric guidance for mimicry.
- **Evaluation metrics**:
  - Cosine distance to training‑author embeddings.
  - Visual inspection of embedding distribution plots.
- **Overlap analysis** examined sentence‑ and phrase‑level reuse from the training texts.

## 📊 Models Evaluated
| Model | Observed Mimicry Performance |
|-------|------------------------------|
| Gemini 3 Pro | Strongest apparent mimicry (but extensive copying) |
| Claude Opus | Challenging to impersonate |
| GPT 5.2 | Challenging to impersonate |
| GPT 5.2 Pro | Challenging to impersonate |
| DeepSeek 3.2 | Challenging to impersonate |
| Grok 4.1 Fast | Challenging to impersonate |

## 📈 Findings
- Authorship impersonation was **challenging for most LLMs**.
- **Gemini 3 Pro** achieved the strongest apparent mimicry, yet overlap analysis showed it **copied and reused sentences and phrases** far beyond typical human levels.
- Factor analyses identified **training‑set consistency** as the most robust predictor of mimicry success across models; **author distinctiveness** did not generalise as a reliable predictor.
- Global embedding visualisations revealed a macro‑level pattern: generated texts for most models occupied regions **separate from the human training clusters**, indicating limited convergence toward the target author's style and the presence of model‑specific lexical preferences.

## 🛡️ Implications
- Highlights the need to **distinguish genuine stylistic imitation from direct textual reuse** when evaluating LLM output.
- Provides important context for **forensic analysis of textual evidence** involving potential LLM‑enabled impersonation.
- Suggests that relying on apparent style similarity alone may overlook substantial copying.

*Study author: Shunichi Ishihara (arXiv v1, 4 Nov 2026).*

#LLM #AuthorshipImpersonation #ForensicAI

---

*Source: [How Well Can Large Language Models Impersonate Individual Authors? A Comparative Evaluation](https://arxiv.org/abs/2611.05771v1)*
