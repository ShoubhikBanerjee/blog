---
title: "Evaluating When Offline Tests Can Replace A/B Experiments"
slug: "evaluating-when-offline-tests-can-replace-a-b-experiments"
description: "In our paper, When Can You Ship on Evals Alone?, we work through this problem in detail."
date: 2026-11-19T22:12:49+05:30
tags: [offlineevals, abtesting, aievaluation]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Product Development"]
image: "https://images.ctfassets.net/p762jor363g1/4w1jduYhnyiLjUjI8Ar3ZH/e354d444350d376d11dbde38a9213272/2.1__1_.png"
author: "Shoubhik Banerjee"
draft: false
---

# Evaluating When Offline Tests Can Replace A/B Experiments

In our paper, When Can You Ship on Evals Alone?, we work through this problem in detail.

## 🔍 Overview
- When we change an AI feature, say a new prompt or a different underlying LLM, there are two main ways to check whether it got better.
- Offline evals are quick tests run on a fixed set of sample prompts before any real user sees the change, often with other LLM-as-judges grading the answers.
- A/B tests give the new version to a random group of real users and compare how they behave against users on the old version.
- The potential upside is substantial.
- Offline evals take hours; A/B tests often take days or weeks.

## 📈 Why offline evals matter
- If we could confidently make product decisions based on offline evals alone, we could shorten feedback loops and iterate much faster.

## ⚙️ Formal problem definition
- We formalize the “when we can ship based on eval alone” as follows: We want to make shipping decisions based on the offline eval while bounding the risk of shipping something that actually harms the online metric.
- If we want to bound the risk of shipping something that harms the online metric, ideally we need to know the conditional distribution of the true online treatment effect, given the observed offline eval treatment effect.
- We cannot have a heterogeneous set of experiments where, for some types of changes, an improvement in the eval corresponds to an improvement in the online outcome, while for others the relationship is different or even reversed.

## 📊 Noise and correlation
- Both numbers are noisy estimates, not exact values.
- Offline eval scores have sampling errors from several sources, including randomly sampling examples from a larger eval set, and using an LLM to grade the answers (LLM-as-a-judge).
- Online treatment effects are estimated with sampling error too.
- The short version: if we ignore noise, a strong offline-online relation can look weak.
- The squared correlation (R², roughly how much of the online result the eval explains, from 0 to 100%) determines how much uncertainty remains in the online effect after observing the eval.
- A high R² means the eval is highly informative about the online outcome.
- A low R² means substantial uncertainty remains, regardless of how precisely we measure the eval.
- Using a naive estimator, we find that the squared correlation is only 24% in the working example.
- In our example, a naive estimate says the eval explains 24% of the variation in online results, when the true figure is 60%.
- Noise is a problem too, because it can hide a strong link between offline and online results.

## 🛠️ Assumptions
- We assume that we have a sufficiently large, homogeneous pool of paired offline eval effects and online treatment effects.
- And, we assume that any future changes for which we want to make eval-based decisions come from the same class, with the same underlying relationship between offline and online effects (also called exchangeability).
- We assume that the true offline and online treatment effects follow a bivariate normal distribution.
- We assume that measurement errors are centered at zero with known variances, independent across interventions.
- We assume that any errors introduced by using an LLM as a judge are independent of the treatment arm.

![figure](https://images.ctfassets.net/p762jor363g1/4JjjfhoP5DUhFU06MmME7O/2aa56a7be9fd8cdc5a736c1d6abf118f/Figure_1.png)

![figure](https://images.ctfassets.net/p762jor363g1/7oR6tYsGJV1M28QWttJNRS/2c84f5c6cd5036c84433145e623b6cd4/Figure_2.png)

![figure](https://images.ctfassets.net/p762jor363g1/2FJnYkQPl0uAJALhkMGBU5/afe7d2fe6ce4b0cc166f781e0b83fb38/Figure_3.png)

#offline-evals #ab-testing #ai-evaluation

---

*Source: [When Can You Ship on Offline Evals Alone? | Spotify Engineering](https://engineering.atspotify.com/2026/11/when-can-you-ship-on-offline-evals-alone/)*
