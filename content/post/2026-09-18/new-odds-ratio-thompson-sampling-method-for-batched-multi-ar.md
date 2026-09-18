---
title: "New Odds-Ratio Thompson Sampling Method for Batched Multi-Armed Bandits"
slug: "new-odds-ratio-thompson-sampling-method-for-batched-multi-armed-bandits"
description: "A new paper specifies Odds-Ratio Thompson Sampling (OR-TS), an alternative update method for batched multi-armed bandits. While standard implementations carry each arm's absolute reward rate from one..."
date: 2026-09-18T18:02:43+05:30
tags: [MachineLearning, MultiArmedBandits, BayesianInference, DataScience]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Data Science"]
author: "Shoubhik Banerjee"
draft: false
---

# New Odds-Ratio Thompson Sampling Method for Batched Multi-Armed Bandits

A new paper specifies Odds-Ratio Thompson Sampling (OR-TS), an alternative update method for batched multi-armed bandits. While standard implementations carry each arm's absolute reward rate from one update to the next, OR-TS is designed to better handle level variations within batch updates.

## 🧩 How it works

Batched multi-armed bandits update on a service's own schedule. OR-TS changes how data is preserved between these updates:
* Instead of carrying absolute reward rates, OR-TS carries the joint posterior over log-odds contrasts.
* It fits the common level afresh in every batch, marginalizing it out.

This update is placed inside a Bayesian bandit agent with two controls:
* **Decay**: Controls how much past evidence survives an update.
* **Aggressiveness**: Controls how sharply belief becomes allocation.

## 📊 Performance and Evaluation

Researchers evaluated OR-TS against traditional absolute-rate memory across multiple scenarios, finding significant differences in performance when levels vary:

* **Public A/B Series**: Across 86 public A/B series, the level varies about twenty-five times more than the contrast.
* **Synthetic Environments**: In prespecified synthetic environments, a moving level costs absolute-rate memory five times the regret. Furthermore, it leaves the best arm below a majority of traffic in 7 of 20 runs, compared to zero runs for OR-TS.
* **Policy Simulations**: In a policy simulation built from 71 real experiments where the contrasts are too small to resolve, expected-click differences stay within 0.1% for 58 of them. Despite this, contrast memory still ends on the better arm more than twice as often.

## ⚙️ Key Limitations

* Where the contrasts themselves move, the bet fails. This specific failure case is also reported in the paper.

#MachineLearning #MultiArmedBandits #BayesianInference #DataScience

---

*Source: [Odds-Ratio Thompson Sampling: A Specification and Design Guide for Contrast-Based Multi-Armed Bandits](https://arxiv.org/abs/2609.19709v1)*
