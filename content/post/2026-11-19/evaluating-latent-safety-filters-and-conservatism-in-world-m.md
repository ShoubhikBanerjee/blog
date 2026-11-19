---
title: "Evaluating Latent Safety Filters and Conservatism in World Models"
slug: "evaluating-latent-safety-filters-and-conservatism-in-world-models"
description: "A new approach uses a latent safety filter based on a world model's latent to decide whether a planned action is safe, utilizing conformal calibration to set thresholds."
date: 2026-11-19T18:06:46+05:30
tags: [ArtificialIntelligence, MachineLearning, WorldModels, SafetyFilters]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "AI Safety"]
author: "Shoubhik Banerjee"
draft: false
---

# Evaluating Latent Safety Filters and Conservatism in World Models

A new approach uses a latent safety filter based on a world model's latent to decide whether a planned action is safe, utilizing conformal calibration to set thresholds.

## 🧩 How it works

- A latent safety filter decides from the latent of a world model whether a planned action is safe.
- Conformal calibration sets the threshold of the filter so that it accepts an unsafe action only with a small probability.
- To measure conservatism, similar latents and actions are grouped into cells.
- A filter giving one decision per cell must refuse safe transitions in order to refuse unsafe ones within that cell, with this share of safe transitions called the overlap.
- Both the overlap and conformal calibration can be applied to any latent.

## ⚙️ Key details

- It is proven that the overlap is the minimum share of safe transitions that such a filter has to refuse in order to accept no unsafe transition in the data.
- The overlap and conformal calibration were used to compare three existing designs where safety labels train:
  - A classifier on top of the world model
  - The world model itself
  - A separate encoder beside it

| Design Variant | Performance in Visual Navigation |
| --- | --- |
| Separate encoder beside the world model | Lowest overlap, refuses the fewest safe actions at the same conformal level, and lets the planner reach the most goals among the three |

#ArtificialIntelligence #MachineLearning #WorldModels #SafetyFilters

---

*Source: [Measuring the Conservatism of Latent Safety Filters for World Models](https://arxiv.org/abs/2611.23685v1)*
