---
title: "Elith and NVIDIA Release Nemotron-Personas-Finance-Japan Synthetic Dataset"
slug: "elith-and-nvidia-release-nemotron-personas-finance-japan-synthetic-dataset"
description: "- The financial sector faces strict privacy regulations and compliance requirements that limit the use of real‑world data."
date: 2026-11-09T22:03:01+05:30
tags: [SyntheticData, FinancialAI, NVIDIA, Japan, NeMo]
categories: ["AI", "Artificial Intelligence", "Data Generation", "Financial Technology", "Synthetic Data"]
image: "https://cdn-uploads.huggingface.co/production/uploads/604ad59e2fad27aca4515dab/-hyd03JaQoRhMbmlw9-uJ.jpeg"
author: "Shoubhik Banerjee"
draft: false
---

# Elith and NVIDIA Release Nemotron-Personas-Finance-Japan Synthetic Dataset

## 🔍 Overview
- The financial sector faces strict privacy regulations and compliance requirements that limit the use of real‑world data.
- Developing agentic AI for finance therefore needs synthetic data that mimics demographics, household structures, and asset statuses while avoiding privacy risks.
- Elith and NVIDIA have released **Nemotron-Personas-Finance-Japan**, a financial‑domain extension of the open‑source persona dataset *Nemotron-Personas-Japan*.
- To our knowledge, it is the first open persona dataset at million‑record scale that pairs Japan’s official statistics with household finance and financial literacy data.

## 🧩 How it works
- Built on official Japanese government statistics and public survey data.
- Generated with **NeMo SDG‑PGMs**, a probabilistic graphical model framework for statistically grounded synthetic data generation, and **NeMo Data Designer**, NVIDIA’s enterprise synthetic data generation system.
- Integrated with the **NeMo User Sim** framework, allowing instant execution of simulations drawn from diverse, realistic distributions.
- Text generation is performed by **gemma‑4‑31B‑it**, a Japanese language model.
- The generation pipeline supports complex Jinja templating, Pydantic validation, structured outputs, automated retries, and multiple generation back‑ends.

## ⚙️ Key details
- **Scale**: 9 M personas (1 M base records × 9 persona variations) – 50 % more than the original Nemotron‑Personas‑Japan.
- **Fields per record**: 50 total → 9 persona fields, 11 persona attributes, 30 contextual fields based on official demographic and labor statistics.
- **Token count**: ~1.5 B tokens, including ~750 M persona tokens.
- **Synthetic only**: No real individuals are represented; names follow real Japanese naming patterns but are generated from statistical distributions.
- **Rich persona attributes**:
  - Education granularity beyond national aggregates.
  - Expanded Occupation categories (e.g., business owners, specialized professions).
  - Life‑stage scenarios such as students, retirees, and periods of unemployment.
  - Household finances and real assets to reflect diverse economic backgrounds.
  - Digital & financial literacy indicators (internet and smartphone usage, financial knowledge).
- **Industry input**: Designed with feedback from Sompo Japan, Tokio Marine Holdings, Bank of Fukuoka, Mizuho Financial Group, Meiji Yasuda Life Insurance, and the Financial Data Utilization Association (FDUA).
- **License**: Released under CC BY 4.0, permitting commercial use.

| Model | License | Purpose |
|-------|---------|---------|
| NeMo SDG‑PGMs | Apache‑2.0 | Probabilistic graphical model framework for synthetic data generation |
| gemma‑4‑31B‑it | Apache‑2.0 | Japanese text generation |

## 🚀 Availability
- The dataset is open source and downloadable under the CC BY 4.0 license.
- It can be used directly with the NeMo User Sim framework for building conversational agents, customer‑simulation environments, model evaluation pipelines, and red‑team testing of customer‑facing AI.

## 💡 Why it matters
- Provides Japanese developers and enterprises a privacy‑preserving way to create and evaluate AI tailored to local financial regulations and consumer behavior.
- Enables realistic financial AI use cases—such as chatbots, sales‑conversation evaluation, and marketing simulations—without exposing real customer data.
- Helps the industry meet compliance demands while accelerating AI development cycles.

![figure](https://cdn-uploads.huggingface.co/production/uploads/604ad59e2fad27aca4515dab/P649AGmEfc-8C0I5qjqv_.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/604ad59e2fad27aca4515dab/qEMManizZ8vV73X4Ynh1P.png)

#SyntheticData #FinancialAI #NVIDIA #Japan #NeMo

---

*Source: [Nemotron-Personas-Finance-Japan: A Synthetic Dataset Capturing Japan's Demographics and Financial Context](https://huggingface.co/blog/nvidia/nemotron-personas-finance-japan)*
