---
title: "NVIDIA Releases Kumo Forecast for Multi-Variate Time-Series Forecasting"
slug: "nvidia-releases-kumo-forecast-for-multi-variate-time-series-forecasting"
description: "NVIDIA has introduced Kumo Forecast (formerly known as NV-Tesseract Forecasting), a multi-variate time-series forecasting model that integrates a pretrained Transformer backbone with a..."
date: 2026-10-21T22:03:49+05:30
tags: [NVIDIA, TimeSeries, Forecasting, MachineLearning, Transformer]
categories: ["AI", "Machine Learning", "Predictive Analytics", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/660f5683b710b57b115a5483/pFl0vhvFrc-oZjk5qE8_0.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Kumo Forecast for Multi-Variate Time-Series Forecasting

NVIDIA has introduced Kumo Forecast (formerly known as NV-Tesseract Forecasting), a multi-variate time-series forecasting model that integrates a pretrained Transformer backbone with a context-enhanced retrieval mode.

## 🧩 How it works
Kumo-Forecast combines four main components to generate predictions by drawing on representations learned during pretraining and historical observations available for the current application:

| Component | Function |
| :--- | :--- |
| Pretrained Temporal Encoder | Uses the MOMENT-1-large Transformer encoder as the backbone. |
| Trainable Forecasting Head | Maps representations to future values for the requested horizon. |
| Historical-Pattern Retrieval | Uses a nearest-neighbor approach to retrieve related patterns from historical data. |
| Interpretability Framework | Produces model-agnostic explanations without modifying the forecaster. |

## ⚙️ Key details
* **Architecture:** The model uses a MOMENT-1-large backbone consisting of an approximately 340-million-parameter base encoder. During training of the forecasting head, the encoder and embedder weights remain frozen.
* **Forecasting Modes:** 
    * **Direct Forecasting:** Uses the MOMENT-based Transformer and forecasting head to predict future values, with support for autoregressive extension for horizons beyond native capability.
    * **Domain-Aware Representation and Retrieval (DARR):** Augments direct forecasts by retrieving patterns from a separate historical DataFrame (`context_df`). Developers can configure the strength of reliance on each pathway.
* **Input Specifications:** Supports input sequence lengths of 256, 512, 1024, and 2048 observations. Inputs must include a timestamp column and one or more numeric value columns via CSV, JSON, or pandas DataFrame.
* **Interpretability:** When enabled, the framework provides an explanation bundle including trajectory-stability diagnostics, semantic-flow diagnostics, lag and feature attributions per horizon, and optional embedding Integrated Gradients.

## 🚀 Availability
* **License:** Available under the Apache 2.0 license.
* **API:** Provides a DataFrame-first API with configurable forecast horizons.
* **Integration:** The Predictive Maintenance module within the Factory Operations (FOX) Blueprint leverages Kumo Forecast and Kumo Anomaly to predict future anomalies from real-time data.
* **Developer Resources:** The Kumo-TS repository includes examples for fine-tuning the model on user-supplied CSVs, supporting both pretrained inference and adaptation workflows.

![figure](https://huggingface.co/nvidia/Kumo-Forecast/resolve/main/images/image-gtc-2026.png)

#NVIDIA #TimeSeries #Forecasting #MachineLearning #Transformer

---

*Source: [NVIDIA Kumo Forecast Combines Pretrained Time-Series Representations with Historical Pattern Retrieval and Interpretability](https://huggingface.co/blog/nvidia/kumo-forecast)*
