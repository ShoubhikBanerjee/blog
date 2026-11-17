---
title: "Chandra OCR 2: Advanced Document Conversion and Extraction"
slug: "chandra-ocr-2-advanced-document-conversion-and-extraction"
description: "Chandra OCR 2, a state-of-the-art OCR model, has been released with significant improvements in math, tables, layout, and multilingual OCR. It converts images and PDFs into structured..."
date: 2026-11-17T22:09:21+05:30
tags: [OCR, DocumentConversion, AI, MachineLearning, DataExtraction]
categories: ["AI", "Computer Vision", "Natural Language Processing", "Document Processing", "AI Tools"]
image: "https://avatars.githubusercontent.com/u/176631703?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Chandra OCR 2: Advanced Document Conversion and Extraction

Chandra OCR 2, a state-of-the-art OCR model, has been released with significant improvements in math, tables, layout, and multilingual OCR. It converts images and PDFs into structured HTML/Markdown/JSON while preserving layout information.

## 🔍 Overview
- Chandra OCR 2 is a state-of-the-art OCR model that converts images and PDFs into structured HTML/Markdown/JSON while preserving layout information.
- It has significant improvements in math, tables, layout, and multilingual OCR.
- The model supports 90+ languages and has excellent handwriting support.
- It reconstructs forms accurately, including checkboxes, and has strong performance with tables, math, and complex layouts.
- The model extracts images and diagrams, and adds captions and structured data.

## ⚙️ Key details
- Chandra OCR 2 has two inference modes: local (HuggingFace) and remote (vLLM server).
- Multilingual performance was a focus for Chandra 2. There isn't a good public multilingual OCR benchmark, so the team made their own.
- The model was benchmarked with the widely accepted olmocr benchmark.

## 🚀 Availability
- Chandra OCR 2 is available for commercial self-hosting with a license.
- For on-prem licensing, contact the team.
- The Datalab API turns documents into verifiable knowledge your agents act on. Every result traces back to its page and position, and one API can parse, extract, fill and edit documents.
- Get started with about 5,000 free convert pages every month (work email) — sign up — takes under 30 seconds — or try Chandra in the public playground.
- If you have high volume workloads, a batch processing service is available that has processed 1B+ pages in a day at peak.

## 💡 Why it matters
- Chandra OCR 2's improvements in math, tables, layout, and multilingual OCR make it a powerful tool for document conversion and extraction.
- The model's ability to preserve layout information and reconstruct forms accurately is particularly notable.
- The availability of a batch processing service for high volume workloads ensures that users can manage their workloads efficiently.

## 📦 Installation
```bash
pip install chandra-ocr
```

## 🔧 Usage
- With vLLM (recommended, lightweight install)
```bash
chandra input.pdf ./output
```
- Print Markdown directly to stdout
```bash
chandra input.pdf --stdout
```
- With HuggingFace (requires torch + transformers)
```bash
pip install "chandra-ocr[hf]"
chandra input.pdf ./output --method hf
```
- Interactive Web Viewer (zero extra dependencies)
```bash
chandra_app
```

## 📅 Timeline
- 3/2026 - Chandra 2 is here with significant improvements to math, tables, layout, and multilingual OCR
- 10/2025 - Chandra 1 launched

## 🌐 Multilingual Performance
- The model supports 90+ languages.
- Multilingual performance was a focus for Chandra 2.
- The team made their own multilingual OCR benchmark to test tables, math, ordering, layout, and text accuracy.

## 📊 Benchmarks
- Tops external olmocr benchmark and significant improvement in internal multilingual benchmarks.

## 📄 Document Conversion
- Convert documents to markdown, html, or json with detailed layout information.

## 📝 Document Extraction
- Extracts images and diagrams, and adds captions and structured data.

## 📋 Form Reconstruction
- Reconstructs forms accurately, including checkboxes.

## 📝 Handwriting Support
- Excellent handwriting support.

## 📊 Table Performance
- Strong performance with tables, math, and complex layouts.


#OCR #DocumentConversion #AI #MachineLearning #DataExtraction

---

*Source: [datalab-to/chandra](https://github.com/datalab-to/chandra)*
