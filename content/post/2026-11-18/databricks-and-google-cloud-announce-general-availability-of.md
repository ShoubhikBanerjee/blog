---
title: "Databricks and Google Cloud Announce General Availability of Bi-directional Catalog Federation"
slug: "databricks-and-google-cloud-announce-general-availability-of-bi-directional-catalog-federation"
description: "Today, Databricks and Google Cloud announced a significant milestone in catalog interoperability. Customers can now access a single copy of data from both Unity Catalog and Google Cloud's borderless..."
date: 2026-11-18T06:16:59+05:30
tags: [Databricks, GoogleCloud, DataInterop, UnityCatalog, Iceberg, DataGovernance]
categories: ["AI", "Data Engineering", "Cloud Computing", "Data Governance", "Interoperability"]
image: "https://www.databricks.com/sites/default/files/2026-11/unnamed_2.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks and Google Cloud Announce General Availability of Bi-directional Catalog Federation

Today, Databricks and Google Cloud announced a significant milestone in catalog interoperability. Customers can now access a single copy of data from both Unity Catalog and Google Cloud's borderless Lakehouse through Lakehouse Federation, which is now generally available.

## 🧩 How it works
The partnership supports bi-directional interoperability, allowing data to move seamlessly between the two platforms without copying.

- **From Google Cloud to Databricks**: Customers can mount Iceberg tables managed by Google Cloud's Lakehouse runtime catalog into Unity Catalog. These tables can then be queried by Databricks Lakehouse (the serverless data warehouse) or analyzed via Genie, which answers data questions from natural language without requiring code or SQL.
- **From Databricks to Google Cloud**: Data from Databricks can be brought into Google Cloud's Lakehouse. This allows customers using engines like BigQuery to read Unity Catalog managed tables without data copy.

## ⚙️ Key details
Databricks and Google Cloud are strengthening interoperability by making catalog metadata open. They helped drive the landing of catalog labels in the Iceberg community, a proposal that enables catalogs to share metadata through key-value pairs.

| Feature | Description |
| :--- | :--- |
| Catalog Labels | Enables catalogs to share metadata through key-value pairs (e.g., `domain=finance`, `status=certified`). |
| Tag Persistence | Ensures table and column tags (e.g., `pii=ssn`) continue to be tagged even as the table is federated from one catalog to another. |
| Agent Context | Shared labels provide context to agents searching for assets to answer data questions. |
| Data Masking | Catalog metadata can be used to flag sensitive data for masking. |

## 💡 Why it matters
Shared labels are critical for governance in the era of agents. By maintaining metadata consistency across federated catalogs, the partnership advances the vision of open governance, allowing sensitive data to be flagged and masked while providing necessary context for AI agents interacting with data assets.

Customers can get started with Catalog Federation between Unity Catalog and Google Cloud's borderless Lakehouse by reading the documentation.

![figure](https://www.databricks.com/sites/default/files/inline-images/bigquery-demo-under-2mb.gif)

#Databricks #GoogleCloud #DataInterop #UnityCatalog #Iceberg #DataGovernance

---

*Source: [Advancing Catalog Interoperability with Unity Catalog and Google Cloud’s Borderless Lakehouse](https://www.databricks.com/blog/advancing-catalog-interoperability-unity-catalog-and-google-clouds-borderless-lakehouse)*
