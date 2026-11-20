---
title: "Morphik Core and Metasyn Introduce New Tools for Multimodal Data and Synthetic Privacy"
slug: "morphik-core-and-metasyn-introduce-new-tools-for-multimodal-data-and-synthetic-privacy"
description: "Morphik and Metasyn introduce new tools for developers. Morphik Core offers an open-source multimodal retrieval engine for complex documents, while Metasyn provides a tool for generating synthetic..."
date: 2026-11-20T06:16:59+05:30
tags: [AI, DataPrivacy, SyntheticData, DocumentProcessing]
categories: ["AI", "Machine Learning", "Data Privacy", "Computer Vision", "Software Development"]
image: "https://avatars.githubusercontent.com/u/189408230?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Morphik Core and Metasyn Introduce New Tools for Multimodal Data and Synthetic Privacy

Morphik and Metasyn introduce new tools for developers. Morphik Core offers an open-source multimodal retrieval engine for complex documents, while Metasyn provides a tool for generating synthetic tabular data.

## 🔍 Overview

Morphik (morphik.ai) builds AI workers that run back-office operations — AP, billing, collections, and payroll — for skilled nursing and senior living operators. To support this, Morphik Core is the open-source multimodal retrieval engine offered to developers at dev.morphik.ai.

Separately, Metasyn allows owners of sensitive data to create test data, do open science, improve code reproducibility, and enhance dataset accessibility without leaking private information.

## 🧩 How it works

**Morphik Core** addresses the failure of traditional RAG approaches in production. Cobbling together separate systems for text extraction, OCR, embeddings, and vector databases creates fragile pipelines that break under real-world load and fail to understand visually rich documents. Charts become meaningless text fragments, and critical diagrams lose their spatial relationships.

Morphik Core provides a unified AI-native toolset to ingest, search (deep and shallow), transform, and manage unstructured and multimodal documents.

*   **Multimodal Search:** Uses techniques such as ColPali to build search that understands visual content. Search over images, PDFs, videos, and more with a single endpoint.
*   **Metadata Extraction:** Fast and scalable extraction of metadata including bounding boxes, labeling, classification, and more.
*   **Integration:** Developers can integrate with existing tools and workflows, including Google Suite, Slack, and Confluence.

**Metasyn** generates synthetic tabular data by fitting a model to an existing dataframe, saving it to a transparent and auditable .json file, and synthesizing a new dataframe that looks like the real one.

## ⚙️ Key details

**Morphik Core Capabilities**

| Capability | Feature |
| :--- | :--- |
| **Ingest** | Multimodal documents |
| **Search** | ColPali, images, PDFs, videos |
| **Transform** | Metadata extraction (bounding boxes, labeling, classification) |
| **Manage** | Unstructured and multimodal data |

**Metasyn Features**

*   **Accessible:** Designed to be easy to use and understand, welcoming to newcomers.
*   **Fully featured:** Natively handles missing values, categorical data, key columns with unique values, and structured strings.
*   **Transparent:** Shares the model and settings used to create data through a traceable, auditable metadata format.
*   **Private:** By default, does not incorporate multivariate information to reduce privacy risks; supports disclosure control plugins.
*   **Integrated:** Closely integrates with Polars and Faker for localized data generation.
*   **Extensible:** Plugin system allows for custom extensions to adjust privacy or features.

## 🚀 Availability

**Morphik Core**
*   **Pricing:** Offers a generous free tier and transparent, compute-usage based pricing.
*   **Hosting:** Self-host options available via Docker or direct installation. Note: Limited support is provided for self-hosted deployments.
*   **Access:** Programmers can use the Python SDK or REST API. The Morphik Console is also available.

**Metasyn**
*   **Installation:** Can be installed directly from PyPI or GitHub.
*   **Usage:** To generate synthetic data, users fit a MetaFrame to the data, which can then be used to produce new synthetic rows. The resulting DataFrame can be exported to CSV, Parquet, Excel, and more.
*   **Tutorial:** An interactive tutorial is available online to explore options.

## 💡 Why it matters

Building AI applications that interact with data shouldn't require duct-taping together a dozen different tools just to get relevant results to your LLM. Morphik Core provides the tools to integrate complex context into AI applications, while Metasyn enables transparent, privacy-friendly data reuse.

#AI #DataPrivacy #SyntheticData #DocumentProcessing

---

*Source: [morphik-org/morphik-core](https://github.com/morphik-org/morphik-core)*
*Source: [sodascience/metasyn](https://github.com/sodascience/metasyn)*
