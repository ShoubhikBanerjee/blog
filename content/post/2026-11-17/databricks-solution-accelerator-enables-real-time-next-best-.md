---
title: "Databricks Solution Accelerator Enables Real-Time Next-Best-Offer Recommenders"
slug: "databricks-solution-accelerator-enables-real-time-next-best-offer-recommenders"
description: "Databricks has released an open-source Solution Accelerator that uses Feature Views to build a real-time next-best-offer (NBO) recommender for financial services. The solution addresses the challenge..."
date: 2026-11-17T18:10:30+05:30
tags: [Databricks, MachineLearning, RecommendationSystems, FinTech, MLOps]
categories: ["AI", "Machine Learning", "Data Engineering", "Financial Services"]
image: "https://www.databricks.com/sites/default/files/2026-11/real-time-nbo-og.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks Solution Accelerator Enables Real-Time Next-Best-Offer Recommenders

Databricks has released an open-source Solution Accelerator that uses Feature Views to build a real-time next-best-offer (NBO) recommender for financial services. The solution addresses the challenge of real-time personalization by allowing developers to define features once for both training and serving, preventing duplicate definitions that can drift over time.

## 🔍 Overview
The accelerator enables a system that ranks a catalog of offers—including credit card upgrades, savings products, and personal loans—based on in-session intent. When a retail banking customer checks their accounts, explores credit cards, or opens a loan calculator, these interactions signal current intent. The system ensures that relevant offers reach the customer while they are still in the session. The accelerator includes two main parts: a recommender using batch features and an extension that adds streaming, in-session intent. Both are built end-to-end on Databricks with runnable notebooks that users can clone and deploy.

## 🧩 How it Works
Raw clickstream data is aggregated into time-windowed features for two purposes: training on historical values as they existed at a given point in time, and serving predictions using current values with millisecond latency. To avoid train/serve skew, which can degrade model accuracy, features must be computed the same way during training and serving. Databricks Feature Views eliminate the need for separate feature definitions by letting users define features once for both contexts.

The training process uses the `create_training_set` API, which retrieves feature values as they existed at each labeled event to prevent future data leakage. This utilizes the Feature Engineering SDK to reconstruct feature values via a point-in-time join. The resulting training set feeds a LightGBM ranker registered in Unity Catalog. At inference time, the Model Serving endpoint fetches batch features from the online store using `customer_id` and scores all 40 offers directly without an additional candidate-narrowing step. Each request contains the `customer_id`, candidate offers, and session context.

## ⚙️ Key Details
The architecture supports specific performance and structural requirements:

*   **Latency:** One declarative definition powers point-in-time training and warm online ranking at p95 34 ms, with in-session signals live in under 130 ms.
*   **Model:** A single ranking model combines stable customer context (balances, spending, tenure, and risk band) with recent clickstream activity.
*   **Optimization:** `SawtoothWindow` keeps longer streaming windows practical, allowing a 30-day category count to stay fresh as new events arrive without recomputing entire history.
*   **Structure:** The accelerator consists of three steps delivered as runnable notebooks across two parts that share a catalog, schema, online store, and feature definitions.

## 💡 Why it Matters
Real-time personalization depends on understanding what customers want in the moment. By ensuring that features are computed identically for offline training and online serving, organizations can maintain model accuracy while serving predictions with millisecond latency. The shared definitions reduce the risk of feature drift that typically occurs when training and serving pipelines are built separately.

![figure](https://www.databricks.com/sites/default/files/inline-images/image1_144.png?v=1794598267)

![figure](https://www.databricks.com/sites/default/files/inline-images/image4_83.png?v=1794617944)

#Databricks #MachineLearning #RecommendationSystems #FinTech #MLOps

---

*Source: [Build a real-time next-best-offer recommender using Databricks Feature Views](https://www.databricks.com/blog/build-real-time-next-best-offer-recommender-using-databricks-feature-views)*
