---
title: "SDGym Benchmarking Framework Released for Synthetic Data Evaluation"
slug: "sdgym-benchmarking-framework-released-for-synthetic-data-evaluation"
description: "The Synthetic Data Vault Project from DataCebo has introduced SDGym (Synthetic Data Gym), a benchmarking framework designed to model and generate synthetic data. This tool allows developers to..."
date: 2026-11-16T22:14:27+05:30
tags: [SyntheticData, Benchmarking, DataCebo, MachineLearning, SDGym]
categories: ["AI", "Data Engineering", "Machine Learning", "Open Source Tools", "Synthetic Data"]
image: "https://avatars.githubusercontent.com/u/59050321?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# SDGym Benchmarking Framework Released for Synthetic Data Evaluation

The Synthetic Data Vault Project from DataCebo has introduced SDGym (Synthetic Data Gym), a benchmarking framework designed to model and generate synthetic data. This tool allows developers to measure performance, memory usage, and data quality across various modeling techniques, including classical statistics and deep learning.

## 🔍 Overview
SDGym integrates with the Synthetic Data Vault (SDV) ecosystem, providing a way to evaluate synthesizers, datasets, and metrics. The project traces its origins to MIT's Data to AI Lab in 2016, with DataCebo founded in 2020 to grow the ecosystem, which is now described as the largest for synthetic data generation and evaluation.

## 🧩 How it works
The framework allows users to benchmark techniques by selecting synthesizers and baselines, then running evaluations on publicly available or custom datasets. Key workflow steps include:
*   Defining which modeling techniques to use, such as `GaussianCopulaSynthesizer` and `CTGANSynthesizer`.
*   Selecting baselines, such as `UniformSynthesizer`.
*   Executing the benchmark using the function `sdgym.benchmark_single_table`.
*   Generating a detailed evaluation of performance, memory, and quality across the selected datasets.

Users can also customize the process by writing their own machine learning models, specifying training and sampling logic to test personal synthetic data generation techniques.

## ⚙️ Key details
*   **Metrics:** Measures performance, memory usage, synthetic data quality, and privacy.
*   **Data Sources:** Supports publicly available datasets from the SDV project and custom private datasets stored locally or on Amazon S3.
*   **Customization:** Allows users to include their own synthesizers, datasets, or metrics.
*   **Installation:** Available via pip or conda, with a recommendation to use a virtual environment to avoid software conflicts.

## 🚀 Availability
SDGym is part of the SDV library ecosystem. Developers can access the documentation and install the package to begin benchmarking immediately. The library includes a feature to list available datasets, facilitating quick setup for users wishing to test against standard public data.

#SyntheticData #Benchmarking #DataCebo #MachineLearning #SDGym

---

*Source: [sdv-dev/SDGym](https://github.com/sdv-dev/SDGym)*
