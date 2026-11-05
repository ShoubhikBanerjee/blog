---
title: "DharmaOCR Field Extractor: 2B‑Parameter Model Beats LLMs on Structured Document Extraction"
slug: "dharmaocr-field-extractor-2bparameter-model-beats-llms-on-structured-document-extraction"
description: "A new 2‑billion‑parameter model called the **Field Extractor**, built on the DharmaOCR‑LITE v1.1 checkpoint, extracts exactly the fields you ask for from any document image and returns typed JSON. It..."
date: 2026-11-05T12:04:51+05:30
tags: [OCR, DocumentAI, LLMComparison]
categories: ["AI", "Machine Learning", "Computer Vision", "Natural Language Processing", "AI Applications"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6a725daa5ca641a21ab61956/c1ik58RednXjcqrx5s2Fo.png"
author: "Shoubhik Banerjee"
draft: false
---

# DharmaOCR Field Extractor: 2B‑Parameter Model Beats LLMs on Structured Document Extraction

A new 2‑billion‑parameter model called the **Field Extractor**, built on the DharmaOCR‑LITE v1.1 checkpoint, extracts exactly the fields you ask for from any document image and returns typed JSON. It outperforms every frontier large language model (LLM) we tested while costing a fraction of the price.

## 🔍 Overview
- Takes a document image (invoice, ID, contract, court filing, etc.)
- Returns structured JSON: each field typed (string, number, boolean) and nested where the document nests
- Works on any language supported by the training data (English, Portuguese, and other European/Asian languages)

## 🧩 How it works
- **OCR layer** – First runs OCR to obtain the full printed text, preserving original layout.
- **Two request modes**
  - **Open** – No schema supplied. The model infers label‑value pairs and tables from layout and context, returning every detected field as key‑value pairs.
  - **Schema‑directed** – You provide an exact schema (field names and types). The model fills the schema, returns `null` for missing fields, and produces no extra keys, so the output can be piped directly into downstream systems.
- Output is always valid JSON with typed values.

## ⚙️ Key details
- **Base model**: DharmaOCR‑LITE v1.1, a 2‑billion‑parameter model optimized for OCR via supervised fine‑tuning and DPO.
- **Adapter**: LoRA adapter trained on 43,384 examples covering both request modes.
- **Training data**:
  - English multi‑domain documents collected from the public web.
  - Brazilian documents in Portuguese sourced internally.
  - Smaller multilingual set covering other European and Asian languages.
  - All data annotated at the field level.
- **Benchmark**: 546 documents across three scenarios (open extraction, partial schema, schema with nonexistent fields) – 1,638 total cases.
- **Metric**: Field‑level F1 (matched by path, including table position) multiplied by Levenshtein similarity and JSON validity.

## 📊 Performance comparison
| Provider | Quality gap (F1 pts) | Cost factor vs Field Extractor |
|----------|----------------------|------------------------------|
| Claude Opus 5 (closest) | 1.8 | ~6× higher |
| GPT‑5.6 Luna (widest) | 9.3 | ~147× higher |

The Field Extractor achieves higher accuracy while running at dramatically lower cost because it processes only the necessary tokens for OCR and field extraction, unlike general‑purpose LLM APIs that require full‑sentence reasoning for every request.

## 🚀 Availability
You can try the Field Extractor yourself **[here]**.

---

#OCR #DocumentAI #LLMComparison

---

*Source: [Dharma Field Extractor: Any Document In, Structured Fields in JSON Out](https://huggingface.co/blog/Dharma-AI/dharma-field-extractor)*
