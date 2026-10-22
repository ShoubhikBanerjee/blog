---
title: "Google DeepMind releases 10‑meter global Forest Typology map with yearly change data"
slug: "google-deepmind-releases-10meter-global-forest-typology-map-with-yearly-change-data"
description: "Google DeepMind and Google Research, together with the World Resources Institute and the International Institute for Applied Systems Analysis, have released Forest Typology (ForTy) 2020, a global..."
date: 2026-10-22T22:11:45+05:30
tags: [Forestry, RemoteSensing, AIMaps, Deforestation, EURegulation]
categories: ["AI", "Artificial Intelligence", "Remote Sensing", "Environmental Monitoring", "Geospatial Data"]
image: "https://lh3.googleusercontent.com/Et3g0tNB_bC00f6cP94Y40QbqshCvf7_fg_gRVfZQoeVSc3Hn9g6jIenf1udZdACY4x-wpY_5tyy_LznFSlu0yhGCqfxKos6QFRRj4lad_hQHOBV8Q=w1200-h630-n-nu-rw"
author: "Shoubhik Banerjee"
draft: false
---

# Google DeepMind releases 10‑meter global Forest Typology map with yearly change data

Google DeepMind and Google Research, together with the World Resources Institute and the International Institute for Applied Systems Analysis, have released Forest Typology (ForTy) 2020, a global 10‑meter resolution map that categorizes every land patch into six forest and land‑use types and provides an annual time series from 2017‑2025.

## 🔍 Overview
- 10‑meter resolution global map covering every 10 × 10 m pixel on Earth.
- Six distinct forest and land‑use categories based on FAO definitions.
- Early‑release time series tracks changes for each year from 2017 to 2025.
- Intended as a key baseline for the European Union’s deforestation‑free regulation.

## 🧩 How it works
- Trained on about **1.7 million** labeled locations compiled from expert surveys, national and regional datasets, and targeted reviews of difficult cases.
- Uses a custom architecture designed for remote‑sensing data.
- Primary input: **AlphaEarth Foundations embeddings**, compact summaries of years of satellite observations for each 10‑meter pixel, enabling detection of subtle cues such as planting patterns, growth cycles, and harvest rhythms.

## 📊 Classification scheme
| Category | Definition |
|---|---|
| Primary forest | Native forest with no visible signs of human disturbance. |
| Naturally regenerating forest | Forest that grew back on its own, e.g., after logging or fire. |
| Planted forest | Forest that people planted or seeded and manage over long cycles. |
| Plantation forest | Fast‑growing, intensively managed tree farms, often single‑species. |
| Tree crops and agroforestry | Farms growing non‑wood products such as oil palm, rubber, cocoa, or fruit. |
| Other land | All remaining land types, including grassland, cropland, cities, and water. |

## 📈 Performance
- Validated against **more than 9,000** randomly chosen sites worldwide.
- At each site, two trained experts examined high‑resolution imagery and satellite records to determine the true land type.
- Accuracy: **90 %** correct forest‑type classification; **95 %** correct forest vs. non‑forest distinction, outperforming other global forest maps.

## ⚙️ Output format
- Provides a **probability score** for each of the six classes rather than a simple yes/no label.
- Users can adjust thresholds to match their needs, e.g.:
  - Companies complying with the EU Deforestation‑Free Regulation may adopt a strict confidence threshold to avoid regulatory risk.
  - Researchers estimating total forest extent may use the full probability distribution for a more nuanced view.

## 🚀 Availability
- The early‑release time series for each year 2017‑2025 is publicly shared.
- Builds on the previously released **Natural Forests of the World 2020** map, which identified whether each pixel was natural forest in 2020.

## 💡 Why it matters
- For the first time, stakeholders can see at 10‑meter detail worldwide not only where forest loss occurs but **what replaces it** (timber plantation, tree‑crop farm, or other land).
- Supports EU regulations that require products like coffee, cocoa, palm oil, and wood to be free of recent forest conversion or degradation.
- Offers companies and researchers a high‑resolution, probabilistic tool to assess deforestation risk and monitor forest dynamics globally.

#Forestry #RemoteSensing #AIMaps #Deforestation #EURegulation

---

*Source: [Not All Forests Are Equal: Mapping the World’s Forests](https://deepmind.google/blog/beyond-tree-cover-mapping-the-worlds-forest-types/)*
