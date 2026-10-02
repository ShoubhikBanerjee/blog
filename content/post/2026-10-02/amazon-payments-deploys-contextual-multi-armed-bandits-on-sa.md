---
title: "Amazon Payments Deploys Contextual Multi‑Armed Bandits on SageMaker for Funnel Personalization"
slug: "amazon-payments-deploys-contextual-multiarmed-bandits-on-sagemaker-for-funnel-personalization"
description: "Amazon Payments applied AI‑based personalization to a product acquisition funnel, using a multi‑objective contextual multi‑armed bandit (MAB) on Amazon SageMaker AI."
date: 2026-10-02T22:04:29+05:30
tags: [AmazonPayments, MultiArmedBandit, Personalization, SageMaker]
categories: ["AI", "Machine Learning", "Reinforcement Learning", "Personalization", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-20979-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Payments Deploys Contextual Multi‑Armed Bandits on SageMaker for Funnel Personalization

Amazon Payments applied AI‑based personalization to a product acquisition funnel, using a multi‑objective contextual multi‑armed bandit (MAB) on Amazon SageMaker AI.

## 🔍 Overview
- "In this post, we share how Amazon Payments applied AI-based personalization to a product acquisition funnel, using a multi-objective contextual multi-armed bandit (MAB) on Amazon SageMaker AI."
- The customer journey in our use case comprises three steps: application start, submission, and approval.

## 📊 Results
- "In a seven-week online A/B test we currently see a high single-digit percentage relative lift in final-funnel conversion for one customer population, while another saw no improvement over the existing experience."
- "The problem turned out to be the content, not the model."

## 🤖 How it works
- "A multi-armed bandit (MAB) is a reinforcement learning method built for settings with many options and limited traffic."
- "It treats each content variation as an “arm,” tries each against live traffic, and steadily shifts impressions toward the arms that perform, while holding a fraction back to keep testing the rest."
- "In Amazon Payments, we chose UCB, a strategy that selects the arm with the highest estimated reward plus an uncertainty bonus, naturally balancing exploitation and exploration."
- "Its deterministic selection rule gives an auditable, reproducible decision for every impression, which makes sure every serving decision can be explained and reproduced if needed."
- "Contextual bandits condition directly on a feature vector (a numeric representation of attributes), so a pattern learned in one context transfers to every similar visit without separate per-group traffic."
- "Our production system represents each customer as a context vector of behavioral signals (payment behavior, transaction mix, and similar features) in place of a fixed segment."
- "The entity ID (an opaque key such as entity_id) is used only to route the learned recommendation back to the right visitor."
- "The entity ID is never a model input."
- "For a contextual approach, we selected Linear UCB (LinUCB), introduced by Li et al. (2010)."
- "LinUCB remains a battle-tested method that is computationally efficient, auditable (deterministic arm selection), and naturally handles a large arm space with limited warm-start data."
- "Its key assumption is that the expected reward for an arm is a linear function of the context vector, which lets it generalize to visitors it has not seen before."
- "Each arm keeps two running tallies updated on every impression: b , the reward ledger: which visitor signals led to conversions (b += reward · x)."
- "A , the experience ledger: which visitors the arm has seen (A += x·xᵀ, starting from identity)."
- "Dividing reward by experience gives the estimate (θ = A⁻¹·b)."
- "The experience ledger also shrinks the exploration bonus as evidence grows."
- "The bonus is context‑dependent."
- "It’s large for a kind of visitor the arm has rarely seen, and small for one it has seen often."
- "A plain bandit explores at a single global rate, while LinUCB adjusts how much it explores for every visitor it scores."
- "Optimizing one stage in isolation can degrade another."
- "Our approach optimizes the entire funnel simultaneously by running one LinUCB model per stage (start, submit, approve) and combining their UCB scores through a linear combination."
- "The stage weights can be assigned based on business priorities or learned by a separate calibration step."

## 🛠️ Architecture & Implementation
- "We also share a code repository that you can use to test this approach on synthetic data and understand the method hands‑on using Amazon SageMaker AI."


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-20979-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-20979-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-20979-3.jpg)

#AmazonPayments #MultiArmedBandit #Personalization #SageMaker

---

*Source: [Uplifting conversion across the acquisition funnel with personalization using contextual bandits on AWS | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/uplifting-conversion-across-the-acquisition-funnel-with-personalization-using-contextual-bandits-on-aws/)*
