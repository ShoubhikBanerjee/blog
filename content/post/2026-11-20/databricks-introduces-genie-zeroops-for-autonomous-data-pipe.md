---
title: "Databricks introduces Genie ZeroOps for autonomous data pipeline issue resolution"
slug: "databricks-introduces-genie-zeroops-for-autonomous-data-pipeline-issue-resolution"
description: "Databricks has introduced Genie ZeroOps, an autonomous agent that detects, investigates, and resolves data pipeline issues. Now available in Public Beta, ZeroOps automates the manual workflow of..."
date: 2026-11-20T14:26:01+05:30
tags: [Databricks, GenieZeroOps, DataPipeline, AutonomousAgent, DataQuality]
categories: ["AI", "Data Engineering", "Autonomous Systems", "AI Agents", "Data Quality"]
image: "https://www.databricks.com/sites/default/files/2026-11/2026-11-Blog-Genie-ZeroOps-now-in-public-beta-What-we-re-building-after-feedback-from-80-000-customer-incidents-OG-1200x628-2x.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks introduces Genie ZeroOps for autonomous data pipeline issue resolution

Databricks has introduced Genie ZeroOps, an autonomous agent that detects, investigates, and resolves data pipeline issues. Now available in Public Beta, ZeroOps automates the manual workflow of identifying and fixing pipeline issues, maintaining security, governance, and recommendation quality.

## 🔍 Overview
- Genie ZeroOps is an autonomous agent that detects, investigates, and resolves data pipeline issues.
- It automates the entire manual workflow from initial issue alert to a pull request.
- ZeroOps maintains security, governance, and recommendation quality.

## 🧩 How it works
- ZeroOps automatically triggers as soon as an issue is detected, without a prompt.
- It reads run logs, source code, upstream table metadata, and samples, while respecting Unity Catalog permissions.
- It uses Data Quality Monitoring to flag tables with issues related to freshness and completeness.
- ZeroOps proposes fixes and can push them to a new branch for a pull request, never changing production code or data without direct approval.

## ⚙️ Key details
- ZeroOps leverages direct access to Unity Catalog, metadata, and pipeline lineage.
- It uses models hosted by Databricks inside their security perimeter, with model calls staying in the workspace's region.
- The model provider does not retain prompts or responses.
- ZeroOps can be enabled by a workspace admin from the workspace Previews page.

## 🚀 Availability
- Genie ZeroOps is available in Public Beta.
- Workspace admins can turn it on from the workspace Previews page.
- The ZeroOps banner can be found on the top of the pipelines page.

## 💡 Why it matters
- Data engineering teams are overwhelmed, managing many thousands of pipelines a day.
- Over half of pipeline issues require organization-specific knowledge to properly triage, rank, and resolve.
- ZeroOps handles these complexities natively, leveraging direct access to your Unity Catalog, metadata, and pipeline lineage.
- ZeroOps observed over 80,000 real customer issues across hundreds of companies during the private preview.
- The new features added to help data teams triage issues faster include inbox sharing, notifications, one-click PR creation, and the ability to add custom business instructions.

## 📚 Documentation
- Read the documentation [here](https://www.databricks.com/sites/default/files/inline-images/View-of-ZeroOPs-inbox-listing-recent-incidents.png) for more details on how to get started.
- If your team needs help onboarding ZeroOps to production, reach out to your account team to inquire about any workshops that we offer.


![figure](https://www.databricks.com/sites/default/files/inline-images/View-of-ZeroOPs-inbox-listing-recent-incidents.png)

![figure](https://www.databricks.com/sites/default/files/inline-images/share-your-zeroops-configuration_0.png)

![figure](https://www.databricks.com/sites/default/files/inline-images/Notifications-with-summaries_0.png)

#Databricks #GenieZeroOps #DataPipeline #AutonomousAgent #DataQuality

---

*Source: [Genie ZeroOps, now in public beta: An autonomous agent that fixes data pipelines, with lessons from 80,000 customer issues](https://www.databricks.com/blog/genie-zeroops-now-public-beta-autonomous-agent-fixes-data-pipelines-lessons-80000-customer)*
