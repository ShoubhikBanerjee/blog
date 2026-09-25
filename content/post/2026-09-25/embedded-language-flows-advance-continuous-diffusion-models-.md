---
title: "Embedded Language Flows Advance Continuous Diffusion Models for Reasoning and Code"
slug: "embedded-language-flows-advance-continuous-diffusion-models-for-reasoning-and-code"
description: "A new update introduces ELF-REG, an extension of Embedded Language Flows (ELF) that improves continuous diffusion language models on reasoning and code generation tasks."
date: 2026-09-25T18:03:21+05:30
tags: [diffusionLLM, ELF, AIresearch]
categories: ["AI", "Machine Learning", "Natural Language Processing", "AI Research"]
author: "Shoubhik Banerjee"
draft: false
---

# Embedded Language Flows Advance Continuous Diffusion Models for Reasoning and Code

A new update introduces ELF-REG, an extension of Embedded Language Flows (ELF) that improves continuous diffusion language models on reasoning and code generation tasks.

## 🔍 Overview
- Fully continuous diffusion language models (dLMs) denoise continuous representations without intermediate discretization and decode all response tokens in parallel at the final step.
- Their performance on challenging reasoning tasks has been less established than that of autoregressive (AR) LLMs and masked dLMs.
- ELF is scaled to mathematical reasoning and code generation on GSM8K, MATH‑500, HumanEval, and MBPP.

## 🧩 How it works
- ELF-REG adds representation alignment and entanglement (REPA+REG).
- A frozen AR teacher supervises intermediate denoiser features and provides a global representation that is jointly denoised with the response.

## ⚙️ Performance highlights
| Model | Task | Metric | Score | NFE |
|---|---|---|---|---|
| ELF-REG-L | GSM8K | pass@1 | 55.96% | 64 |
| ELF-REG-L | MATH-500 | pass@1 | 13.39% | 128 |
| ELF-REG-L | HumanEval | pass@1 | 22.56% | 128 |
| ELF-REG-L | HumanEval | pass@10 | 41.21% | 16 |
| ELF-L (baseline) | MATH-500 | pass@1 | 10.55% |  |
- ELF-REG-L outperforms comparable‑scale dLMs on GSM8K and code tasks.
- It improves MATH‑500 pass@1 from 10.55% (ELF-L) to 13.39%.

## 📈 Low‑NFE capabilities
- Without few‑step training, task‑specific checkpoints support strong low‑NFE performance through early‑stop decoding, producing an intermediate clean prediction without completing the full denoising trajectory.


#diffusionLLM #ELF #AIresearch

---

*Source: [ELF-REG: Scaling Continuous Diffusion Language Models to Reasoning Tasks](https://arxiv.org/abs/2609.29102v1)*
