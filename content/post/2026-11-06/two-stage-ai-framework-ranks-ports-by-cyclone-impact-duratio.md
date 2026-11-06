---
title: "Two‑stage AI framework ranks ports by cyclone impact duration"
slug: "twostage-ai-framework-ranks-ports-by-cyclone-impact-duration"
description: "A new AI‑driven two‑stage recommendation framework was evaluated on Gulf of Mexico ports to anticipate which ports will be most affected by an approaching tropical cyclone and how long disruptions..."
date: 2026-11-06T22:02:31+05:30
tags: [tropicalcyclones, portlogistics, machinelearning]
categories: ["AI", "Machine Learning", "Disaster Management", "Transportation"]
author: "Shoubhik Banerjee"
draft: false
---

# Two‑stage AI framework ranks ports by cyclone impact duration

A new AI‑driven two‑stage recommendation framework was evaluated on Gulf of Mexico ports to anticipate which ports will be most affected by an approaching tropical cyclone and how long disruptions may last.

## 🔍 Overview
- Port preparedness relies on predicting affected ports and the length of disruption.
- Historical data at individual ports are limited, and landfall location is uncertain, making impact estimation challenging.

## 🛠️ How it works
- **Stage 1 – Retrieval**: Select candidate ports that are closest to the expected cyclone landfall.
- **Stage 2 – Ranking**: Order the selected ports by the estimated number of impact days.
- The framework was tested on Hurricanes Nicole and Ian, and the retrieval stage consistently identified all observed affected ports despite landfall uncertainty.

## 📊 Model comparison
Three ways of representing port–cyclone interactions were compared using AIS‑derived impact days for 37 ports and 31 cyclones:
- Pairwise feature interactions
- Tree‑based feature combinations
- Explicit feature crosses combined with learned embeddings

Among the ranking models, **Wide & Deep Learning** achieved the closest agreement with observed port rankings. Its mean ranking agreement:
- Exceeds the distance‑based baseline by **85.5 %** for Hurricane Nicole
- Exceeds the baseline by **55.5 %** for Hurricane Ian
- Shows lower sensitivity to landfall location uncertainty.

| Model                    | Representation used                                         | Improvement over distance baseline |
|--------------------------|------------------------------------------------------------|-----------------------------------|
| Distance‑based baseline  | Simple proximity to landfall                               | —                                 |
| Wide & Deep Learning     | Explicit feature crosses + learned embeddings (deep part) | +85.5 % (Nicole), +55.5 % (Ian) |

## 📈 Why it matters
- Provides port authorities with prioritized lists for post‑cyclone inspections.
- Helps allocate recovery resources efficiently across ports threatened by the same event.
- Reduces reliance on sparse historical observations by leveraging AI‑based impact day estimates.

#tropicalcyclones #portlogistics #machinelearning

---

*Source: [Robust Ranking of Port Impacts from Impending Tropical Cyclones: A Two-Stage Recommendation System](https://arxiv.org/abs/2611.07296v1)*
