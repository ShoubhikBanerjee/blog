---
title: "Databricks Introduces Agentic Identity Resolution for Customer Data Platforms"
slug: "databricks-introduces-agentic-identity-resolution-for-customer-data-platforms"
description: "Databricks has launched Agentic Identity Resolution, an approach that combines deterministic, probabilistic, and LLM-based matching to connect fragmented customer records. This capability is part of..."
date: 2026-11-25T18:07:47+05:30
tags: [AIagents, CDP, CustomerData, IdentityResolution, Databricks]
categories: ["AI", "Data Management", "Customer Experience", "Artificial Intelligence", "Machine Learning"]
image: "https://www.databricks.com/sites/default/files/2026-11/Blog-Data-Modeling-Best-Practices-for-an-Agentic-CDP-Part-1-The-Data-Foundation.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks Introduces Agentic Identity Resolution for Customer Data Platforms

## 📚 Introduction

Databricks has launched Agentic Identity Resolution, an approach that combines deterministic, probabilistic, and LLM-based matching to connect fragmented customer records. This capability is part of CustomerLake, designed to help data teams build trusted datasets and enable marketers to activate audiences faster.

## 🧩 How It Works

The process involves several steps:

- Run deterministic rules first (exact email, exact phone, a partner ID that maps to your customer ID), then score the gaps with probabilistic matching.
- Cluster the matches and mint, or keep, a persistent ID.
- Build layers using Spark Declarative Pipelines and run identity resolution after silver, with the canonical ID becoming the join key for gold.

## ⚙️ Key Details

| Feature | Description |
|---------|-------------|
| Agentic Identity Resolution | Combines deterministic, probabilistic, and LLM-based matching to connect fragmented records |
| Profile Agents | Handle heavy lifting of matching and golden-record survivorship |
| Manual data steward overrides | Allow teams to apply human judgment where needed |

Agentic CDP requires:

- The right sources, clean data, one identity per customer, and golden profiles marketers trust.
- Agents handle matching records and drafting audiences while people choose sources, review matches, and approve actions.
- Identity resolution runs next to data, making ownership of the identity graph practical.

## 📏 Data Model Approach

- Part 1 of a two-part series focusing on modeling from raw data to omnichannel activation.
- Part 2 covers mapping B2C and B2B datasets, attributes, and use cases onto the model.
- Identity is matched nightly inside a tool, owned, explainable and reversible, with an audit-able identity graph using a persistent ID.

## 🚀 Availability

- Can be built with SQL rules plus open-source matchers like Splink or Zingg.
- Or use CustomerLake, where Profile Agents handle the heavy lifting.
- Data teams can define trusted datasets once through Databricks and Unity Catalog.

## 💡 Why It Matters

Brands long asked why they couldn't own their identity graph and run deterministic matching on their own data. With identity resolution running next to the data, owning the graph becomes practical, and in our experience it's the most important table you'll build.

#AIagents #CDP #CustomerData #IdentityResolution #Databricks

---

*Source: [Data Modeling Best Practices for an Agentic CDP, Part 1: The Data Foundation](https://www.databricks.com/blog/agentic-cdp-data-modeling-data-foundation)*
