---
title: "English Calibration Hurts Lithuanian Performance in Pruned MoE Language Models"
slug: "english-calibration-hurts-lithuanian-performance-in-pruned-moe-language-models"
description: "English calibration, which works well for many high‑resource languages, was found to severely damage Lithuanian performance when applied to expert‑pruned Mixture‑of‑Experts (MoE) language models."
date: 2026-11-06T18:03:32+05:30
tags: [MixtureOfExperts, ModelCompression, MultilingualAI]
categories: ["AI", "Machine Learning", "Natural Language Processing", "Model Compression"]
author: "Shoubhik Banerjee"
draft: false
---

# English Calibration Hurts Lithuanian Performance in Pruned MoE Language Models

English calibration, which works well for many high‑resource languages, was found to severely damage Lithuanian performance when applied to expert‑pruned Mixture‑of‑Experts (MoE) language models.

## 🔍 Overview
- Expert pruning compresses MoE language models by removing experts that a calibration set marks as unimportant.
- Prior studies show English calibration usually transfers well to other high‑resource languages.
- This study tests whether that transfer holds for Lithuanian.

## 🧩 How Expert Pruning Works
- A calibration set evaluates the importance of each expert in an MoE model.
- Unimportant experts are removed, yielding a smaller, faster model.
- The process is called REAP in the experiments.

## ⚙️ Experiment Details
- Four MoE models were pruned with REAP, removing either **25 %** or **50 %** of the experts.
- Calibration sets used were:
  1. English only
  2. Lithuanian only
  3. A mixed English‑Lithuanian set
- The pruned models were evaluated on **reading comprehension**, **translation**, and **language modelling** for both English and Lithuanian.

## 📊 Results
- **English calibration does not transfer to Lithuanian:**
  - At 25 % pruning, English comprehension dropped by a median of **1.7 points**.
  - Lithuanian comprehension dropped by **21.4 points** under the same English calibration.
- **Asymmetric transfer:** Lithuanian calibration removed most of the Lithuanian loss and never significantly hurt English comprehension.
  - English comprehension was on average **2.5 points better** than under English calibration.
  - Only English language modelling got slightly worse.

## 📈 Why the Asymmetry Happens
- Routing analysis of the last layers shows:
  - Lithuanian directs **55‑72 %** of its expert selections to just eight experts.
  - English directs only **19‑39 %** of its selections to the same number of experts.
- English calibration therefore removes some of the few experts critical for Lithuanian, causing a large performance drop.

## ✅ Takeaway
- Compressed models should be calibrated **and evaluated in every language they must serve** to avoid severe degradation in low‑resource or typologically different languages.


#MixtureOfExperts #ModelCompression #MultilingualAI

---

*Source: [English Calibration Erodes Lithuanian in Expert-Pruned Mixture-of-Experts Language Models](https://arxiv.org/abs/2611.07654v1)*
