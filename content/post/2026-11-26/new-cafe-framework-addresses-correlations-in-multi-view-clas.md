---
title: "New CAFE Framework Addresses Correlations in Multi-View Classification"
slug: "new-cafe-framework-addresses-correlations-in-multi-view-classification"
description: "Trusted multi-view classification aims to make accurate and reliable predictions by integrating information from multiple views. Existing methods typically estimate class evidence and uncertainty for..."
date: 2026-11-26T12:19:42+05:30
tags: [multiviewclassification, AIframeworks, correlationawarefusion, trustedAI, evidencefusion, calibration]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Data Fusion", "Uncertainty Estimation"]
author: "Shoubhik Banerjee"
draft: false
---

# New CAFE Framework Addresses Correlations in Multi-View Classification

Trusted multi-view classification aims to make accurate and reliable predictions by integrating information from multiple views. Existing methods typically estimate class evidence and uncertainty for each view and combine the resulting opinions through aggregation rules. However, they generally treat different views as independent information sources, overlooking the correlations among them. Highly correlated views tend to produce similar evidence, and treating them as independent sources may repeatedly count consistent information and give it disproportionate influence, while weakening complementary evidence that provides additional information. Consequently, such correlation-unaware fusion may not only limit classification performance but also produce miscalibrated uncertainty estimates. To address this issue, we propose Correlation-Aware Fusion of Evidence (CAFE), a framework for trusted multi-view classification. CAFE applies complementarity-based trust discounting to the evidence produced by view-private experts and introduces a correlation-aware constraint to reduce the repeated contribution of similar evidence. It then learns sample-specific weights from the global multi-view context to adaptively combine the correlation-adjusted private evidence with cross-view collaborative evidence. Extensive experiments on six real-world datasets demonstrate that CAFE consistently improves classification and calibration performance in general settings, with particularly significant gains when strong correlations exist among views.

## 🔍 Overview

Trusted multi-view classification aims to make accurate and reliable predictions by integrating information from multiple views.

#multi-viewclassification #AIframeworks #correlation-awarefusion #trustedAI #evidencefusion #calibration

---

*Source: [Correlation-Aware Evidential Fusion for Trusted Multi-View Classification](https://arxiv.org/abs/2611.33900v1)*
