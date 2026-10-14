---
title: "HiRO-ACEv2 Enables Low‑Cost Global 3 km Climate Simulations with Improved Extreme‑Event Modeling"
slug: "hiro-acev2-enables-lowcost-global-3-km-climate-simulations-with-improved-extremeevent-modeling"
description: "We introduce HiRO-ACEv2, the newest update to the High Resolution Output AI Climate Emulator (HiRO-ACE) system. The update focuses on accurately reproducing extreme rain, wind, and pressure events..."
date: 2026-10-14T22:09:38+05:30
tags: [AIClimate, HighResolution, ExtremeEvents, ClimateModeling]
categories: ["AI", "Artificial Intelligence", "Climate Science", "Machine Learning", "Environmental Modeling"]
image: "https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/VxZSVqDUz8eoV89Ekpn0U.png"
author: "Shoubhik Banerjee"
draft: false
---

# HiRO-ACEv2 Enables Low‑Cost Global 3 km Climate Simulations with Improved Extreme‑Event Modeling

## 🔍 Overview
We introduce HiRO-ACEv2, the newest update to the High Resolution Output AI Climate Emulator (HiRO-ACE) system. The update focuses on accurately reproducing extreme rain, wind, and pressure events while delivering global 3 km climate data at a fraction of the cost of traditional high‑resolution models.

## 🧩 How it works
- **HiRO‑ACE (2026)** – Consists of two components:
  - **ACE** – An AI model that runs at a coarse 100 km resolution.
  - **HiRO** – A downscaling model that sharpens ACE’s output to 3 km detail.
- **HiRO‑ACEv2** – Replaces the original downscaler with **HiROv2**, which:
  - Predicts several high‑resolution fields simultaneously (rainfall, wind, pressure, etc.) instead of only rainfall.
  - Shows improved skill in predicting the most intense rain, wind, and pressure values.
  - Matches target high‑resolution statistics to within **3 %** even for events that occur only once in a million data points.
- The system is trained on coarsened data from the X‑SHiELD global atmospheric model and inherits its ability to simulate storms and other small‑scale weather.

## ⚙️ Key details
- **Extreme‑event performance**:
  - Accurately estimates total energy of tropical cyclones, including storms never seen during training.
  - Generates hurricanes with realistic eyes and rain bands (winds and pressure around the eye are somewhat more lopsided than X‑SHiELD).
  - Realistically produces strong downslope winds on mountain slopes.
- **Cost and speed**:
  - Generates global 3 km data at about **1/300th** the cost of X‑SHiELD (≈ 300 times cheaper).
  - For a single region, savings can exceed **100 times**, depending on area size.
  - A streamlined HiROv2 version under development could be **more than ten times faster**.
- **Long‑term simulations**:
  - A full year of global 3 km data was produced by combining HiROv2 with the updated ACE.
  - Over a 10‑year run, hurricane energy and the distributions of rain, wind, and pressure closely match X‑SHiELD.
  - Average climate patterns and overall statistics remain well aligned with X‑SHiELD.
- **Training updates**:
  - Both ACE and HiROv2 were retrained; the new training regime improves reproduction of the most intense events.
  - Current version works only with the ACE tuned to match X‑SHiELD and cannot yet generate high‑resolution data for other climate states.

## 🚀 Availability
- The models are downloadable, and tutorial notebooks are provided to guide users through running them.
- A web demo showcases pre‑generated precipitation, wind, and sea‑level pressure from HiROv1, HiROv2, and X‑SHiELD side‑by‑side, allowing users to zoom in on regions of interest.

## 💡 Why it matters
HiRO‑ACEv2 offers researchers a flexible, inexpensive way to create many versions of high‑resolution climate fields—including extreme events—over multi‑year periods. The dramatic cost reduction and the ability to simulate rare, intense weather phenomena open new possibilities for climate research, impact assessments, and risk modeling.


![figure](https://www.datocms-assets.com/64837/1791928654-hiro-acev2-blog-draft-google-docs-image-2.png?fit=max&h=810&w=1550)

![figure](https://www.datocms-assets.com/64837/1791928757-hiro-acev2-blog-draft-google-docs-image-3.png?fit=max&h=810&w=1550)

![figure](https://www.datocms-assets.com/64837/1791928822-hiro-acev2-blog-draft-google-docs-image-4.png?fit=max&h=810&w=1550)

#AIClimate #HighResolution #ExtremeEvents #ClimateModeling

---

*Source: [HiRO-ACEv2: Simulating extreme weather at 3 km resolution for a fraction of the cost](https://huggingface.co/blog/allenai/hiro-acev2)*
