---
title: "OlmoEarth v1.3 releases global 10‑m satellite embeddings and explorer"
slug: "olmoearth-v1-3-releases-global-10m-satellite-embeddings-and-explorer"
description: "Today the team released OlmoEarth v1.3, a state‑of‑the‑art satellite embedding model that generates a 128‑dimensional vector for every 10‑meter pixel on Earth and ships with pre‑computed global..."
date: 2026-10-22T22:11:45+05:30
tags: [Satellites, Embeddings, OpenSource, GeospatialAI]
categories: ["AI", "Machine Learning", "Remote Sensing", "Geospatial Analytics", "Artificial Intelligence"]
image: "https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/VEmSzlLjei8J3cUVNe7G6.png"
author: "Shoubhik Banerjee"
draft: false
---

# OlmoEarth v1.3 releases global 10‑m satellite embeddings and explorer

Today the team released OlmoEarth v1.3, a state‑of‑the‑art satellite embedding model that generates a 128‑dimensional vector for every 10‑meter pixel on Earth and ships with pre‑computed global embeddings and a browser‑based explorer.

## 🚀 Release
- OlmoEarth v1.3 reads a full year of Sentinel‑1 radar and Sentinel‑2/Landsat multispectral time series.
- It outputs a 128‑dimensional vector per pixel; the first 64 dimensions can be used independently.
- Pre‑computed annual embeddings are provided for the entire planet at 10 m resolution in both 64‑ and 128‑dimensional forms.
- The OlmoEarth Embeddings Explorer lets anyone pan, flip years, and compare vectors without signing in or advanced technical knowledge.

## 🧩 How it works
- A vision transformer ingests the satellite data.
- An Attention Pooler aggregates the data into one vector per land patch.
- A linear layer reduces the pooled representation to 128 numbers.

## 📊 Evaluation & Performance
| Variant | Dimensions | Leads on evals (out of 27) |
|---------|------------|----------------------------|
| OlmoEarth v1.3 (full) | 128 | 20 |
| OlmoEarth v1.3 (half) | 64 | 18 |
- The 128‑dimensional embeddings scored highest on 20 of 27 evaluations and ranked highest overall against AlphaEarth Foundations (AEF) and Tessera v2.
- The 64‑dimensional version still led on 18 of 27 evaluations.
- A new PLANTEUR crop‑type benchmark for tropical farming was introduced; OlmoEarth embeddings generalized best to unseen locations.

## ⚙️ Key details
- Training cost: roughly $2,720 of rented H100 GPU time for the final run.
- Compared to v1.2, training time dropped to 53% and carbon emissions to 50%; compared to v1, time dropped to 18% and emissions to 22%.
- Model weights, pre‑training data, and code are fully open on Source Cooperative.

## 📈 Availability & Tools
- The pre‑computed embeddings are shared publicly; users can train a small classifier locally for tasks such as:
  - Smallholder‑crop classification in Kenya
  - Brick‑kiln detection west of Dhaka
  - Fire‑damage assessment in Indonesia
  - Gold‑mining monitoring in the Peruvian Amazon
- The Embeddings Explorer renders the embeddings as a false‑color map, allows year‑to‑year comparison, and lets users click a location to find similar places or drop labeled points to train a classifier on the fly.

## 💡 Why it matters
- Global embeddings turn heavyweight satellite analysis into lightweight, locally‑run models.
- In Peru’s Madre de Dios region, the embeddings highlighted illegal gold‑mining expansion from 2017‑2020 and subsequent shifts through 2025, matching on‑the‑ground reports from MAAP and the Associated Press.
- By lowering compute and expertise barriers, the release aims to democratize high‑resolution Earth observation for research, NGOs, and industry.


![figure](https://www.datocms-assets.com/64837/1792611867-olmoearth-v1-3-globe.png)

![figure](https://www.datocms-assets.com/64837/1792611867-olmoearth-v1-3-architecture.png)

![figure](https://www.datocms-assets.com/64837/1792611867-olmoearth-v1-3-training-cost.png)

#Satellites #Embeddings #OpenSource #GeospatialAI

---

*Source: [OlmoEarth v1.3: State-of-the-art embeddings for the whole planet](https://huggingface.co/blog/allenai/olmoearth-v1-3)*
