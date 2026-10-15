---
title: "Tail Competition Theory Explains Best‑of‑N Sampling Scaling"
slug: "tail-competition-theory-explains-bestofn-sampling-scaling"
description: "A paper submitted on 14 Oct 2026 proposes a tail‑competition framework for understanding the scaling behavior of Best‑of‑N sampling in large language models."
date: 2026-10-15T18:01:40+05:30
tags: [BestOfN, Sampling, ExtremeValueTheory, RewardModel]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Theory"]
author: "Shoubhik Banerjee"
draft: false
---

# Tail Competition Theory Explains Best‑of‑N Sampling Scaling

A paper submitted on 14 Oct 2026 proposes a tail‑competition framework for understanding the scaling behavior of Best‑of‑N sampling in large language models.

## 🔍 Overview
- Best‑of‑N sampling is a simple inference‑time scaling strategy for large language models.
- The paper studies Best‑of‑N as a competition between the extreme reward tails of correct and incorrect responses.
- Success depends on both the probability of sampling a correct response and whether correct responses dominate the upper tail.

## 🧩 How it works
- Using extreme value theory, the authors identify three asymptotic regimes:
  - **Correct‑tail‑dominant**
  - **Incorrect‑tail‑dominant**
  - **Critical** – explains both monotonic gains and reward‑hacking‑induced degradation.
- The framework treats the selection process as a tail‑competition rather than a simple probability comparison.

## ⚙️ Key details
- Finite‑sample scaling laws are derived for representative reward distributions.
- Under Gaussian rewards, incorrect responses with sufficiently large variance can dominate selection even when their mean reward is lower.
- Convergence with an incomplete selector can be polynomial rather than exponential, unlike oracle selection.
- A lightweight *tail‑tension* criterion is proposed to estimate when additional sampling may become harmful.
- Experiments on synthetic data and real reward‑model scores match the predicted regimes, scaling laws, and diagnostic behavior.

## 💡 Why it matters
- The tail‑competition view offers a unified lens on Best‑of‑N sampling for verifiable problems.
- It clarifies when increasing the number of samples improves performance and when it may trigger reward hacking.
- The proposed tail‑tension diagnostic can guide practitioners in deciding how much sampling is beneficial.

#BestOfN #Sampling #ExtremeValueTheory #RewardModel

---

*Source: [Tail Competition Explains Scaling in Best-of-N Sampling for Verifiable Problems](https://arxiv.org/abs/2610.19362v1)*
