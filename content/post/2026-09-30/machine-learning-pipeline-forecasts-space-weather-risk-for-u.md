---
title: "Machine Learning Pipeline Forecasts Space-Weather Risk for US Power Substations"
slug: "machine-learning-pipeline-forecasts-space-weather-risk-for-us-power-substations"
description: "A new machine learning system has been developed to generate location-specific space-weather risk estimates for 66,935 substations across the continental United States, providing grid operators with..."
date: 2026-09-30T22:03:54+05:30
tags: [MachineLearning, SpaceWeather, PowerGrid, AIAgents, GIC]
categories: ["AI", "Machine Learning", "Infrastructure", "Environmental Forecasting"]
image: "https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/ForecastingSpace-TWLIFB-1200x627-1.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Machine Learning Pipeline Forecasts Space-Weather Risk for US Power Substations

A new machine learning system has been developed to generate location-specific space-weather risk estimates for 66,935 substations across the continental United States, providing grid operators with warnings 30 to 60 minutes before potential impacts appear.

## 🧩 How it works
The pipeline operates through a three-step process:

1. **Data Collection and Forecasting**: Solar-wind measurements from the L1 Lagrange point are used to forecast Auroral Electrojet (AE) and Disturbance Storm Time (Dst) indices. Simultaneously, location features and geological conductivity are assembled for each substation.
2. **Risk Estimation**: A gradient-boosting model combines these forecasted indices and location-specific inputs to estimate dB/dt, which is the rate of magnetic-field change associated with geomagnetically induced current (GIC) risk.
3. **Aggregation**: Predictions are converted into location-specific risk estimates and then aggregated into a continental risk assessment.

## ⚙️ Key details
The system utilizes several data sources and model configurations:

* **Data Sources**: The system uses public data including NASA OMNI, NASA-aggregated Kyoto World Data Center data, INTERMAGNET and U.S. Geological Survey magnetometer observations, and GridSFM-derived grid data.
* **Model Inputs**: The pipeline combines solar-wind observations, AE and Dst index forecasts, physics-informed constraints, grid-infrastructure data, and local geological conductivity.
* **Geological Factors**: The system accounts for the fact that regions with resistive bedrock can experience stronger GICs than regions with more conductive geology.
* **Development**: A system of 50 AI agents helped explore model configurations, validation strategies, and features across the pipeline.

## 📊 Performance
During a 2020-2026 evaluation period, the system detected nearly 80% of major space-weather events. Performance varied by latitude, with the highest detection rates occurring at northern stations.

| Metric | Result/Detail |
| :--- | :--- |
| Major Event Detection (≥10 nT/min) | 76.5% |
| Severe Event Detection (≥20 nT/min) | 81.2% |
| Extreme Event Detection (≥50 nT/min) | 64.1% |
| AE Predictor RMSE | 410.2 nT (Lower than empirical and solar-wind-only baselines) |
| Dst Predictor RMSE | 7.2 nT |

The Dst predictor outperformed the Burton equation on 62.2% of individual hours during the most geomagnetically active periods and improved severe-event detection by 1.2 percentage points when combined with AE forecasts.

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/GIC-Forecast-Flowchart-scaled.png)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/Continent-GIC-Risk-Assessment-Demo-High-Res-scaled.jpg)

![figure](https://www.microsoft.com/en-us/research/wp-content/uploads/2026/09/Station-by-Station-Performance-scaled.png)

#MachineLearning #SpaceWeather #PowerGrid #AIAgents #GIC

---

*Source: [Forecasting space weather risks on power grids](https://www.microsoft.com/en-us/research/blog/forecasting-space-weather-risks-on-power-grids/)*
