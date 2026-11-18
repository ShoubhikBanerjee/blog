---
title: "New Counterexamples Challenge E-Means Clustering Algorithm"
slug: "new-counterexamples-challenge-e-means-clustering-algorithm"
description: "A new technical paper titled 'Two Counterexamples for e-means' has been submitted, presenting cases where the e-means algorithm performs worse than standard k-means. The study focuses on the..."
date: 2026-11-18T22:09:17+05:30
tags: [MachineLearning, Clustering, kMeans, AlgorithmAnalysis]
categories: ["AI", "Machine Learning", "Computer Science", "Algorithms"]
author: "Shoubhik Banerjee"
draft: false
---

# New Counterexamples Challenge E-Means Clustering Algorithm

A new technical paper titled "Two Counterexamples for e-means" has been submitted, presenting cases where the e-means algorithm performs worse than standard k-means. The study focuses on the limitations of a method that combines exponential averaging and cluster revival.

## 🔍 Overview
The paper, submitted on November 17, 2026, by Zhenisbek Assylbekov, provides two counterexamples to the published recipe of e-means. These examples demonstrate that e-means can result in a higher final loss than the standard k-means algorithm (Lloyd, 1982) when starting from identical initial centers.

## 🧩 How it works
The analysis highlights specific failure modes of the e-means approach:
- **Mass-based revival**: This component can destroy a global optimum.
- **Loss Ratio**: The ratio of expected losses can become unbounded, even when using k-means++ seeding.

## ⚙️ Key details
- **Paper Title**: Two Counterexamples for e-means
- **Submission Date**: November 17, 2026
- **Author**: Zhenisbek Assylbekov
- **Context**: Computer Science > Machine Learning
- **Comparative Baseline**: Standard k-means (Lloyd, 1982)

#MachineLearning #Clustering #kMeans #AlgorithmAnalysis

---

*Source: [Two Counterexamples for e-means](https://arxiv.org/abs/2611.22065v1)*
