---
title: "Automating Retail Replenishment with MMF, Databricks Genie, and Amazon Quick"
slug: "automating-retail-replenishment-with-mmf-databricks-genie-and-amazon-quick"
description: "A new technical solution integrates Databricks and Amazon Quick to automate the retail replenishment loop, connecting demand forecasting directly to order placement to reduce stockouts of fast-moving..."
date: 2026-09-14T22:04:39+05:30
tags: [Databricks, AmazonQuick, RetailAutomation, SupplyChain, DemandForecasting]
categories: ["AI", "Machine Learning", "Retail Technology", "AI Agents"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21670-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Automating Retail Replenishment with MMF, Databricks Genie, and Amazon Quick

A new technical solution integrates Databricks and Amazon Quick to automate the retail replenishment loop, connecting demand forecasting directly to order placement to reduce stockouts of fast-moving items.

## 💡 Why it matters
Retail demand forecasts typically have a short shelf life. Traditionally, the gap between a forecast and a placed order persisted because the forecast (stored in a governed data platform) and supplier availability (stored in a separate operational feed) lived in different systems, often inaccessible to the person placing the order. While foundation models have simplified demand forecasting across entire catalogs without per-item tuning, the bottleneck shifted to the downstream gap between the forecast and the action.

## 🧩 How it works
The solution creates a loop that detects demand surges, identifies a supplier, and places orders unattended, escalating to a human only when no rule fits. The process runs in four stages:

| Stage | Tool | Function |
| :--- | :--- | :--- |
| Forecast | Databricks MMF | Serves Chronos-2 to predict 7-day demand for every SKU. |
| Detect | Databricks Genie Agent | Surfaces SKUs in a surge (next-7-day average $\geq$ 1.5x prior-14-day average, with a floor of 1). |
| Decide | Amazon Quick | Reconciles surging SKUs against live supplier availability in Amazon S3 Tables and picks the cheapest supplier. |
| Act | Amazon Quick Flows | Places a purchase order via Supplier Order API or raises a human-review ticket if no single supplier can cover the surge. |

Amazon Quick serves as the central component, joining data on a shared product key at decision time using a Databricks Genie Agent over the Model Context Protocol (MCP), S3 Tables for supplier feeds, and an OpenAPI connector for the Order API.

## ⚙️ Key details
**Technical Requirements:**
* Databricks CLI 0.299.0+
* AWS CLI 2.36.2+
* jq 1.7
* uv (or Python 3.11) for the supplier-feed loader

**Permissions and Setup:**
* **Amazon Quick:** User requires an Author or Author Pro role to create Quick Flows, MCP, and OpenAPI connectors.
* **Databricks:** Identity requires CREATE CATALOG on the metastore (or admin pre-creation of the mmf catalog).
* **Authentication:** Databricks workspace profile must be authenticated via `databricks auth login`.

**Deployment:**
The solution is managed via the local terminal using `aws quicksight` subcommands (`create-flow`, `create-data-source`, and `create-space`). Key files in the accompanying repository include `genie/genie_space` for the agent definition, `flow/flow_definition` for the flow, and `cleanup/cleanup.sh` for teardown. The forecast is produced using notebooks 01 and 02 from the MMF accelerator’s `fresh_retail_net` example.

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21670-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/08/28/ML-21670-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/artifacts/DBSBlogs/ML-21670/ML-21670-3.png)

#Databricks #AmazonQuick #RetailAutomation #SupplyChain #DemandForecasting

---

*Source: [Automate replenishment with MMF, Databricks Genie, and Amazon Quick | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/automate-replenishment-with-mmf-databricks-genie-and-amazon-quick/)*
