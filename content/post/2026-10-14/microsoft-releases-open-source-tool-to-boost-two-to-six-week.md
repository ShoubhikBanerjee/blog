---
title: "Microsoft releases open-source tool to boost two-to-six-week weather forecasts"
slug: "microsoft-releases-open-source-tool-to-boost-two-to-six-week-weather-forecasts"
description: "Microsoft Research has unveiled a new machine‑learning tool that corrects systematic bias in existing weather models, extending reliable forecasts out to two‑to‑six weeks."
date: 2026-10-14T22:09:38+05:30
tags: [WeatherForecasting, MachineLearning, OpenSource, ClimateAI]
categories: ["AI", "Machine Learning", "Weather Forecasting", "Climate Science", "Open Source Software"]
image: "https://platform.theverge.com/wp-content/uploads/sites/2/2025/02/STK438_CLIMATE_CHANGE_G.jpg?quality=90&strip=all&crop=0%2C10.732984293194%2C100%2C78.534031413613&w=1200"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft releases open-source tool to boost two-to-six-week weather forecasts

Microsoft Research has unveiled a new machine‑learning tool that corrects systematic bias in existing weather models, extending reliable forecasts out to two‑to‑six weeks.

## 🔍 Overview
- Old‑school physics‑based forecasting and current AI models lose reliability beyond two weeks, a problem Microsoft says it has solved with machine learning.
- The tool, called Probabilistic Bias Correction (PBC), is now open‑source software and its findings were published today in *Nature*.
- Microsoft joins Google, Nvidia and other firms developing AI tools for weather forecasting.

## 🧩 How it works
- PBC uses machine learning to identify systematic bias in a model and make corrections, rather than building a new standalone weather model.
- It can run on standard CPUs, avoiding the supercomputer or GPU clusters required by traditional physics‑based or generative‑AI forecasts.
- Example bias: climate‑change‑induced warming can cause a model that relies on historic records to predict temperatures that are too cold.

## 📊 Performance
- Improves the accuracy of the European Centre for Medium‑Range Weather Forecasts (ECMWF) physics‑based model for **98 % of precipitation** targets and **92 % of temperature** targets.
- Doubles the accuracy of ECMWF’s new AI forecasting system in the study’s analysis.

| Model corrected by PBC | Reported improvement |
|--------------------------|-----------------------|
| ECMWF physics‑based model (precipitation) | 98 % of targets more accurate |
| ECMWF physics‑based model (temperature) | 92 % of targets more accurate |
| ECMWF AI forecasting system | Accuracy doubled |

## 🌍 Accessibility & Impact
- Designed as a lightweight, easy‑to‑train approach that resource‑strained weather agencies can adopt.
- Runs on CPUs, lowering compute and infrastructure barriers that often exclude agencies in economically developing countries.
- Aims to give farmers, emergency responders and other stakeholders more certain forecasts for planning.
- Genevieve Flaspohler notes the method lets scientists without huge pools of resources configure models for specific localities.
- Flaspohler’s nonprofit Rhiza Research is testing PBC with the Kenya Meteorological Service Authority, funded by the Gates Foundation, ahead of an expected extreme rainy season during a record‑breaking El Niño.

## 🚀 Availability
- The software is released as open‑source, allowing the broader community to adopt the bias‑correction technique.
- The research team includes scientists from Microsoft, MIT, ECMWF and other institutions.
- ECMWF previously recognized the work by awarding it in its AI Weather Quest competition.
- Matthew Chantry of ECMWF called the paper “a good example of new ideas being developed for the benefit and consideration of the community,” while noting the challenge of turning ideas into operational processes.

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2025/02/STK438_CLIMATE_CHANGE_G.jpg?quality=90&strip=all&crop=0%2C0%2C100%2C100&w=2400)

![figure](https://platform.theverge.com/wp-content/uploads/sites/2/2026/10/gettyimages-2299992780.jpg?quality=90&strip=all&crop=0%2C0%2C100%2C100&w=2400)

#WeatherForecasting #MachineLearning #OpenSource #ClimateAI

---

*Source: [Microsoft has a new machine learning tool to improve weather forecasts](https://www.theverge.com/science/1011127/ai-weather-forecast-microsoft)*
