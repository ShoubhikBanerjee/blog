---
title: "DocHop Benchmark Evaluates Multi-hop Reasoning in Document-style Images"
description: "DocHop, a new benchmark introduced on 2 Sep 2026, targets the under‑explored ability of multimodal large language models (MLLMs) to combine textual narrative context with chart evidence for..."
date: 2026-09-03T18:04:33+05:30
tags: [AI, Benchmark, MultiHop, DocumentUnderstanding, MLLM]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# DocHop Benchmark Evaluates Multi-hop Reasoning in Document-style Images

DocHop, a new benchmark introduced on 2 Sep 2026, targets the under‑explored ability of multimodal large language models (MLLMs) to combine textual narrative context with chart evidence for multi‑step reasoning in information‑dense documents.

## 🔍 Overview
- MLLMs have shown strong performance on structured visual tasks such as chart and document question answering.
- Existing benchmarks usually assess visual and textual domains in isolation, leaving the integrated chart‑context reasoning capability largely untested.
- DocHop fills this gap by requiring models to select, interpret, and aggregate chart data based on narrative constraints.

## 🧩 Benchmark Design
- The document narrative provides multi‑step compositional constraints; charts supply the corresponding data values.
- Each question is anchored to a semantic reference label defined in the narrative, forcing models to resolve target entities before aggregating evidence across multiple charts.
- Generation follows a stochastic logic‑first pipeline that controls reasoning depth and visual density.
- The benchmark comprises **2,074 examples** across **six task categories**.

## 📊 Scale & Metrics
- Human annotators achieve **over 90 % accuracy** on the benchmark.
- The best evaluated model reaches **62.83 % accuracy**, indicating a substantial gap between current MLLMs and human performance.
- Reasoning‑enhanced model variants consistently improve scores, yet performance declines as reasoning complexity increases.

## ⚙️ Model Performance
- A wide range of proprietary and open‑source MLLMs were evaluated.
- All models fall short of human accuracy, highlighting the challenge of multi‑hop document reasoning.

## 💡 Why it Matters
- DocHop provides a controlled testbed for studying how models integrate textual and visual information in real‑world, information‑dense documents.
- The benchmark can guide future research toward more robust, reasoning‑capable multimodal systems.


#AI #Benchmark #MultiHop #DocumentUnderstanding #MLLM

---

*Source: [DocHop: Benchmarking Out-of-domain Multi-hop Reasoning in Information-Dense Documents](https://arxiv.org/abs/2609.02059v1)*
