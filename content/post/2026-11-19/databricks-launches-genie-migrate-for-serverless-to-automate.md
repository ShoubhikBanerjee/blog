---
title: "Databricks launches Genie Migrate for Serverless to automate classic-to-serverless migration"
slug: "databricks-launches-genie-migrate-for-serverless-to-automate-classic-to-serverless-migration"
description: "Databricks has launched Genie Migrate for Serverless in beta, an agent that automates the migration of jobs and notebooks from classic compute to serverless compute. The agent handles configuration..."
date: 2026-11-19T22:12:49+05:30
tags: [Databricks, Serverless, Migration, Genie, DataEngineering, AI]
categories: ["AI", "Data Engineering", "Cloud Computing", "AI Tools", "DevOps"]
image: "https://www.databricks.com/sites/default/files/blog_images/introducing-genie-migrate-for-serverless-blog-img-og.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks launches Genie Migrate for Serverless to automate classic-to-serverless migration

Databricks has launched Genie Migrate for Serverless in beta, an agent that automates the migration of jobs and notebooks from classic compute to serverless compute. The agent handles configuration translation and presents changes as reviewable diffs, reducing migration from a manual research project to a review-and-approve step.

## 🔍 Overview
- Serverless compute in Databricks removes the operational burden of managing infrastructure, automatically handling provisioning, scaling, and optimization.
- Serverless usage has grown multifold in the past year, with thousands of customers running notebooks and jobs on it.
- Most teams still have classic fleets they want to migrate to gain cost and operational benefits.
- Manual migration has been difficult: flipping a job to serverless often produces errors, access-mode incompatibilities, Spark config issues, or missing libraries.

## 🧩 How it works
- The agent runs from the `/compute migrate` slash command inside Genie on any job or notebook.
- It is fully managed and requires no setup to start scanning.
- Because Databricks manages it, the agent reads your job config and workload code inside your own workspace.
- Before any changes, the agent scans your Jobs and Notebooks and marks each workload with its serverless readiness.
- Once you pick an eligible workload, the agent proposes the changes needed for serverless and presents them for review before anything is written.
- Nothing is applied until you approve it.
- Every change, including code rewrites, is presented as a reviewable diff with a side-by-side comparison.
- If the agent is unsure about something (for example, whether a Spark conf is still needed), it reports the conf rather than removing it.
- For a larger fleet, you can run Genie Migrate for Serverless in the background with the Databricks CLI.
- Your original job does not change until you review and approve its migration, and approving keeps the job's ID, schedule, and permissions.

## ⚙️ Key details
| Aspect | Detail |
|---|---|
| Launch status | Beta |
| Invocation | `/compute migrate` slash command in Genie |
| Setup required | None (fully managed) |
| Scope | Jobs and notebooks inside the workspace |
| External sources | Not supported yet (e.g., Databricks Asset Bundles, Git folders) |
| Change application | Only after explicit approval |
| Diff presentation | Side-by-side comparison of what will change and what will not |
| Uncertainty handling | Reports Spark confs rather than removing them |
| Validation today | Deterministic checks for correctness |
| Validation coming | Deeper runtime validation in isolated sandbox against classic baseline |
| Fleet migration | Background runs via Databricks CLI |
| Job identity preserved | Job ID, schedule, and permissions retained after approval |

## 🚀 Availability
- Genie Migrate for Serverless is available now in beta.
- No setup is required; the agent runs from within Genie in your workspace.
- Background fleet scanning and migration are supported via the Databricks CLI.

## 💡 Why it matters
- Moves the translation knowledge from the practitioner's head and trial-and-error onto the platform.
- Turns workload migration into a review-and-approve step rather than a research project.
- Keeps judgment with the user: whether to migrate now, whether proposed changes look right, and whether the migrated run is healthy.
- Provides an explicit contract (side-by-side diff) that can be handed to a manager or on-call rotation.
- Is honest about what it has and has not proven, with runtime validation coming to show correctness signals before apply.

![figure](https://www.databricks.com/sites/default/files/blog_images/introducing-genie-migrate-for-serverless-blog-img-1.png)

![figure](https://www.databricks.com/sites/default/files/blog_images/introducing-genie-migrate-for-serverless-blog-img-2.png)

![figure](https://www.databricks.com/sites/default/files/blog_images/introducing-genie-migrate-for-serverless-blog-img-3.png)

#Databricks #Serverless #Migration #Genie #DataEngineering #AI

---

*Source: [Introducing Genie Migrate for Serverless](https://www.databricks.com/blog/introducing-genie-migrate-serverless)*
