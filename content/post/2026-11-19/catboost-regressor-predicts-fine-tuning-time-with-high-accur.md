---
title: "CatBoost Regressor Predicts Fine-Tuning Time with High Accuracy"
slug: "catboost-regressor-predicts-fine-tuning-time-with-high-accuracy"
description: "A preview of an upcoming paper titled 'Predicting End-to-End Fine-Tuning Time for Generative Language Models' is available. It proposes a method to improve GPU scheduling by predicting job duration..."
date: 2026-11-19T22:12:49+05:30
tags: [M, a, c, h, i, n, e, L, e, a, r, n, i, n, g, F, i, n, e, T, u, n, i, n, g, G, P, U, S, c, h, e, d, u, l, i, n, g, C, a, t, B, o, o, s, t, T, r, a, n, s, f, o, r, m, e, r, s]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "G", "P", "U", "C", "o", "m", "p", "u", "t", "i", "n", "g", ",", "D", "e", "e", "p", "L", "e", "a", "r", "n", "i", "n", "g", ",", "S", "o", "f", "t", "w", "a", "r", "e", "E", "n", "g", "i", "n", "e", "e", "r", "i", "n", "g"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6a725daa5ca641a21ab61956/J6DIf4Len_31Tj-CQlQXY.png"
author: "Shoubhik Banerjee"
draft: false
---

# CatBoost Regressor Predicts Fine-Tuning Time with High Accuracy

A preview of an upcoming paper titled "Predicting End-to-End Fine-Tuning Time for Generative Language Models" is available. It proposes a method to improve GPU scheduling by predicting job duration more accurately than traditional calculations.

## 🔍 Overview
GPUs are among the most expensive and scarcest resources in AI today. Anyone running a shared cluster must decide which jobs go on which GPUs and in what order. This plan is only as good as the estimate of how long each job will take.

When a job finishes hours early, GPUs sit idle. When it runs hours late, everything queued behind it slips. Better duration estimates turn this into planning instead of guesswork: what runs, when, and on how many GPUs, with less idle capacity in between.

The usual estimate most teams use is a back-of-the-envelope FLOP calculation. It says nine hours, and the job finishes the next afternoon. The short version: the usual FLOP-based estimate explains little of what we observed.

## 🧩 Methodology
We took 272 real supervised fine-tuning (SFT) jobs from our production pool of NVIDIA H200 GPUs, about 7,382 GPU-hours in total, and compared analytical estimates against learned predictors.

We treat end-to-end duration as a supervised regression problem. Everything is known before dispatch. We compared Linear Regression, Ridge, XGBoost and CatBoost.

| Method | R² | MAE (h) |
| :--- | :--- | :--- |
| FLOP-based estimate | 0.31 | 12.41 |
| CatBoost regressor | 0.98 | 1.71 |

A CatBoost regressor that only sees information available before dispatch reaches R² = 0.98, with a mean absolute error of 1.71 h and a median error of 0.51 h in 5-fold cross-validation.

## ⚙️ Key Details
The regressor sees more training-specific signals, such as evaluation cadence, checkpoint policy, per-GPU load and fine-tuning regime, and it learns the nonlinear interactions between them from past runs.

For a dense Transformer, training costs roughly 6·P·D floating-point operations, where P is the parameter count and D the number of training tokens.

Divide that by what your GPUs can deliver and you get a training-loop time:

$$ T_{theoretical} = \frac{6 \cdot P \cdot D}{N_{GPU} \cdot FLOPS_{peak} \cdot MFU} $$

Real jobs never run at peak because of memory traffic, communication and kernel inefficiencies, so MFU typically sits somewhere between 30% and 60%.

### Overheads
Before the first step there is environment setup, model download and loading, and tokenization. During training there are periodic evaluations and checkpoint uploads. At the end, the final model goes to object storage.

On a multi-tenant cluster, all of this competes with other jobs for network and storage I/O. These overheads depend on configuration, and they do not scale neatly with workload or GPU count. Two jobs with the same nominal compute can finish hours apart.

### Configuration
*   **Jobs:** 272 SFT runs from operational logs of a corporate production environment, covering several model families up to 15 billion parameters, both LoRA and full fine-tuning.
*   **Hardware:** Jobs ran on 1, 2 or 4 GPUs drawn from a pool of 8 to 32 H200s across 1 to 4 nodes, alongside other training and inference workloads.
*   **Duration:** Measured times include real contention. Durations ranged from 1.6 to 172.4 hours, with a mean of 23.43 h and a median of 15.29 h.
*   **Stack:** Hugging Face Transformers and Unsloth.

## 🚀 Availability
The full version will be on arXiv soon.

![figure](https://cdn-uploads.huggingface.co/production/uploads/6a725daa5ca641a21ab61956/uD4Td4N-bvoPStQBNx8yy.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6a725daa5ca641a21ab61956/MHyGZSFJZ6HXmwAUCTAnF.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6a725daa5ca641a21ab61956/gQbjzLv37ag5kX7nZuuMh.png)

#M #a #c #h #i #n #e #L #e #a #r #n #i #n #g #, # #F #i #n #e #T #u #n #i #n #g #, # #G #P #U #, # #S #c #h #e #d #u #l #i #n #g #, # #C #a #t #B #o #o #s #t #, # #T #r #a #n #s #f #o #r #m #e #r #s

---

*Source: [Why your fine-tuning job takes longer than the FLOPs say](https://huggingface.co/blog/Dharma-AI/predicting-fine-tuning-time)*
