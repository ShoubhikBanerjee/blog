---
title: "Mostly AI engine enables flexible tabular and text model reuse"
slug: "mostly-ai-engine-enables-flexible-tabular-and-text-model-reuse"
description: "A new library, `mostlyai-engine`, serves as the core model engine for the Mostly AI Synthetic Data SDK. It allows users to train models on flat or sequential data and flexibly reuse them for various..."
date: 2026-11-27T22:09:22+05:30
tags: [SyntheticData, TabularAI, ModelReuse, MostlyAI, Python]
categories: ["AI", "Synthetic Data", "Machine Learning", "Data Engineering", "AI Infrastructure"]
image: "https://avatars.githubusercontent.com/u/8805950?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Mostly AI engine enables flexible tabular and text model reuse

## 🔍 Overview
A new library, `mostlyai-engine`, serves as the core model engine for the Mostly AI Synthetic Data SDK. It allows users to train models on flat or sequential data and flexibly reuse them for various downstream tasks without retraining. The engine supports two primary model classes: `TabularARGN` for structured tabular data and `LanguageModel` for semi-structured textual tabular data.

## 🧩 How it works
The `TabularARGN` class provides a scikit-learn-compatible interface for working with structured, flat, or sequential tabular data. Once trained, models can be reused for regression, classification, imputation, and sampling. Key training and generation capabilities include:
*   Control training time and parameters
*   Monitor training progress
*   Optionally enable differential privacy
*   Optionally provide context data
*   Up-sample or down-sample
*   Conditionally generate
*   Rebalance categories
*   Impute missing values
*   Incorporate fairness

## ⚙️ Key details
The library supports synthetic data generation, classification, regression, and imputation through a few lines of Python code. Users can load data, train the model, and perform tasks such as:
*   Generating new synthetic samples
*   Generating new synthetic samples conditionally
*   Filling in missing values
*   Predicting categorical or numerical target columns
*   Assessing marginal conditional probability for one or more target columns

A companion tool, `mostlyai-qa`, is used to assess the fidelity and novelty of synthetic samples with respect to original samples. It calculates accuracy, similarity, and distance metrics, visualizes statistics for comparison against training and holdout samples, and generates a standalone HTML summary report. It supports analyzing single-table data, sequential data, and sequential data with context.

## 🚀 Availability
The latest release of `mostlyai-engine` can be installed via `uv`. It is highly recommended to install the package within a dedicated virtual environment. For GPU setups required for LLM finetuning and inference, specific installation instructions are provided. On Linux, users can explicitly install the CPU-only variant of PyTorch together with `mostlyai-engine`. The `mostlyai-qa` package is available via `pip install -U mostlyai-qa`.

#SyntheticData #TabularAI #ModelReuse #MostlyAI #Python

---

*Source: [mostly-ai/mostlyai-engine](https://github.com/mostly-ai/mostlyai-engine)*
*Source: [mostly-ai/mostlyai-qa](https://github.com/mostly-ai/mostlyai-qa)*
