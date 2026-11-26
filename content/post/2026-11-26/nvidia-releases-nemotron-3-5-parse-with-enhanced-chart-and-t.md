---
title: "NVIDIA Releases Nemotron 3.5 Parse with Enhanced Chart and Table Extraction"
slug: "nvidia-releases-nemotron-3-5-parse-with-enhanced-chart-and-table-extraction"
description: "NVIDIA has released Nemotron 3.5 Parse, a compact document model that turns page images into structured data for retrieval-augmented generation (RAG) and agents. The new version significantly extends..."
date: 2026-11-26T22:08:01+05:30
tags: [NVIDIA, AI, DocumentAI, RAG]
categories: ["AI", "Machine Learning", "Computer Vision", "Natural Language Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6365c3f398da81987e2753f2/zArpuP9uLsLz9luMW0K2g.png"
author: "Shoubhik Banerjee"
draft: false
---

# NVIDIA Releases Nemotron 3.5 Parse with Enhanced Chart and Table Extraction

NVIDIA has released Nemotron 3.5 Parse, a compact document model that turns page images into structured data for retrieval-augmented generation (RAG) and agents. The new version significantly extends its ability to read charts and tables, especially in more difficult and ambiguous cases.

## 📄 What Parse 3.5 Does

Parse extracts content from pages of documents into reading order, assigns content classes such as headings, paragraphs, tables, and charts, and returns bounding boxes that locate the content. Tables and charts become structured records that can power downstream document processing applications.

For example, bar charts or other plots that do not have any marked numeric values can be analyzed by the model, which infers values by looking at the axes and height of the bar to derive these. Tables can be especially tricky because the structure is so meaningful, a shifted row or column can totally change the interpretation and meaning.

## 🧪 Training Approach

The advancements in Parse 3.5 have been largely powered by synthetic data generation, rendering variations of charts and tables with known ground truth and then training the model to reverse this process.

NVIDIA is open-sourcing three datasets used in the Parse 3.5 training:

- Synthetic Charts V1 — 9.98M examples: rendered charts and structured annotations for learning categories, series, and numerical values.
- Synthetic Tables V1 — 1M examples: rendered HTML tables with targets that preserve rows, columns, headers, and cell relationships.
- OCR Synthetic Multilingual v2 — 7.9M examples: synthetic document pages with Parse-format targets across varied fonts and layouts, for multilingual OCR and structured page reading.

## ⚙️ Key Details

Training was conducted in two phases. First, supervised fine-tuning (SFT) spanning text, layout, tables, charts, and multilingual documents. Learning to predict structured targets established the general capability of reading a page and representing its contents. Then, reinforcement learning with verifiable rewards (RLVR) was applied, using Group Relative Policy Optimization (GRPO). Rewards check the quality of sampled extractions, giving the model flexibility to find a correct answer without prescribing one exact token sequence, while discouraging looping and unfinished output.

The matched comparison shows the benefit: loop-flagged outputs fall from 126 to 29 pages—about 77% fewer, and outputs reaching the 9,000-token limit fall from 185 to 35. Overall score improves from 66.24 to 71.38, including +5.18 points in tables and +4.15 in charts.

## 🚀 Availability and Performance

A DFlash2 speculator enables faster inference. In the native single-pass benchmark on one H200 in BF16, DFlash2 increased throughput 7.62× at concurrency 1 and 1.52× at concurrency 512, compared with Parse 3.5 with speculative decoding disabled. At 512, Parse 3.5 reaches 13.48 pages/s without speculation and 20.44 pages/s with DFlash2, versus 2.98 for Parse 2.0. Those are 4.53× and 6.86× the Parse 2.0 throughput, respectively.

Now we're building on that release with synthetic training datasets, a fine-tuning recipe, and a DFlash2 speculator for faster inference. We're also sharing how we trained Parse 3.5.

![figure](https://huggingface.co/datasets/nvidia/Nemotron-Parse-Blog-Assets/resolve/main/images/figure-01-page-structure.png)

![figure](https://huggingface.co/datasets/nvidia/Nemotron-Parse-Blog-Assets/resolve/main/images/figure-02-chart-geometry.png)

![figure](https://huggingface.co/datasets/nvidia/Nemotron-Parse-Blog-Assets/resolve/main/images/figure-03-sft-grpo-gains.png)

#NVIDIA #AI #DocumentAI #RAG

---

*Source: [Building on Nemotron 3.5 Parse: Open Data, Fine-Tuning, and Faster Inference](https://huggingface.co/blog/nvidia/building-on-nemotron-35-parse-open-data-fine-tunin)*
