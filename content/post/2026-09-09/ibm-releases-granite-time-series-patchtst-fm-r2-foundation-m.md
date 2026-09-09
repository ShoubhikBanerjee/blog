---
title: "IBM Releases Granite Time Series PatchTST-FM-r2 Foundation Model"
slug: "ibm-releases-granite-time-series-patchtst-fm-r2-foundation-model"
description: "IBM has released Granite Time Series PatchTST-FM-r2, the latest iteration in the Granite TSFM family. This model enables users to perform zero-shot forecasting across diverse datasets, such as..."
date: 2026-09-09T22:05:26+05:30
tags: [IBM, TimeSeries, MachineLearning, OpenSource, Forecasting]
categories: ["AI", "Machine Learning", "Artificial Intelligence", "Data Science"]
image: "https://cdn-uploads.huggingface.co/production/uploads/69d3d41eef229c09afea5d83/KYse3pX6t3l8FnI-1pKsi.png"
author: "Shoubhik Banerjee"
draft: false
---

# IBM Releases Granite Time Series PatchTST-FM-r2 Foundation Model

IBM has released Granite Time Series PatchTST-FM-r2, the latest iteration in the Granite TSFM family. This model enables users to perform zero-shot forecasting across diverse datasets, such as demand, prices, energy loads, and telemetry, without the need to train or maintain separate models for every dataset.

## 🔍 Overview
As of September 8, 2026, PatchTST-FM-r2 is the top-performing model in the replicable, zero-shot category among those released under a permissive, commercial-friendly open-source license (Apache 2.0 and OpenMDW 1.0). It ranks second overall in the zero-shot, replicable category of the GIFT-Eval benchmark, trailing only TimesFM-3.

## 🧩 How it works
PatchTST-FM-r2 utilizes a redesigned architecture that replaces standard transformer layers with conformer blocks. These blocks combine multi-head self-attention with temporal convolution to capture both long- and short-range temporal structures. This design allows the model to model long-range relationships between patches while using convolution to provide an inductive bias toward local temporal structure.

## ⚙️ Key details
* Parameters: Approximately 385M.
* Context Length: Up to 8,192 tokens.
* Forecasting: Supports probabilistic forecasting via a 99-quantile prediction head.
* Capabilities: Includes support for imputation of missing values.
* Benchmarking: Achieves a geometric-mean CRPS of 0.467 and a geometric-mean MASE of 0.6846.

## 🚀 Availability
The model weights, architecture, inference pipeline, and code required to reproduce benchmark results are publicly available. The model is dual-licensed under Apache-2.0 and OpenMDW-1.0, allowing users to select either license. The Granite Time Series family is also designed for integration into streaming production applications using Confluent.

![figure](https://cdn-uploads.huggingface.co/production/uploads/64b01b5252349201f972ba17/EHyv5DrZggfNQPIZzZ-Lk.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/64b01b5252349201f972ba17/5zG7qXwRtBp-ceZ_0UnAY.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/64b01b5252349201f972ba17/5nFJSV8NMdjQUGsRIKW2l.png)

#IBM #TimeSeries #MachineLearning #OpenSource #Forecasting

---

*Source: [IBM releases SOTA Granite Time Series PatchTST-FM-r2 model with commercial-friendly license](https://huggingface.co/blog/ibm-research/ibm-releases-sota-granite-time-series)*
