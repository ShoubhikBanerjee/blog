---
title: "Databricks adopts adaptive concurrency limits for cluster creation"
slug: "databricks-adopts-adaptive-concurrency-limits-for-cluster-creation"
description: "Databricks' Compute Platform team applied adaptive concurrency limits to cluster creation to address the shortcomings of fixed request‑rate limits for long‑running operations."
date: 2026-11-18T18:09:03+05:30
tags: [Databricks, ConcurrencyLimits, ClusterCreation, CloudInfrastructure]
categories: ["AI", "Cloud Computing", "Infrastructure Engineering", "Distributed Systems"]
image: "https://www.databricks.com/sites/default/files/2026-11/blog-og-how-we-raised-databricks-cluster-rate-limits-by-7.5x.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks adopts adaptive concurrency limits for cluster creation

Databricks' Compute Platform team applied adaptive concurrency limits to cluster creation to address the shortcomings of fixed request‑rate limits for long‑running operations.

## 🔍 Overview
We turn cloud infrastructure into clusters ready to run customer workloads. Our day‑to‑day work includes provisioning virtual machines and coordinating cluster creation across AWS, Azure, and Google Cloud.

## 🛠️ How it works
- A request‑rate limiter at the API entry point caps requests per time window.
- For cluster creation, the handler validates the request, records a work item, and returns.
- A background workflow coordinates services, updates state, and provisions resources such as cloud virtual machines.
- These operations complete asynchronously, and their duration depends on the health and capacity of their dependencies.

## ⚙️ Key details
- "Conservative limits turned away customer requests despite spare capacity, yet kept accepting requests when our services or dependencies, such as cloud providers, slowed down."
- Engineers manually lowered limits to shed load during incidents and raised them again after recovery.
- Adaptive concurrency limits account for both unfinished work and changing system health.
- "For long‑running operations, a fixed request rate is a poor model of capacity."
- Limiting active workflows helps contain pressure and gives unfinished work a chance to drain.

## 📊 Definitions
| Limit type | Description |
|---|---|
| Request-rate limit | A cap on requests accepted per unit time, such as 10 requests per second, with a possible burst allowance. |
| Concurrency limit | A cap on active operations, such as 100 at once. |

## 💡 Why it matters
- The goal is to let customers run at full throttle when capacity allows, then ease off enough to keep useful work moving during degradation.
- Fixed limits can reject work even when capacity exists, while adaptive limits adjust to system health.
- A retry storm can sustain overload after traffic normalizes because internal retries bypass the request‑rate limiter.
- Adaptive limits provide a final safety guardrail via a fixed API request‑rate ceiling while dynamically managing active workflow count.

![figure](https://www.databricks.com/sites/default/files/blog_images/how-we-raised-databricks-cluster-rate-limits-blog-img-1.png)

![figure](https://www.databricks.com/sites/default/files/blog_images/how-we-raised-databricks-cluster-rate-limits-blog-img-2.png)

![figure](https://www.databricks.com/sites/default/files/blog_images/how-we-raised-databricks-cluster-rate-limits-blog-img-3.png)

#Databricks #ConcurrencyLimits #ClusterCreation #CloudInfrastructure

---

*Source: [How we raised Databricks cluster rate limits by 7.5×](https://www.databricks.com/blog/how-we-raised-databricks-cluster-rate-limits-75)*
