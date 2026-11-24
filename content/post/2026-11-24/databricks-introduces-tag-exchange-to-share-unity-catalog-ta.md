---
title: "Databricks introduces Tag Exchange to share Unity Catalog tags via Iceberg"
slug: "databricks-introduces-tag-exchange-to-share-unity-catalog-tags-via-iceberg"
description: "Databricks announced support for catalog labels, a new capability in the Apache Iceberg REST Catalog API that enables platforms, engines, and agents to access context such as business purpose,..."
date: 2026-11-24T22:08:41+05:30
tags: [Databricks, ApacheIceberg, Metadata, TagExchange, DataGovernance, Interoperability]
categories: ["AI", "Data Management", "Metadata & Governance", "Open Standards", "AI Infrastructure"]
image: "https://www.databricks.com/sites/default/files/2026-11/blog-og-Sharing-catalog-metadata-across-data-platforms-engines-and-agents.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks introduces Tag Exchange to share Unity Catalog tags via Iceberg

Databricks announced support for catalog labels, a new capability in the Apache Iceberg REST Catalog API that enables platforms, engines, and agents to access context such as business purpose, ownership, and data classifications maintained in Iceberg REST-compatible catalogs. This development addresses the issue of metadata context remaining siloed in source catalogs, which previously forced teams to recreate classifications across platforms or maintain custom metadata synchronization pipelines.

## 🧩 How it works

Databricks worked with the Apache Iceberg community to add an optional labels field to the Iceberg REST LoadTable response. This provides a standard way for catalogs to expose table- and column-level context to other platforms, tools, and agents. 

*   **Labels format:** String key-value pairs that describe business ownership, intended use, sensitivity, or other catalog-maintained context.
*   **Flexibility:** The standard defines a common format for sharing metadata without prescribing vocabulary or interpretation, allowing each platform to build on it in its own way.
*   **Example:** A table named `support_cases` can carry labels like `domain=customer_support` or `system.certification_status=certified`. An authorized data steward can also assign column-level labels, such as `content_type=support_case_summary` for an `issue_summary` column.

## ⚙️ Key details

Tag Exchange is Databricks' implementation of this standard, exposing Unity Catalog’s table- and column-level tags through the Apache Iceberg REST Catalog API. This makes catalog metadata available directly to Python applications, including data-discovery tools and agents.

*   **Open Governance:** Context maintained in one system becomes usable across every platform, engine, and AI agent working with the data.
*   **Reusability:** Enterprises can reuse classifications and business context for discovery, agent workflows, and access policies.
*   **Interoperability:** Each tool retains the freedom to decide how to interpret and use that context, while the catalog’s metadata remains intact across platforms.

Databricks is joined by Google Cloud, Salesforce, ClickHouse, Atlan, Collibra, DataHub, Immuta, Trust3 AI, PhoenixAI, and Datastrato in advancing this shared vision of metadata interoperability.

## 🚀 Availability

Tag Exchange is available in Beta today. To get started, users can enable “Tag Exchange via Iceberg REST Catalog” in the Databricks Previews portal.

## 💡 Why it matters

This capability allows sensitivity labels set once in Unity Catalog to drive policy in external platforms without separate metadata projects. As noted by Don Bosco Durai, CTO of Trust3 AI, a sensitivity label set once in Unity Catalog can now drive policy in platforms like Trust3 AI without a separate metadata project. Similarly, Chandru Sugunan, Director of Product at Atlan, noted that open metadata exchange through the Iceberg REST Catalog lets enterprises keep context intact across every platform they choose to run.

#Databricks #ApacheIceberg #Metadata #TagExchange #DataGovernance #Interoperability

---

*Source: [Sharing catalog metadata across data platforms, engines, and agents](https://www.databricks.com/blog/sharing-catalog-metadata-across-data-platforms-engines-and-agents)*
