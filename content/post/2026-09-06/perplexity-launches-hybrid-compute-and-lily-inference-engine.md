---
title: "Perplexity Launches Hybrid Compute and Lily Inference Engine for Mac"
description: "Perplexity has introduced hybrid compute for its Mac app, allowing a single Perplexity Computer task to be split between cloud-based frontier models and a compact local model."
date: 2026-09-06T22:07:38+05:30
tags: [Perplexity, HybridCompute, LocalAI, AppleSilicon, OpenSource]
categories: [AI]
image: "https://www.marktechpost.com/wp-content/uploads/2019/06/Screen-Shot-2021-09-14-at-9.02.24-AM.png"
author: "Shoubhik Banerjee"
draft: false
---

# Perplexity Launches Hybrid Compute and Lily Inference Engine for Mac

Perplexity has introduced hybrid compute for its Mac app, allowing a single Perplexity Computer task to be split between cloud-based frontier models and a compact local model.

## 🧩 How it works
Tasks begin in the cloud for reasoning, planning, and search. Sensitive steps are then handed down to the Mac without losing context or restarting. This process is managed by an on-device privacy gate that determines if data should be:
* Kept local
* Masked
* Refused
* Asked for consent

## ⚙️ Key details
Perplexity has open-sourced two components related to this development:

| Component | Description |
| :--- | :--- |
| 0.6B Classifier | The model behind the privacy gate, recording the highest character F1 (0.629) among twelve evaluated detectors. |
| Lily | A local inference engine built in Rust with custom Metal kernels for one model on one chip family. |

On a 40-core, 128 GB M5 Max, Lily averages 1.35x the decode throughput and 1.23x the prefill throughput of MLX-LM.

## 🚀 Availability
Hybrid compute is currently live for the following users:
* Pro
* Max
* Enterprise

It requires Apple silicon Macs with 24GB of unified memory.

#Perplexity #HybridCompute #LocalAI #AppleSilicon #OpenSource

---

*Source: [Asif Razzaq](https://www.marktechpost.com/author/6flvq/)*
