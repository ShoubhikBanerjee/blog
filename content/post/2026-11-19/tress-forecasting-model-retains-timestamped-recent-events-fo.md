---
title: "TRESS forecasting model retains timestamped recent events for efficient predictions"
slug: "tress-forecasting-model-retains-timestamped-recent-events-for-efficient-predictions"
description: "A new forecasting model called TRESS (Timestamped Recent Events and Statistical Summaries) addresses the challenge that a fixed number of recent observations may span minutes for one variable and..."
date: 2026-11-19T12:23:35+05:30
tags: [Forecasting, MachineLearning, TimeSeries, DeepLearning, Efficiency]
categories: ["AI", "Time Series Analysis", "Forecasting", "Machine Learning", "Model Architecture"]
author: "Shoubhik Banerjee"
draft: false
---

# TRESS forecasting model retains timestamped recent events for efficient predictions

A new forecasting model called TRESS (Timestamped Recent Events and Statistical Summaries) addresses the challenge that a fixed number of recent observations may span minutes for one variable and days for another, while earlier measurements can still reveal whether the latest value is unusual for that variable.

## 🔍 Overview
The proposed model retains the latest observations at their original times and summarises the full history of each variable. For a given set of variables and event budget, this representation stays the same size as the record grows.

## 🧩 How it works
- A query-conditioned event lifting module weights deviations from the latest value according to the age of each observation and the forecast horizon.
- A channel-specific decoder combines the resulting features with historical statistics and a summary shared across variables to predict a correction to the latest value.

## ⚙️ Key details
- TRESS retains 8 to 16 observations per variable.
- On all four benchmarks compared, TRESS records the lowest mean test MSE and MAE among the methods tested.
- Serving 32 successive query times from one encoded history reduces CPU inference time by a factor of 2.12 to 2.60 across the four datasets.

## 🚀 Availability
The code for the model is available at the URL provided in the source material.

#Forecasting #MachineLearning #TimeSeries #DeepLearning #Efficiency

---

*Source: [TRESS: A Fixed-Size History Representation for Irregular Time Series Forecasting](https://arxiv.org/abs/2611.24257v1)*
