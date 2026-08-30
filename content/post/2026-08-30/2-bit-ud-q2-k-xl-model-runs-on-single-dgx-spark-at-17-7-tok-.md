---
title: "2-bit UD-Q2_K_XL Model Runs on Single DGX Spark at 17.7 tok/s"
description: "A 2‑bit neural network variant (UD‑Q2_K_XL, 109 GB) was tested on a single DGX Spark system. The model fit within the hardware's memory limits and achieved a processing speed of 17.7 tokens per..."
date: 2026-08-30T22:18:59+05:30
tags: [AI, Quantization, DGX, LowBit, ModelPerformance]
categories: [AI]
image: "https://devio2024-media.developers.io/image/upload/v1788061840/user-gen-eyecatch/ftmnqrlujplttchac2ut.png"
author: "Shoubhik Banerjee"
draft: false
---

# 2-bit UD-Q2_K_XL Model Runs on Single DGX Spark at 17.7 tok/s

A 2‑bit neural network variant (UD‑Q2_K_XL, 109 GB) was tested on a single DGX Spark system. The model fit within the hardware's memory limits and achieved a processing speed of 17.7 tokens per second when run with a generation context size of C=1.

All functional checks reported perfect scores: code fixes received a rating of 5 out of 5, code generation also scored 5 out of 5, and the model produced complete answers on every one of 49 test cases, indicating practical performance despite the low‑bit precision. When the model was explicitly set to a low‑precision mode, it completed the same tasks in 98 seconds and showed no degradation in scoring metrics.

These results demonstrate that a 2‑bit configuration can operate within a single DGX Spark appliance while maintaining full test‑suite accuracy and reasonable throughput.

![figure](https://devio2024-media.developers.io/image/upload/f_auto,q_auto,w_3840/v1788061840/user-gen-eyecatch/ftmnqrlujplttchac2ut.png)

![figure](https://devio2024-media.developers.io/image/upload/v1786675895/2026/08/14/um005gzjfbr0tjc06apv.png)

#AI #Quantization #DGX #LowBit #ModelPerformance

---

*Source: [I tried running the 320B GLM-5.3-Flash on a single DGX Spark to measure the dividing line of practical usability | DevelopersIO](https://dev.classmethod.jp/articles/dgx-spark-glm-5-3-flash-first-touch/)*
