---
title: "LUCID Framework Improves Dynamic Cardiac PET Imaging Using Large-Scale CT Data"
slug: "lucid-framework-improves-dynamic-cardiac-pet-imaging-using-large-scale-ct-data"
description: "Researchers have introduced LUCID, a framework designed to synthesize $μ$-maps for dynamic cardiac $^{82}$Rb PET imaging by leveraging anatomical priors from a large-scale CT dataset."
date: 2026-11-19T22:12:49+05:30
tags: [D, i, f, f, u, s, i, o, n, M, o, d, e, l, s, M, e, d, i, c, a, l, I, m, a, g, i, n, g, P, E, T, C, T, C, o, m, p, u, t, e, r, V, i, s, i, o, n, D, e, e, p, L, e, a, r, n, i, n, g]
categories: ["AI", "C", "o", "m", "p", "u", "t", "e", "r", "V", "i", "s", "i", "o", "n", ",", "D", "e", "e", "p", "L", "e", "a", "r", "n", "i", "n", "g", ",", "M", "e", "d", "i", "c", "a", "l", "I", "m", "a", "g", "i", "n", "g", ",", "D", "i", "f", "f", "u", "s", "i", "o", "n", "M", "o", "d", "e", "l", "s"]
author: "Shoubhik Banerjee"
draft: false
---

# LUCID Framework Improves Dynamic Cardiac PET Imaging Using Large-Scale CT Data

Researchers have introduced LUCID, a framework designed to synthesize $μ$-maps for dynamic cardiac $^{82}$Rb PET imaging by leveraging anatomical priors from a large-scale CT dataset.

## 🔍 Overview

LUCID (Large-scale Unpaired CT-Informed Diffusion) is a framework that transfers anatomical priors learned from 10,000 chest CT volumes in the public CT-RATE dataset to $μ$-map synthesis for dynamic cardiac $^{82}$Rb PET.

## 🧩 How it works

The framework operates through a three-step process to generate $μ$-maps:

*   A convolutional neural network (CNN) predicts an initial $μ$-map from each NAC PET frame.
*   A CT-pretrained diffusion backbone refines a low-noise perturbation of the CNN prediction through a single denoising step, conditioned on the corresponding NAC PET frame via ControlNet.
*   Frame-wise predictions are averaged voxel-wise to obtain the final $μ$-map.

The framework also introduces the voxel-wise temporal standard deviation (TSD) to quantify inter-frame variability without requiring a reference $μ$-map.

## ⚙️ Key details

*   **Evaluation:** LUCID was evaluated on an in-house dataset of 102 patients. It achieved the best quantitative accuracy while maintaining competitive inter-frame consistency.
*   **Ablation Studies:** Refinement with a diffusion backbone pretrained on in-house CT data from the training patients was less accurate than the CNN prediction alone. This highlights the importance of large-scale CT pretraining.

#D #i #f #f #u #s #i #o #n #M #o #d #e #l #s #, # #M #e #d #i #c #a #l #I #m #a #g #i #n #g #, # #P #E #T #C #T #, # #C #o #m #p #u #t #e #r #V #i #s #i #o #n #, # #D #e #e #p #L #e #a #r #n #i #n #g

---

*Source: [Image-Condition-Controlled Diffusion Network with Large-Scale CT Pretraining for CT-Free Attenuation Correction in Dynamic Cardiac PET](https://arxiv.org/abs/2611.23672v1)*
