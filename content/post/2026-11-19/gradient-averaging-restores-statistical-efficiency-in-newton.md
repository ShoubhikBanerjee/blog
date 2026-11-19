---
title: "Gradient Averaging Restores Statistical Efficiency in Newton Sketch Methods"
slug: "gradient-averaging-restores-statistical-efficiency-in-newton-sketch-methods"
description: "Gradient averaging restores statistical efficiency in online sketched Newton methods without extra computational cost."
date: 2026-11-19T12:23:35+05:30
tags: [GradientAveraging, NewtonSketch, StatisticalEfficiency]
categories: ["AI", "Machine Learning", "Optimization", "Statistical Inference"]
author: "Shoubhik Banerjee"
draft: false
---

# Gradient Averaging Restores Statistical Efficiency in Newton Sketch Methods

Gradient averaging restores statistical efficiency in online sketched Newton methods without extra computational cost.

## 🔍 Overview
- Online sketched Newton methods solve each Newton system with an inner randomized sketching solver.
- Prior work shows a computational‑statistical trade‑off: sketching cuts per‑step cost from $O(d^3)$ to $O(d^2)$ but inflates the limiting covariance of both the last and the averaged Newton iterates.

## 🧩 How it works
- The proposed fix replaces the stochastic gradient at each step with a moving average of past gradients.
- This gradient averaging requires no additional oracle evaluations and leaves the contraction bound of the inner sketching solver unchanged.

## ⚙️ Key results
- The last sketched Newton iterate with gradient averaging attains a limiting covariance no larger than without averaging.
- The averaged iterate achieves the minimax optimal limiting covariance, matching that of the exact Newton method.
- This is the first analysis showing that randomness introduced for computational efficiency need not compromise statistical efficiency when proper gradient estimates are used.

## 🧪 Experimental validation
- Numerical experiments on linear and logistic regression confirm the theoretical covariance comparisons.


#GradientAveraging #NewtonSketch #StatisticalEfficiency

---

*Source: [A Free Lunch: Gradient Averaging Achieves Optimal Statistical Efficiency in Newton Sketch](https://arxiv.org/abs/2611.23671v1)*
