---
title: "Cloudflare Updates Clairic Extraction Model and Introduces Lighter Clairic-flash Variant"
slug: "cloudflare-updates-clairic-extraction-model-and-introduces-lighter-clairic-flash-variant"
description: "Cloudflare's Workers AI superintelligence team has announced a major update to Clairic, its frontier AI extraction model, alongside the release of a lighter, faster 9-billion-parameter model called..."
date: 2026-11-19T06:12:23+05:30
tags: [Cloudflare, WorkersAI, Clairic, LLM, DataExtraction]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Natural Language Processing", "Computer Vision"]
image: "https://blog.cloudflare.com/_emdash/api/media/file/01M7R8FT40SDKKF94QYB97GJJT.01M7R8FTRTG1FSS3A675QSEWY2.png"
author: "Shoubhik Banerjee"
draft: false
---

# Cloudflare Updates Clairic Extraction Model and Introduces Lighter Clairic-flash Variant

Cloudflare's Workers AI superintelligence team has announced a major update to Clairic, its frontier AI extraction model, alongside the release of a lighter, faster 9-billion-parameter model called Clairic-flash. Based on feedback from its preview release, Cloudflare redesigned the architecture of Clairic to improve extraction accuracy from complex documents, including images and multi-page PDFs, while maintaining fast performance and open-weights availability on Hugging Face.

## 🔍 Overview
Cloudflare has transitioned into a neolab building its own frontier AI models for customers and the open-source community. Since announcing the preview of Clairic, the team received extensive feedback on customer use cases, such as extracting data from images of receipts and reading values from support tickets. To excel at reading from unstructured data, the team redesigned the model's architecture to prioritize highly accurate data extraction.

## 🧩 How it works
The new architecture introduces several updates to improve extraction performance:
* **Parallel Slot Autoregressive Generation**: Instead of a single forward pass, the model now uses parallel slot autoregressive generation for ordinary text and number extraction fields. Each field uses its already written tokens to select the next token and stops at its own end marker. This parallel advancement occurs in the serving batch to ensure fast latency.
* **Specialized Heads**: Trained specialized heads handle computation, estimation, forecasts, durations, calculated dates, and explicit arithmetic.
* **Preserved API Features**: Despite the architectural changes, the typed API interface still provides confidence scores, character spans, and probabilities with every request.

## ⚙️ Key details
The updated models offer significant functional improvements over the preview version:
* **Multi-Page and Document Support**: The models now support reading complex documents, including PDFs and up to four total images or PDF pages. In a single request, users can extract information such as the supplier, total, and line items (which return as rows preserving the association of description, quantity, and price).
* **Improved Accuracy**: On internal benchmarks covering text and images, image reading accuracy improved from 207 errors to 0.
* **Sub-Second Latency**: Latency tests measuring complete HTTP responses from self-hosted servers demonstrate response times under one second.

## 🚀 Availability
Both models are hosted on Workers AI, and their full open weights are available on Hugging Face.

| Model | Parameter Count | Workers AI Endpoint | Pricing (per Million Input Tokens) |
| :--- | :--- | :--- | :--- |
| Clairic | 27B | `@cf/cloudflare/clairic` | $0.24 |
| Clairic-flash | 9B | `@cf/cloudflare/clairic-flash` | $0.10 |

Clairic's pricing follows System One pricing principles, meaning users are only charged for input tokens, and Cloudflare covers the cost of output token generation.

#Cloudflare #WorkersAI #Clairic #LLM #DataExtraction

---

*Source: [An updated Clairic and Clairic-flash are now open-weight, from the new Workers AI Superintelligence team](https://blog.cloudflare.com/open-clairic/)*
