---
title: "New Bandit Algorithms Achieve Near-Optimal Regret in Adversarial Convex Optimization"
slug: "new-bandit-algorithms-achieve-near-optimal-regret-in-adversarial-convex-optimization"
description: "Researchers have advanced the state of the art in adversarial bandit convex optimization and robust reinforcement learning with new theoretical bounds and algorithms."
date: 2026-11-26T18:08:23+05:30
tags: []
categories: ["AI"]
author: "Shoubhik Banerjee"
draft: false
---

# New Bandit Algorithms Achieve Near-Optimal Regret in Adversarial Convex Optimization

Researchers have advanced the state of the art in adversarial bandit convex optimization and robust reinforcement learning with new theoretical bounds and algorithms.

## 📚 Two Key Papers

Two papers were submitted in late November 2026 addressing distinct but related problems in sequential decision-making.

| Paper | Focus Area |
|-------|------------|
| On the Impact of Extra Information in Bandit Learning | How extra information affects bandit algorithms |
| Adversarial Bandit Convex Optimization with $d^{3/2}\sqrt{n}$ Regret | Improved regret bounds for adversarial convex optimization |

## 🔍 How Extra Information Can Hurt Performance

In a stochastic bandits setup with exogenous extra information, researchers examine whether unbiased extra reward samples are guaranteed to reduce regret. They introduce a formal notion of 'non-degradation under extra information' and demonstrate that the widely used Upper Confidence Bound (UCB) algorithm violates this property — there exist benign extra-information under which UCB incurs strictly higher regret than when run without extra information. In contrast, Thompson Sampling and Explore-Then-Commit appear to benefit from the same extra information. A meta-algorithm is proposed that provably enforces non-degradation for a broad class of bandit algorithms.

## ⚙️ Improved Regret Bounds

For adversarial bandit convex optimization — where a learner chooses points in a convex body and observes noisy convex loss values chosen adaptively by an adversary — researchers improve the best known regret bound from $\widetilde O(d^{5/2}\sqrt n)$ to $\widetilde O(d^{3/2}\sqrt n)$, matching the rate conjectured by Bubeck et al. (2017). This new bound, together with a recent lower bound of $\Omega(d^{4/3}\sqrt n)$, determines the minimax regret up to a factor of $d^{1/6}$ and logarithmic factors. The algorithm uses an online Newton step with Gaussian exploration, estimating gradient and Hessian of Gaussian smoothing rather than optimistic surrogates.

## 📈 Sample Complexity in Robust Reinforcement Learning

In distributionally robust reinforcement learning with KL divergence-defined uncertainty sets, researchers develop tighter and complete upper and lower bounds for sample complexity. The upper bound is the tightest among existing studies and improves upon the best-known bound by at least the order of $\mathcal{O}(\min\{p_\wedge^{-1},(1-\gamma)^{-1}\})$ for uncertainty level $\delta\in(0,1)$. The lower bound holds for any uncertainty level, and the bounds nearly match in various regimes.

## 🚀 Availability

Both papers were submitted in November 2026: one on 24 November and the other on 25 November, both listed under Statistics > Machine Learning on arXiv.

---

*Source: [On the Impact of Extra Information in Bandit Learning: More is Not Always Merrier](https://arxiv.org/abs/2611.33479v1)*
*Source: [Adversarial Bandit Convex Optimization with $d^{3/2}\sqrt{n}$ Regret](https://arxiv.org/abs/2611.33531v1)*
*Source: [Improved Sample Complexity of Robust Reinforcement Learning with KL Uncertainty Sets](https://arxiv.org/abs/2611.33592v1)*
