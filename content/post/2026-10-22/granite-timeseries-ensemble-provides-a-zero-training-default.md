---
title: "Granite Timeseries Ensemble provides a zero‑training default forecast recipe"
slug: "granite-timeseries-ensemble-provides-a-zerotraining-default-forecast-recipe"
description: "Granite Timeseries Ensemble (Granite TSFM) introduces a default, zero‑training forecast recipe that combines four pre‑trained models."
date: 2026-10-22T22:11:45+05:30
tags: [TimeSeries, Forecasting, Ensemble, Granite]
categories: ["AI", "Machine Learning", "Time Series Forecasting", "AI Tools", "Open Source"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6806091ee92bd22fd8ce9719/P6P8ZzHR8yL7GOOO4hQOg.png"
author: "Shoubhik Banerjee"
draft: false
---

# Granite Timeseries Ensemble provides a zero‑training default forecast recipe

Granite Timeseries Ensemble (Granite TSFM) introduces a default, zero‑training forecast recipe that combines four pre‑trained models.

## 🔍 Overview
- Pre‑trained time‑series models can forecast without training on your dataset, but you still have to choose one.
- Granite Timeseries Ensemble reduces that choice to a sensible default.
- The default recipe combines four pre‑trained Granite models with different architectures, each capturing trends, seasonality, and local variation in different ways.

## 🧩 How it works
- Two main ensemble recipes are provided:
  - **Probabilistic Ensemble** (uniform probability pooling)
  - **IQR Ensemble** (weights based on forecast spread)
- Both recipes work with each member’s quantile forecasts (default 0.1 – 0.9) and produce a median and quantile forecasts.
- **Probabilistic Ensemble** gives each member equal influence, pools quantile forecasts in probability space, and extracts the requested quantiles. No fitting step and no weighting hyperparameters are required.
- **IQR Ensemble** approximates each member’s inter‑quartile range from the nearest 25th and 75th percentiles, then weights members inversely to their interval width. Weights vary by sample, target, and horizon step; isotonic regression keeps combined quantiles from crossing. A temperature setting and optional cap let users move weights toward uniform or limit any single member’s influence.

## ⚙️ Key details
- Each member returns:
  - `result.prediction_outputs` – the point forecast.
  - `result.quantile_outputs` – quantile predictions ranging from 0.1 to 0.9.
- The 0.1 and 0.9 quantiles define a central forecast interval with nominal 80 % coverage.
- No retraining and no fitted ensemble weights; simple equal‑weight combinations have historically performed well in point forecasting.
- The ensemble recipe stores the configuration rather than merged model weights; member checkpoints are downloaded at runtime, so allow extra time for the first run.
- The recipe and its default Granite members are permissively licensed.
- Both recipes were evaluated on 97 GIFT‑Eval dataset configurations (see the model card for full details, member checkpoints, evaluation, and limitations).

## 🚀 Availability
- Install the package with:
  ```
  pip install "granite-tsfm>=0.3.11"
  ```
- Load the recommended four‑model recipe directly from Hugging Face.
- The model card provides the full configuration, member checkpoints, evaluation details, and known limitations.

## 💡 Why it matters
- Provides a ready‑to‑use, zero‑training forecast solution for a wide range of series, from smooth industrial signals to noisy retail demand.
- Reduces the risk of selecting a poor single model by combining diverse architectures; a 50‑year review of forecast combinations notes that such ensembles can lower error risk when members are high‑quality and diverse.
- Enables applications to use the median as a central prediction and selected quantiles to express forecast uncertainty without any hyperparameter tuning.

![figure](https://huggingface.co/buckets/rry003/blogcomponents/resolve/gift_eval_ranks_granite.png?download=true)

#TimeSeries #Forecasting #Ensemble #Granite

---

*Source: [Ensemble forecasting with IBM Granite time-series models](https://huggingface.co/blog/ibm-research/granite-timeseries-ensemble-r1)*
