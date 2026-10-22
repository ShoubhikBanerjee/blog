---
title: "Continuous Diffusion Language Models Struggle with Rare Words, GRAFT Restores Balance"
slug: "continuous-diffusion-language-models-struggle-with-rare-words-graft-restores-balance"
description: "Continuous diffusion language models (dLLMs) generate an entire sequence in parallel, converting embeddings to text only at the final step. Recent work shows that while models like ELF achieve..."
date: 2026-10-22T22:11:45+05:30
tags: [continuousdiffusion, languagemodels, GRAFT, rarewords]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Generative Models", "AI Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Continuous Diffusion Language Models Struggle with Rare Words, GRAFT Restores Balance

Continuous diffusion language models (dLLMs) generate an entire sequence in parallel, converting embeddings to text only at the final step. Recent work shows that while models like ELF achieve autoregressive‑level quality with far fewer sampling steps, they suffer a pronounced drop in rare‑word usage.

## 🔍 Overview
- Continuous diffusion models never draw a single word at intermediate steps; they output the whole sequence at once.
- ELF matches human frequency on common words but produces rare words at only **0.30×** the human rate.
- Scaling ELF from 105 M to 652 M parameters does **not** close the rare‑word gap.
- By contrast, a same‑size GPT‑2 can span from zero to above the human rate depending on its decoding rule.

## 🧩 How Continuous Diffusion Works
- Each generation step averages over all candidate tokens that are still possible.
- Because rare candidates are averaged together with far more common ones, the average tends toward the common word, effectively discarding the rare word.
- Autoregressive models avoid this by sampling a single candidate at each step rather than averaging.

## ⚙️ Problem: Collapse of the Lexical Long Tail
- Measured against held‑out human text, ELF’s rare‑word frequency is **0.30×** that of humans.
- No sampler setting for ELF can raise this rate, and the shortfall persists across model sizes.
- The underlying cause is the lack of a discrete‑word decision step in continuous diffusion.

## 💡 Solution: GRAFT (Training‑Free Rare‑Word Grafting)
- GRAFT intervenes while the model is still undecided, committing rare‑word choices that the averaging step would discard.
- After committing these choices, the model regenerates the sequence from scratch, preserving the rare‑word commitments.

## 📈 Results
| Model | Pre‑GRAFT Rare‑Word Share (× human) | Post‑GRAFT Rare‑Word Share (× human) | Relative Gain |
|-------|--------------------------------------|---------------------------------------|---------------|
| ELF (various scales) | 0.42–0.77 | 0.82–1.10 | 34%–109% |
| LangFlow (independent continuous dLLM) | 0.42–0.77* | 0.82–1.10* | 34%–109% |

*Exact pre‑GRAFT numbers for LangFlow are not specified; the same improvement range is reported.

- The word‑frequency profile moves **2.7×** closer to human on ELF‑B and **12×** closer on LangFlow.
- GRAFT restores rare‑word usage without additional training, applying to frozen models of any size.

*The story focuses on the technical findings; unrelated statements about arXivLabs values are omitted.*

#continuousdiffusion #languagemodels #GRAFT #rarewords

---

*Source: [GRAFT: Restoring the Missing Sampling Interface in Continuous Diffusion Language Models](https://arxiv.org/abs/2610.29136v1)*
