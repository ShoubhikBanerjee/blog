---
title: "Lakebase Postgres Introduces Read Replicas with Decoupled Compute and Storage"
slug: "lakebase-postgres-introduces-read-replicas-with-decoupled-compute-and-storage"
description: "Lakebase Postgres has introduced a new approach to read replicas that decouples compute from storage, enabling faster scaling and lower costs compared to traditional managed PostgreSQL services like..."
date: 2026-11-26T22:08:01+05:30
tags: [PostgreSQL, Database, Scalability, Lakebase, ComputeStorageDecoupling]
categories: ["AI", "Database Systems", "Cloud Infrastructure", "Software Architecture"]
image: "https://www.databricks.com/sites/default/files/2026-11/read-replicas-lakebase.png"
author: "Shoubhik Banerjee"
draft: false
---

# Lakebase Postgres Introduces Read Replicas with Decoupled Compute and Storage

Lakebase Postgres has introduced a new approach to read replicas that decouples compute from storage, enabling faster scaling and lower costs compared to traditional managed PostgreSQL services like Amazon RDS.

## 🔍 Overview

The traditional read replica model faces significant challenges when scaling reads on demand. In managed Postgres services, a replica is a physical clone of the primary: its own instance, storage volume, and full copy of every page. This makes replicas impractical for elastic scaling because they take minutes to hours to create, each adds a full data copy to billing, and they run continuously even after traffic spikes subside.

## 🧩 How it Works

Lakebase Postgres separates compute from storage. In traditional systems, Postgres runs on a single machine owning both execution and durable state. Lakebase splits these responsibilities: since compute owns nothing durable, multiple compute instances can attach to the same storage. A read replica is simply an independent, read-only compute that reads from the shared storage. Creating one requires no data copy, no replication work on the primary (which continues streaming WAL to safekeepers), and no dependency on database size—resulting in seconds-long creation times regardless of scale.

## ⚙️ Key Details

- In traditional setups, N replicas mean N+1 copies of the database (one on primary, one per replica volume)
- In Lakebase Postgres, N replicas still mean one storage copy
- Replicas maintain only local caches (shared buffers and NVMe), not durable data
- Storage is billed solely for the data in the storage layer; replicas add compute, not storage
- Replica costs follow the reads they serve, not database size or hourly instance billing

## 💡 Why It Matters

The monolithic implementation of replicas in systems like Amazon RDS creates the opposite of their intended purpose. Instead of elastic scaling, you get static, overprovisioned infrastructure. Lakebase’s decoupled architecture fixes both creation time and cost inefficiencies by treating replicas as lightweight compute instances rather than full database clones.

![figure](https://www.databricks.com/sites/default/files/inline-images/Untitled-design-11.gif?v=1795701905)

![figure](https://www.databricks.com/sites/default/files/inline-images/Untitled-design-13.gif?v=1795701905)

![figure](https://www.databricks.com/sites/default/files/inline-images/Untitled-design-15.gif?v=1795701905)

#PostgreSQL #Database #Scalability #Lakebase #ComputeStorageDecoupling

---

*Source: [Rethinking read replicas for the lakebase architecture](https://www.databricks.com/blog/rethinking-read-replicas-lakebase-architecture)*
