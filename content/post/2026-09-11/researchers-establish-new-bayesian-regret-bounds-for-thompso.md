---
title: "Researchers Establish New Bayesian Regret Bounds for Thompson Sampling in Bandit Convex Optimization"
slug: "researchers-establish-new-bayesian-regret-bounds-for-thompson-sampling-in-bandit-convex-optimization"
description: "Researchers Bakhtiari, Lattimore, and Szepesvári (COLT 2025) have established new Bayesian regret bounds for Thompson sampling (TS) applied to bandit convex optimization problems."
date: 2026-09-11T18:06:00+05:30
tags: [ThompsonSampling, BanditOptimization, COLT2025, MachineLearningTheory]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Mathematics"]
author: "Shoubhik Banerjee"
draft: false
---

# Researchers Establish New Bayesian Regret Bounds for Thompson Sampling in Bandit Convex Optimization

Researchers Bakhtiari, Lattimore, and Szepesvári (COLT 2025) have established new Bayesian regret bounds for Thompson sampling (TS) applied to bandit convex optimization problems.

## 🔍 Overview

The study differentiates between monotone and non-monotone ridge losses in convex optimization. The researchers provide theoretical bounds on the performance of Thompson sampling under these two distinct conditions.

## ⚙️ Key details

The findings establish the following regret bounds:

| Loss Type | Bayesian Regret Bound |
| :--- | :--- |
| Monotone ridge losses | $\tilde O(d^{5/2}\sqrt n)$ |
| Non-monotone convex ridge losses | $\tilde O(d^{9/2}\sqrt n)$ |

## 🧩 How it works

*   **Monotone Case:** The proof utilizes a single-removal John-ellipsoid dichotomy.
*   **Non-Monotone Case:** The researchers demonstrate that the John-ellipsoid dichotomy fails for non-monotone links via an explicit twelve-point configuration. Instead, they employ an $O(d^2)$ cardinality bound for "uninformative" configurations.
*   **Mathematical Argument:** The bound relies on a Boolean rounding argument, which posits that a 0-1 matrix within $1/(4r)$ in max-norm of a rank-$r$ matrix has a rank of at most $2r-1$.
*   **Verification:** The team constructed $d(d+1)$ uninformative losses, demonstrating that the cardinality bound is tight up to constants in the large-diameter-to-gap regime.

## 💡 Why it matters

While these bounds have been established, it remains an open question whether the $d^{5/2}$ dependence observed in the monotone case can be retained for non-monotone scenarios.

#ThompsonSampling #BanditOptimization #COLT2025 #MachineLearningTheory

---

*Source: [Thompson Sampling for Non-Monotone Convex Ridge Bandits: Monotonicity Is Not Needed for Polynomial Regret](https://arxiv.org/abs/2609.10981v1)*
