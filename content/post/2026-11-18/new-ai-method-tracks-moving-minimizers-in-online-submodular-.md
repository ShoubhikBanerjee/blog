---
title: "New AI Method Tracks Moving Minimizers in Online Submodular Optimization"
slug: "new-ai-method-tracks-moving-minimizers-in-online-submodular-optimization"
description: "A new method for online submodular minimisation under bandit feedback has been introduced, addressing the challenge of tracking a moving minimizer as cost functions change over time. Unlike existing..."
date: 2026-11-18T18:09:03+05:30
tags: [submodularoptimization, banditalgorithms, onlinelearning, dynamicregret, zerothordermethods]
categories: ["AI", "Machine Learning", "Optimization", "Online Learning", "Bandit Algorithms"]
author: "Shoubhik Banerjee"
draft: false
---

# New AI Method Tracks Moving Minimizers in Online Submodular Optimization

## 📚 Introduction

A new method for online submodular minimisation under bandit feedback has been introduced, addressing the challenge of tracking a moving minimizer as cost functions change over time. Unlike existing bandit methods that only guarantee static regret against a single fixed subset, this approach provides dynamic regret bounds for tracking the evolving minimizer.

## 🔍 Overview

The paper focuses on online submodular minimisation where a decision maker plays subsets and observes only their costs, with cost functions changing over time. Key contributions include:

- First method with guarantees for tracking a moving minimizer in this setting
- Zeroth-order method using a two-point oracle for the Lovász extension
- Perturbed and base points rounded by a common random threshold
- Smoothing direction drawn from the unit sphere to create an unbiased estimator

## 🧩 How it Works

The proposed approach uses a two-point oracle for the Lovász extension where both evaluations are subsets that can be played. The method involves:

- Rounding perturbed and base points by a common random threshold
- Drawing the smoothing direction from the unit sphere
- Building a base evaluation as a zero-mean control variate for the smoothed gradient estimate

## ⚙️ Key Details

The method establishes the following performance bounds:

| Regret Type | Bound |
|-------------|-------|
| Dynamic Regret (General) | O((1+sqrt(P*_N))N^(3/4)) |
| Dynamic Regret (Small Drift) | O((1+sqrt(P*_N))N^(2/3)) |
| Static Regret | O(N^(3/4)) and O(N^(2/3)) |

Where P*_N represents the path length of the minimizer sequence.

## 🚀 Availability

- Status: Submitted on 17 Nov 2026
- Author: Amir Ali Farzin Mr.
- File size: 14,138 KB (v1)

#submodularoptimization #banditalgorithms #onlinelearning #dynamicregret #zeroth-ordermethods

---

*Source: [Bandit Online Submodular Minimisation Using Zeroth-Order Oracles](https://arxiv.org/abs/2611.22130v1)*
*Source: [Batched Stochastic Linear Bandits with 1-Bit Communication Constraints](https://arxiv.org/abs/2605.30976v2)*
