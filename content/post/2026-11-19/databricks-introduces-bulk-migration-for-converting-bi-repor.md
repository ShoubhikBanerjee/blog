---
title: "Databricks introduces bulk migration for converting BI reports to AI/BI Dashboards"
slug: "databricks-introduces-bulk-migration-for-converting-bi-reports-to-ai-bi-dashboards"
description: "Databricks has made a new feature generally available that allows organizations to migrate multiple Business Intelligence (BI) reports to AI/BI Dashboards in a single run. This capability addresses..."
date: 2026-11-19T22:12:49+05:30
tags: [Databricks, AIBI, DataMigration, GenieCode, BusinessIntelligence]
categories: ["AI", "Data Engineering", "AI Applications", "Business Intelligence", "Platform Features"]
image: "https://www.databricks.com/sites/default/files/blog_images/bulk-migrate-your-dashboards-to-ai-bi-blog-img-og.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks introduces bulk migration for converting BI reports to AI/BI Dashboards

Databricks has made a new feature generally available that allows organizations to migrate multiple Business Intelligence (BI) reports to AI/BI Dashboards in a single run. This capability addresses the limitations of the previous one-report-at-a-time flow, which was suitable for pilots but resulted in a months-long manual grind for organizations with hundreds of reports. The bulk migration agent can now process an entire folder of reports from a single command.

## 🔍 Overview

The migration agent reads source BI files, generates corresponding AI/BI Dashboards on Databricks, and maps them to a specified target catalog and schema. Instead of importing reports individually, users can process many reports together. This extends the existing Databricks AI/BI migration experience to support batch processing from a single command.

## 🧩 How it works

To use this feature, users must ensure that partner-powered AI features are enabled at both the account and workspace levels. The migration process involves preparing source files and triggering the bulk flow through specific commands or natural language prompts.

**File Preparation**:
* Export Tableau or Power BI reports to supported file types: `.twb`, `.twbx`, `.tds`, `.tdsx`, `.pbit`, or `.tmdl`.
* For Tableau workbooks connecting to published data sources, export the data source (`.tds` or `.tdsx`) and place it next to the workbook.
* Place all BI report files into a directory within a Unity Catalog volume. Note that bulk runs only pick up files from volumes; dragging files directly into the chat is only for single-report imports.

**Triggering the Migration**:
* **Directory-based**: Pointing the command at a directory triggers the bulk flow for all reports in that folder.
* **Natural Language**: Users can request, “Migrate every Power BI report in /Volumes/finance/bi/reports to AI/BI Dashboards.”
* **Specific Files**: Users can name specific files, e.g., “Migrate Tableau reports Dashboard1.twb, Dashboard2.twb in /Volumes/finance/bi/reports to AI/BI Dashboards.”

## ⚙️ Key details

The agent recognizes the batch, lists the found reports, and matches Tableau workbooks to their companion data source files automatically. It checks with the user if a pairing is unclear and prompts for the destination catalog and schema. Reports are queued and processed a few at a time, reusing existing Unity Catalog tables and views where possible before creating new ones.

**Supported File Formats**:
| Format | Source |
| :--- | :--- |
| .twb | Tableau |
| .twbx | Tableau |
| .tds | Tableau Data Source |
| .tdsx | Tableau Data Source |
| .pbit | Power BI |
| .tmdl | Power BI |

**Execution and Monitoring**:
* Each report runs through the Genie Code planning phase, including parsing, assessing the workbook, enumerating the semantic layer, creating metric views, building dashboard pages, and validating the migration.
* A status card in the chat maintains a running tally of the batch, marking each report as Queued, Running, or Completed.
* Users can stop an individual report or halt all in-flight processes from the status card.
* Each report runs in its own background job, so the tab does not need to remain open. Progress can be viewed later in Genie Code history.
* If a run stops to ask a question, users can answer it in the linked Genie Code conversation, and the migration will pick up where it left off.
* Every Genie Code response can be undone as a single step.

## 🚀 Availability

The bulk migration feature is now generally available and ready to use in workspaces today. For current limits on the number and size of files supported in a single bulk import, users should refer to the public documentation on `/importBI`.

## 💡 Why it matters

This feature transforms the migration of legacy BI assets into a strategic modernization effort that is no longer limited to manual, report-by-report grinding. By allowing organizations to point the agent at an entire folder, they can convert large libraries of reports to AI/BI Dashboards efficiently, ensuring that metric views and SQL views are mapped to the correct target catalogs and schemas.

![figure](https://www.databricks.com/sites/default/files/blog_images/bulk-migrate-your-dashboards-to-ai-bi-blog-img-3.png?v=1794493394)

![figure](https://www.databricks.com/sites/default/files/blog_images/bulk-migrate-your-dashboards-to-ai-bi-blog-img-4.png?v=1794493394)

![figure](https://www.databricks.com/sites/default/files/blog_images/bulk-migrate-your-dashboards-to-ai-bi-blog-img-5.png?v=1794493394)

#Databricks #AI-BI #DataMigration #GenieCode #BusinessIntelligence

---

*Source: [Bulk migrate your dashboards to AI/BI with Genie Code](https://www.databricks.com/blog/bulk-migrate-your-dashboards-aibi-genie-code)*
