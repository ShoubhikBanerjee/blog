---
title: "Lakebase Postgres minimizes object‑storage reads using tiered caching"
slug: "lakebase-postgres-minimizes-objectstorage-reads-using-tiered-caching"
description: "Lakebase Postgres builds on object storage for durability while keeping reads off of it through a multi‑tier cache hierarchy."
date: 2026-11-17T22:09:21+05:30
tags: [Lakebase, Postgres, ObjectStorage, DatabaseArchitecture]
categories: ["AI", "Database Systems", "Storage Architecture", "Distributed Systems"]
image: "https://www.databricks.com/sites/default/files/2026-11/reads-served-from-cache-cover.png"
author: "Shoubhik Banerjee"
draft: false
---

# Lakebase Postgres minimizes object‑storage reads using tiered caching

Lakebase Postgres builds on object storage for durability while keeping reads off of it through a multi‑tier cache hierarchy.

## 🔍 Overview
- Object storage provides the foundation: durable, bottomless storage, instant branches and restores, and a single copy of data for transactions and analytics (LTAP).
- The system is designed so that object storage never sits in front of a query; reads travel through faster tiers first.

## 🧩 Architecture
| Tier | Role |
|---|---|
| Compute node | Runs standard Postgres, holds no durable state, serves ~99.46% of page accesses from its local cache (memory or micro‑second latency). |
| Pageserver | Owns local NVMe, serves ~0.54% of reads, builds an LSM tree, persists materialized history to object storage asynchronously. |
| Object storage | Holds immutable, long‑term history, backs pageservers, is accessed for only ~1 in 28 million page accesses. |

## ⚙️ Read Path Details
- On a compute‑node cache miss, the request is sent over the network to a pageserver, which serves the page from its own NVMe.
- Only if the pageserver also misses does the request reach object storage.
- Production statistics:
  - Compute cache: ~1.1 billion page accesses / s (99.46% of total).
  - Pageserver NVMe: ~6 million reads / s (0.54% of total).
  - Object storage: ~39 requests / s (≈1 in 28 million accesses).
- Reads that do reach object storage are rare one‑offs—old branches, restores, or databases that have been idle for weeks. Once cached, subsequent reads return to the faster tiers.

## 🚀 Availability & Durability
- Transactions are committed after a quorum of safekeepers acknowledges the record.
- A Paxos‑based protocol handles leader election and failover.
- Because the compute layer holds no durable state, it can start, stop, scale, or fail without risking data.
- The storage layer owns correctness, durability, and history.

## 💡 Why it matters
- By keeping the hot path in memory or NVMe, Lakebase Postgres achieves micro‑second latency comparable to a traditional warm‑cache Postgres instance.
- Object storage provides virtually unlimited capacity and durability without becoming a performance bottleneck.
- The tiered design ensures that even as data grows, the vast majority of reads stay on the fastest tier, making the system both scalable and responsive.


![figure](https://www.databricks.com/sites/default/files/inline-images/read-paths-lakebase.gif?v=1794924287)

![figure](https://www.databricks.com/sites/default/files/inline-images/build-page-at-LSN.gif?v=1794924287)

#Lakebase #Postgres #ObjectStorage #DatabaseArchitecture

---

*Source: [Built on object storage, served from cache](https://www.databricks.com/blog/built-object-storage-served-cache)*
