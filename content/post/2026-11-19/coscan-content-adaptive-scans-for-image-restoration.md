---
title: "CoScan: Content-Adaptive Scans for Image Restoration"
slug: "coscan-content-adaptive-scans-for-image-restoration"
description: "A new method titled CoScan has been submitted to arXiv on November 18, 2026. The research focuses on improving image restoration by addressing the linearization of 2D feature maps for causal..."
date: 2026-11-19T18:06:46+05:30
tags: [C, o, m, p, u, t, e, r, V, i, s, i, o, n, I, m, a, g, e, R, e, s, t, o, r, a, t, i, o, n, S, t, a, t, e, S, p, a, c, e, M, o, d, e, l, s, M, a, m, b, a, C, o, m, p, u, t, e, r, S, c, i, e, n, c, e]
categories: ["AI", "C", "o", "m", "p", "u", "t", "e", "r", "V", "i", "s", "i", "o", "n", ",", "M", "a", "c", "h", "i", "n", "e", "L", "e", "a", "r", "n", "i", "n", "g", ",", "P", "a", "t", "t", "e", "r", "n", "R", "e", "c", "o", "g", "n", "i", "t", "i", "o", "n", ",", "A", "r", "t", "i", "f", "i", "c", "i", "a", "l", "I", "n", "t", "e", "l", "l", "i", "g", "e", "n", "c", "e"]
author: "Shoubhik Banerjee"
draft: false
---

# CoScan: Content-Adaptive Scans for Image Restoration

A new method titled CoScan has been submitted to arXiv on November 18, 2026. The research focuses on improving image restoration by addressing the linearization of 2D feature maps for causal state-space models (SSMs). CoScan introduces a content-adaptive scan-order design to mitigate the sensitivity of restoration performance to scan order.

## 🔍 Overview
Selective state-space models (SSMs) have shown potential for efficient image restoration. However, a central difficulty is that 2D feature maps typically need to be linearized into a 1D token sequence for causal state-space updates. Existing deterministic scans follow space-filling principles but remain fixed and content-agnostic. This can yield fragmented or semantically inconsistent contexts under degradations.

## 🧩 How it works
CoScan proposes a content-adaptive scan-order design for causal vision SSMs. The method learns image-dependent space-filling traversals through differentiable proxy supervision driven by scan-quality objectives. These objectives encourage short-range coherence and causal predictability while preserving spatial adjacency.

To support hierarchical restoration backbones, the method introduces an efficient multi-scale scan construction. This is achieved by coarsening a fine-level minimum spanning tree, producing coherent scans across feature resolutions. Additionally, a frequency-guided start selection strategy is designed to place informative structures early in the sequence prefix to strengthen causal context formation.

## ⚙️ Key details
*   **Integration:** Plugged into existing Mamba-based backbones.
*   **Performance:** Yields consistent improvements across several restoration benchmarks.
*   **Overhead:** Minimal overhead is required.
*   **Scope:** Shows promising results on high-level vision tasks.

## 🚀 Availability
Code for the project will be released at the provided URL.

| Tool | Description |
| :--- | :--- |
| Connected Papers | Visualizes related research papers.
| Litmaps | Maps the literature landscape.
| scite Smart Citations | Provides context for citations.
| alphaXiv | Preprint server for AI research.
| CatalyzeX Code Finder | Finds code associated with papers.
| DagsHub | Platform for data and ML projects.
| Hugging Face | Repository for machine learning models.
| ScienceCast | Visualizes research papers.
| arXivLabs | Framework for experimental arXiv features.

#C #o #m #p #u #t #e #r #V #i #s #i #o #n #, # #I #m #a #g #e #R #e #s #t #o #r #a #t #i #o #n #, # #S #t #a #t #e #S #p #a #c #e #M #o #d #e #l #s #, # #M #a #m #b #a #, # #C #o #m #p #u #t #e #r #S #c #i #e #n #c #e

---

*Source: [CoScan: Multi-Scale Content-Adaptive Space-Filling Scans for Causal State-Space Image Restoration](https://arxiv.org/abs/2611.23717v1)*
