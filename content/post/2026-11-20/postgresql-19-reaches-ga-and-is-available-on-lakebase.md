---
title: "PostgreSQL 19 reaches GA and is available on Lakebase"
slug: "postgresql-19-reaches-ga-and-is-available-on-lakebase"
description: "PostgreSQL 19 reached general availability today and is already available on Lakebase. Several engineers on the Lakebase team are PostgreSQL committers and contributors who worked on this release..."
date: 2026-11-20T12:08:10+05:30
tags: [PostgreSQL, Lakebase, Database, GARelease, REPACK, QueryPlanning]
categories: ["AI", "Database Management", "Cloud Services", "Software Release", "Data Infrastructure"]
image: "https://www.databricks.com/sites/default/files/2026-11/PG-19-cover.png"
author: "Shoubhik Banerjee"
draft: false
---

# PostgreSQL 19 reaches GA and is available on Lakebase

PostgreSQL 19 reached general availability today and is already available on Lakebase. Several engineers on the Lakebase team are PostgreSQL committers and contributors who worked on this release directly, from query plan advice to shared memory, locale handling, and release management. New major versions often take weeks to reach other managed PostgreSQL services.

## 🔍 Overview
PostgreSQL 19 is a practical release with no single headline feature that changes what PostgreSQL is. Instead, version 19 goes after operational problems that database teams know well:
- Bloated tables
- Unstable query plans
- Replica lag
- Incomplete statistics
- Maintenance work that is hard to run safely in production

## 🧩 Key Features
- **REPACK** — reclaims space while normal reads and writes continue during most of the operation
- **pg_plan_advice** — describes planner decisions as advice, applies supplied advice, and reports whether it was followed
- **pg_stash_advice** — stores advice by query ID and applies it automatically when a matching query is planned

## ⚙️ How REPACK Works
PostgreSQL uses multiversion concurrency control, so an UPDATE creates a new row version and a DELETE leaves a dead tuple behind. Routine vacuuming makes that space reusable, but it doesn't necessarily return space to the operating system or restore a useful physical row order. The usual fixes — VACUUM FULL, CLUSTER, or external tools such as pg_repack — take an ACCESS EXCLUSIVE lock for the whole operation, blocking normal access to the table.

REPACK reclaims space like VACUUM FULL; with `USING INDEX`, it also physically orders rows like CLUSTER. With `CONCURRENTLY`, PostgreSQL rebuilds the table while normal reads and writes continue, capturing ongoing changes through logical decoding. It then takes an ACCESS EXCLUSIVE lock to apply any remaining captured changes and swap the new table and index files into place.

| Component | Role |
|-----------|------|
| pg_plan_advice | Describes planner decisions as advice, applies supplied advice, reports whether it was followed |
| pg_stash_advice | Stores advice by query ID and applies it automatically when a matching query is planned |

These components do not add cross-table statistics or replace the planner. Instead, they let you intervene when an inaccurate estimate produces a poor plan. Unlike inline optimizer hints, plan advice lives outside the application's query text. You can inspect the current plan, test focused advice, and then stash it by query ID.

## ⚠️ REPACK Limitations
Concurrent repacking creates an additional replication slot for the duration of the operation, so it needs free capacity under `max_repack_replication_slots` and a table with either a non-deferrable primary key or a suitable index-based replica identity. It also needs temporary disk space for a copy of the table and all its indexes, potentially plus a sort file up to the size of the table.

Tables with heavy update and delete traffic face an additional limit: the current upstream PostgreSQL 19 implementation fails if more than about 104 million tuples in the target table are updated or deleted while REPACK (CONCURRENTLY) is running. This counts changes made during the repack, not rows already in the table.

Concurrent repacking is also not MVCC-safe: after it commits, transactions using snapshots taken before the repack began can see the table as empty. Physical clustering also degrades as later writes arrive. REPACK CONCURRENTLY still needs planning, but it brings into core a job that previously required more downtime or an extension.

## 🚀 Availability
To try it, create a new Lakebase project and select PostgreSQL 19 as the version.

![figure](https://www.databricks.com/sites/default/files/inline-images/Untitled-design-7_0.gif)

![figure](https://www.databricks.com/sites/default/files/2023-08/databricks-default.png?v=1712162038)

#PostgreSQL #Lakebase #Database #GARelease #REPACK #QueryPlanning

---

*Source: [PostgreSQL 19 is available on Lakebase](https://www.databricks.com/blog/postgresql-19-available-lakebase)*
