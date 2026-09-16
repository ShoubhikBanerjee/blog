---
title: "CRN v2 Module Fixes Errors in Frozen Gemma 4 Model Without Degrading Capabilities"
slug: "crn-v2-module-fixes-errors-in-frozen-gemma-4-model-without-degrading-capabilities"
description: "Researchers have introduced CRN v2, a lightweight correction module designed to fix errors in a frozen Gemma 4 E2B model without degrading its original capabilities. The development addresses the..."
date: 2026-09-16T22:05:42+05:30
tags: [G, e, m, m, a, 4, L, o, g, i, t, C, o, r, r, e, c, t, i, o, n, F, r, o, z, e, n, M, o, d, e, l, s, P, a, r, a, m, e, t, e, r, E, f, f, i, c, i, e, n, t]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "N", "a", "t", "u", "r", "a", "l", "L", "a", "n", "g", "u", "a", "g", "e", "P", "r", "o", "c", "e", "s", "s", "i", "n", "g", ",", "M", "o", "d", "e", "l", "E", "f", "f", "i", "c", "i", "e", "n", "c", "y", ",", "F", "i", "n", "e", "-", "T", "u", "n", "i", "n", "g"]
author: "Shoubhik Banerjee"
draft: false
---

# CRN v2 Module Fixes Errors in Frozen Gemma 4 Model Without Degrading Capabilities

Researchers have introduced CRN v2, a lightweight correction module designed to fix errors in a frozen Gemma 4 E2B model without degrading its original capabilities. The development addresses the challenge of improving model accuracy while keeping the base model static.

## 🔍 Overview
CRN v2 is a logit-level correction module that sits atop a fully frozen Gemma 4 E2B model. The study focuses on a practical question: can a small correction module fix errors without harming the base model's performance?

## ⚙️ Key Details
*   **Architecture:** The module is lightweight, containing approximately 34 million trainable parameters (0.73% of the 4.65 billion text module).
*   **Training Method:** The base model is never updated. The correction module learns through supervised fine-tuning followed by reference-free DPO on 83,400 error-correction pairs.
*   **Design Principle:** The approach is a study of a specific design principle—frozen base + logit correction + KL anchoring—rather than an architectural novelty.

## 📊 Performance & Comparison
The module was tested on a 60-question domain exam (CEHRI: Certified Human-Robot Intelligence) covering facts, arithmetic, and implicit-goal reasoning.

| Module | Parameters | Correction Rate (CEHRI) | Capability Loss |
| :--- | :--- | :--- | :--- |
| **CRN v2** | ~34M | 53.3% (reworded: 43.3%) | None (0%) |
| **LoRA Baseline** | 6.6M (rank 19) | 83.3% | 30-75% |

On standard benchmarks (MMLU/BoolQ N=200; car-wash N=8), CRN v2 showed no degradation in tested capabilities.

## 🧪 Ablation Study
The researchers tested various configurations to optimize the correction module:
*   **KL Preservation:** The KL preservation term (lambda=0.1) is critical. Lowering it to 0.01 degrades correction to 35.0%.
*   **Hidden-State Injection:** A variant with earlier layer injection (1.6M params, SFT-only) reaches 50.0%/55.8% but does not exceed logit correction results.
*   **Multi-depth:** Multi-depth logit correction (~35M params) reaches only 40%.
*   **Training Duration:** Longer training (5,000 SFT + 2,000 DPO) did not exceed the 53.3% correction rate achieved with the standard configuration.

## 🚀 Availability
All code, main-result weights, and evaluation scripts have been released. The deep variant is available as code only, with no trained deep checkpoints.


![figure](https://arxiv.org/static/base/1.0.1/images/funders/simons-foundation.png)

![figure](https://arxiv.org/static/base/1.0.1/images/funders/simons-foundation-international.png)

![figure](https://arxiv.org/static/base/1.0.1/images/funders/schmidt-sciences.png)

#G #e #m #m #a #4 #, # #L #o #g #i #t #C #o #r #r #e #c #t #i #o #n #, # #F #r #o #z #e #n #M #o #d #e #l #s #, # #P #a #r #a #m #e #t #e #r #E #f #f #i #c #i #e #n #t

---

*Source: [Safe Error Correction for Language Models: Frozen-Base Adjustment with Capability Preservation](https://arxiv.org/abs/2609.16145v1)*
*Source: [Fine-Tuning Fixes Mode Collapse and Over-Dispersion in LLMs](https://arxiv.org/abs/2609.16454v1)*
*Source: [A Framework for Generating Valid Context-Specific Benchmarks through Expert Guidance](https://arxiv.org/abs/2609.16592v1)*
*Source: [Few-Shot Degradation Is Not What It Seems: Behavioral Evidence, Representation Analysis, and a Random-Text Control Across 12 Models, 2 Tasks, and 2 Architectures](https://arxiv.org/abs/2609.15990v1)*
