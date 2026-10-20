---
title: "Strategy Mosaic powers agentic AI on AWS via Amazon Bedrock AgentCore"
slug: "strategy-mosaic-powers-agentic-ai-on-aws-via-amazon-bedrock-agentcore"
description: "The latest walkthrough shows how Strategy Mosaic can serve as a semantic layer for agentic AI on AWS, letting a Strands agent hosted on Amazon Bedrock AgentCore query a Customer‑360 (C360) domain..."
date: 2026-10-20T22:03:21+05:30
tags: [AIagents, SemanticLayer, AWS, Bedrock, StrategyMosaic]
categories: ["AI", "Artificial Intelligence", "Data Management", "Cloud Computing", "Enterprise AI"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21332-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Strategy Mosaic powers agentic AI on AWS via Amazon Bedrock AgentCore

The latest walkthrough shows how Strategy Mosaic can serve as a semantic layer for agentic AI on AWS, letting a Strands agent hosted on Amazon Bedrock AgentCore query a Customer‑360 (C360) domain across Amazon Redshift and Amazon Aurora without ETL.

## 🔍 Overview
- This post is co‑written with Zhili Cheng, Principal Product Manager, George Earle, Director, AI Engineering, and Kyler K, Sales Engineer of Strategy.
- Mosaic implements a **dimensional** semantic model – attributes, hierarchies, facts and metrics – composed through Strategy’s metric expression syntax.
- A single Mosaic definition publishes **four native protocols**: 
  - Model Context Protocol (MCP) for AI agents
  - JDBC/ODBC over Trino for SQL clients
  - XMLA for Power BI and Excel
  - REST for custom applications
- The walkthrough reuses the C360 pattern introduced in earlier posts that used Stardog and Denodo, but now applies Mosaic’s **linked‑model** pattern.

## 🧩 How it works
- Two Mosaic Models are created – one over Amazon Redshift, one over Amazon Aurora – and linked together.
- **Metric syntax** supports:
  - Base metrics (e.g., `Purchase Amount = price * quantity`)
  - Advanced metrics with named filter objects and level qualifiers
  - Compound metrics that combine other metrics
- The Strands agent reaches Mosaic through the **MCP endpoint**; joins, metric definitions, and per‑caller row and column filters reside in Mosaic, not in the prompt.
- User identity flows from the enterprise identity provider through **AgentCore Identity**, enabling **Row‑Level Security (RLS)** and **Object‑Level Security (OLS)** to be enforced end‑to‑end.
- Execution can be tuned between **live pushdown** (leveraging the underlying warehouse) and **in‑memory** execution for agent traffic.
- The same governed definitions can be published to Power BI, Tableau, notebooks, and custom apps, and exported in **Apache Ossie** format for tools outside Mosaic.

## ⚙️ Key details
| Item | Details |
|------|---------|
| **Semantic layer type** | Dimensional (attributes, hierarchies, facts, metrics) |
| **Modeling path** | Mosaic Models (self‑service, AI‑assisted) inherit dimensions, ACLs, RLS from Mosaic Schema |
| **Forms** | ID form for joins, display form for reading; forms resolve names like “Carolyn Inworth” to the underlying `cid` |
| **Supported systems** | Cloud warehouses: Snowflake, Databricks; Operational databases: Amazon RDS, Oracle, SQL Server; Analytical engines: Amazon Athena, Trino, SAP HANA; SaaS sources: Salesforce |
| **Protocols** | MCP for agents, JDBC/ODBC over Trino for SQL, XMLA for Power BI/Excel, REST for custom apps |
| **Source of truth** | Strategy One (March 2026) release – Mosaic access through the MCP server is enabled by default |

## 🚀 Availability
- The walkthrough runs on AWS services: Amazon Redshift Serverless for analytical C360 data, Amazon Aurora PostgreSQL as the operational system of record, and Amazon Bedrock AgentCore hosting the Strands agent.
- Deployment uses the native AWS data services; no ETL is required to keep the analytical copy current.
- The MCP server is available by default in the Strategy One release.

---
*This post continues the series that previously demonstrated semantic layers built with Stardog’s ontology‑based knowledge graph and Denodo’s data‑virtualization platform.*

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21332-1-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21332-2-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/05/ML-21332-3-1.png)

#AIagents #SemanticLayer #AWS #Bedrock #StrategyMosaic

---

*Source: [Build a semantic layer for agentic AI on AWS with Strategy Mosaic and Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-semantic-layer-for-agentic-ai-on-aws-with-strategy-mosaic-and-amazon-bedrock-agentcore/)*
*Source: [Build a semantic layer for agentic AI on AWS with AtScale and Amazon Bedrock AgentCore | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/build-a-semantic-layer-for-agentic-ai-on-aws-with-atscale-and-amazon-bedrock-agentcore/)*
