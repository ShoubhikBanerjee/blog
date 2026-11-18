---
title: "COSI Framework for Statistical Functionals"
slug: "cosi-framework-for-statistical-functionals"
description: "A new framework named COSI has been introduced for constructing confidence sets for statistical functionals."
date: 2026-11-18T18:09:03+05:30
tags: [S, t, a, t, i, s, t, i, c, a, l, I, n, f, e, r, e, n, c, e, M, a, c, h, i, n, e, L, e, a, r, n, i, n, g, R, o, b, u, s, t, n, e, s, s, C, o, n, f, i, d, e, n, c, e, I, n, t, e, r, v, a, l, s]
categories: ["AI", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "S", "t", "a", "t", "i", "s", "t", "i", "c", "a", "l", "I", "n", "f", "e", "r", "e", "n", "c", "e", ",", "D", "a", "t", "a", "S", "c", "i", "e", "n", "c", "e", ",", "R", "o", "b", "u", "s", "t", "S", "t", "a", "t", "i", "s", "t", "i", "c", "s"]
author: "Shoubhik Banerjee"
draft: false
---

# COSI Framework for Statistical Functionals

A new framework named COSI has been introduced for constructing confidence sets for statistical functionals.

## 🔍 Overview
COSI stands for COnfidence from Scale Invariance. It is a framework for constructing confidence sets for statistical functionals. The framework builds on HulC (Hull-based Confidence), which uses median unbiasedness to construct confidence sets from batch estimates.

## 🧩 How it works
The process involves dividing the data into batches, computing an estimate in each batch, and retaining each candidate parameter value for which the batch estimates pass a test of scale invariance.

## ⚙️ Key details
COSI uses scale-invariance properties shared by many common estimators. The resulting confidence sets are asymptotically valid under weaker assumptions than classical Wald and bootstrap procedures require. Additionally, their coverage can be closer to the nominal level in small samples.

## 💡 Why it matters
Applications include:
*   Robust inference for the mean
*   Regression coefficients in misspecified linear models
*   Tensor norms
*   Fréchet means

#S #t #a #t #i #s #t #i #c #a #l # #I #n #f #e #r #e #n #c #e #, # #M #a #c #h #i #n #e # #L #e #a #r #n #i #n #g #, # #R #o #b #u #s #t #n #e #s #s #, # #C #o #n #f #i #d #e #n #c #e # #I #n #t #e #r #v #a #l #s

---

*Source: [COSI: A Framework for Robustly Valid Inference](https://arxiv.org/abs/2611.22096v1)*
