---
title: "FlashOffloading Boosts LLM Serving Throughput by Offloading KV Cache to Host DRAM"
slug: "flashoffloading-boosts-llm-serving-throughput-by-offloading-kv-cache-to-host-dram"
description: "FlashOffloading is a new host‑DRAM‑centric inference architecture that fully offloads the key‑value (KV) cache in large language model (LLM) serving, delivering higher throughput while meeting a..."
date: 2026-11-06T22:02:31+05:30
tags: [LLM, Inference, KVCache, DRAM]
categories: ["AI", "Machine Learning", "Systems Engineering", "Artificial Intelligence", "Hardware Acceleration"]
author: "Shoubhik Banerjee"
draft: false
---

# FlashOffloading Boosts LLM Serving Throughput by Offloading KV Cache to Host DRAM

FlashOffloading is a new host‑DRAM‑centric inference architecture that fully offloads the key‑value (KV) cache in large language model (LLM) serving, delivering higher throughput while meeting a 30 ms time‑per‑output‑token (TPOT) service‑level objective.

## 🔍 Overview
- In LLM serving systems the KV cache grows linearly with sequence length and concurrency, quickly exhausting high‑bandwidth memory (HBM) capacity and limiting concurrency.
- Moving the KV cache to host DRAM frees HBM space and allows higher concurrency, but the added cache management and host‑to‑device (H2D) load overhead increase inference latency, so the concurrency gain does not translate into effective throughput.

## 🧩 How it works
- **Rolling HBM cache for prefill** – keeps a small active portion of the KV cache in HBM during the prefill phase.
- **Hot cache for decode** – stores frequently accessed KV entries in host DRAM for decode.
- **Reverse sparse index** – provides zero‑extra miss‑lookup overhead when locating KV entries.
- **Compute‑load overlapped kernel** – overlaps computation with H2D data movement to reduce offloading latency across the entire pipeline.

## ⚙️ Performance gains
- Deployed with GLM‑5.2 using multi‑token prediction (MTP3) speculative decoding on an Ascend910C prefill‑decode disaggregated platform.
- **Prefill throughput** improves by up to **1.38×**.
- **Decode throughput** improves by up to **1.91×**.
- Gains are achieved while staying within a **30 ms TPOT** constraint.

## 🚀 Availability
- FlashOffloading has been integrated into an open‑source serving framework. See the implementation at **this https URL**.


#LLM #Inference #KVCache #DRAM

---

*Source: [FlashOffloading: Low-Latency KV Cache Offloading for Long-Context LLM Serving](https://arxiv.org/abs/2611.07542v1)*
