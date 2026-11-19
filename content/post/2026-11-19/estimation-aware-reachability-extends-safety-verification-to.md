---
title: "Estimation-Aware Reachability Extends Safety Verification to Noisy Robot Estimates"
slug: "estimation-aware-reachability-extends-safety-verification-to-noisy-robot-estimates"
description: "A new paper titled 'Estimation-Aware Reachability' extends Hamilton-Jacobi Reachability to account for the noisy estimates used by real robots."
date: 2026-11-19T18:06:46+05:30
tags: [H, a, m, i, l, t, o, n, J, a, c, o, b, i, R, o, b, o, t, i, c, s, S, a, f, e, t, y, V, e, r, i, f, i, c, a, t, i, o, n, U, n, c, e, r, t, a, i, n, t, y, E, s, t, i, m, a, t, i, o, n]
categories: ["AI", "R", "o", "b", "o", "t", "i", "c", "s", ",", "C", "o", "n", "t", "r", "o", "l", "S", "y", "s", "t", "e", "m", "s", ",", "A", "r", "t", "i", "f", "i", "c", "i", "a", "l", "I", "n", "t", "e", "l", "l", "i", "g", "e", "n", "c", "e", ",", "C", "o", "m", "p", "u", "t", "a", "t", "i", "o", "n", "a", "l", "M", "a", "t", "h", "e", "m", "a", "t", "i", "c", "s"]
author: "Shoubhik Banerjee"
draft: false
---

# Estimation-Aware Reachability Extends Safety Verification to Noisy Robot Estimates

A new paper titled "Estimation-Aware Reachability" extends Hamilton-Jacobi Reachability to account for the noisy estimates used by real robots.

## 🔍 Overview
Hamilton-Jacobi Reachability computes the states from which a system can be kept safe under worst-case disturbances, but it assumes the state is known exactly. Real robots, however, act on noisy estimates whose uncertainty evolves with their motion. This work extends Hamilton-Jacobi Reachability to the robot's belief, estimate, and uncertainty.

## 🧩 How it works
The formulation treats unexpected measurements as a bounded adversary and enlarges the unsafe set by the current uncertainty. This ensures that certified states are safe with a prescribed probability.

## ⚙️ Key details
*   The formulation is compatible with existing solvers.
*   In simulation, the resulting safety filters nearly eliminate the collisions of certainty-equivalent HJ.
*   The approach is less conservative than equally safe uncertainty-padding baselines.

## 🚀 Availability
The implementation code is available at the provided URL.

#H #a #m #i #l #t #o #n #J #a #c #o #b #i #, # #R #o #b #o #t #i #c #s #, # #S #a #f #e #t #y #V #e #r #i #f #i #c #a #t #i #o #n #, # #U #n #c #e #r #t #a #i #n #t #y #, # #E #s #t #i #m #a #t #i #o #n

---

*Source: [Estimation-Aware Reachability](https://arxiv.org/abs/2611.23830v1)*
