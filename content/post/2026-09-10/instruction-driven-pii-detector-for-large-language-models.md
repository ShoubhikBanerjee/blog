---
title: "Instruction-Driven PII Detector for Large Language Models"
slug: "instruction-driven-pii-detector-for-large-language-models"
description: "A new configurable, instruction-driven detector for Personally Identifiable Information (PII) has been released. The tool is designed to run on any large language model (LLM) managed on Amazon..."
date: 2026-09-10T22:04:27+05:30
tags: [LLM, PII, AmazonBedrock, DataPrivacy]
categories: ["AI", "Machine Learning", "Data Privacy", "Software Development"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/08/ML-21255-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Instruction-Driven PII Detector for Large Language Models

A new configurable, instruction-driven detector for Personally Identifiable Information (PII) has been released. The tool is designed to run on any large language model (LLM) managed on Amazon Bedrock or hosted on private infrastructure.

## 🔍 Overview

The detector treats the language model as a configurable and swappable component. It is evaluated on five public PII corpora across nine LLM-based detectors, including the OpenAI PrivacyFilter.

## 🧩 How it works

The detector is built from four components:
* **Prompt**: Defines the schema in a single system-prompt template containing fifteen entity categories with one-line definitions, a do-not-flag list, and optional few-shot examples.
* **Backend**: Runs the model via a uniform inference interface called the Inferencer.
* **Parsing-and-offset layer**: Converts the model response into located spans.
* **Call sequence**: A thin layer that ties the other components together.

Because LLMs cannot reliably produce character offsets, the model is instructed to respond with a JSON list containing the entity type and the exact text value found. A post-processing step then computes exact character offsets and removes duplicates.

## ⚙️ Key details

The detection logic resides entirely in the instructions and a thin parsing layer. This architecture provides several capabilities:
* **Configurability**: The entity set can be changed via a one-line edit to the instructions without retraining or redeployment.
* **Multilingual Support**: The system can reason about context across eight languages without requiring a translation step.
* **Deployment Flexibility**: It can run on a managed API or inside a virtual private cloud (VPC).

| Component | Options/Details |
| :--- | :--- |
| Model | Frontier Amazon Bedrock models or small open models on a single GPU |
| Managed Adapter | Amazon Bedrock adapter (`pii_detector/bedrock_inferencer.py`) |
| Custom Adapter | Open models (e.g., OSS-GPT 20B) served on own infrastructure with a GPU |

## 🚀 Availability

The detector ships as the `pii-detector` package, available in the `sample-llm-pii-detection` repository. The full prompt is located in `pii_detector/templates.py`.

#LLM #PII #AmazonBedrock #DataPrivacy

---

*Source: [Model-agnostic PII detection with LLMs | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/model-agnostic-pii-detection-with-llms/)*
