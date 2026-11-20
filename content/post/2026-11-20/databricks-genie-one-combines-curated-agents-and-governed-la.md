---
title: "Databricks Genie One Combines Curated Agents and Governed Layer for 93-95% Accuracy"
slug: "databricks-genie-one-combines-curated-agents-and-governed-layer-for-93-95-accuracy"
description: "Databricks has released Genie One, powered by the generally available Genie Ontology, which integrates business context into analytics by combining curated agents with a governed semantic layer to..."
date: 2026-11-20T22:08:48+05:30
tags: [GenieOne, GenieOntology, AIagents, Businessanalytics, Databricks, UnityCatalog]
categories: ["AI", "AI Agents", "Business Intelligence", "Data Governance", "Machine Learning"]
image: "https://www.databricks.com/sites/default/files/blog_images/genie-one-accuracy-why-curated-agents-need-blog-img-og.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks Genie One Combines Curated Agents and Governed Layer for 93-95% Accuracy

Databricks has released Genie One, powered by the generally available Genie Ontology, which integrates business context into analytics by combining curated agents with a governed semantic layer to resolve contradictory metrics across teams.

## 🔍 Overview
- Genie One uses Genie Ontology to bring business context into the analytics experience.
- Genie Ontology learns from existing team work (dashboards, queries, notebooks, semantic models) as Ontology Snippets.
- This learned knowledge is complemented by a governed layer: explicitly defined business concepts in Unity Catalog via certified Metric Views, Domains and Subdomains, and Pages.
- A study compared four Genie Agents (Finance, Reserving, Underwriting, Claims) using the same tables but team-specific definitions, queries, and documents.
- The study also tested a fictional retailer to validate findings outside insurance.

## 🧩 How it works
- Genie One does not simply select one agent for every question.
- It can use governed Unity Catalog Semantics (Metric Views, Domains and subdomains, Pages) or route a question to a relevant Genie Agent.
- If no suitable match is found, it searches the workspace.
- When answering using its own context, Genie One does not automatically inherit the instructions configured inside each agent.

## ⚙️ Key details
### Agent setup
- Four agents shared the same underlying tables.
- Each agent had access to its team's folder of documents (14 PDFs total across four folders).
- Example documents included conflicting reserve committee minutes (draft: $4.1M increase, approved: $5.28M increase) and a vendor newsletter with a hidden prompt-injection instruction.
- Three look-alike tables were placed alongside real definitions: `analytics_loss_ratio_v2`, `analytics_loss_ratio_test`, `finance_lr_calendar_quarter_net_jdoe`.

### Accuracy results
| Configuration | Accuracy |
|---------------|----------|
| Tables alone | 64% |
| Curated agents only | 83% |
| Governed layer only | 83% |
| Curated agents + governed layer | 93–95% (across two runs) |
| Combined on loss-ratio questions | 93% |
| Combined on questions needing documents and structured data | 97% |
| Retailer: curated agents + governed layer | 82% (up from 54% with curated agents alone) |

### Complementary strengths
- Curated agents improved document-based answers.
- Governed layer improved answers dependent on business definitions.

## 💡 Why it matters
- Business metrics like loss ratio can have multiple correct definitions (e.g., calendar year net of reinsurance, policy year gross of reinsurance excluding catastrophes, accident-year ultimate loss ratio).
- Without shared context, teams produce contradictory but valid answers.
- Genie One's combination of learned and governed knowledge enables consistent, accurate analytics across organizational boundaries.

![figure](https://www.databricks.com/sites/default/files/blog_images/genie-one-accuracy-why-curated-agents-need-blog-img-1.png?v=1795119354)

![figure](https://www.databricks.com/sites/default/files/blog_images/genie-one-accuracy-why-curated-agents-need-blog-img-2.png?v=1795119354)

![figure](https://www.databricks.com/sites/default/files/blog_images/genie-one-accuracy-why-curated-agents-need-blog-img-3.png?v=1795119354)

#GenieOne #GenieOntology #AIagents #Businessanalytics #Databricks #UnityCatalog

---

*Source: [Genie One Accuracy: Why Curated Agents Need Governed Context](https://www.databricks.com/blog/genie-one-accuracy-why-curated-agents-need-governed-context)*
