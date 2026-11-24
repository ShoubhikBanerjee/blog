---
title: "Databricks Launches Native Lakebase Sink for Apache Spark Structured Streaming"
slug: "databricks-launches-native-lakebase-sink-for-apache-spark-structured-streaming"
description: "Databricks has announced the general availability of a native Lakebase sink for Apache Spark™ Structured Streaming, simplifying real-time data ingestion into its serverless PostgreSQL offering. The..."
date: 2026-11-24T06:12:57+05:30
tags: [Databricks, Lakebase, ApacheSpark, RealTimeStreaming, FeatureEngineering]
categories: ["AI", "Database", "Streaming Analytics", "Machine Learning", "Data Engineering"]
image: "https://www.databricks.com/sites/default/files/2026-11/lakebase-sink-optB-pipeline-2400x1256.png"
author: "Shoubhik Banerjee"
draft: false
---

# Databricks Launches Native Lakebase Sink for Apache Spark Structured Streaming

Databricks has announced the general availability of a native Lakebase sink for Apache Spark™ Structured Streaming, simplifying real-time data ingestion into its serverless PostgreSQL offering. The connector eliminates the need for custom foreach writers, reducing complexity in building low-latency feature pipelines for use cases like fraud detection and recommendation systems.

## 📣 What Happened
Today, Databricks is releasing the native Lakebase sink for Apache Spark™ Structured Streaming. This connector writes computed results directly to Lakebase and handles batching, retries, and upserts automatically, removing the burden of building and maintaining custom infrastructure.

## 🔍 Why It Matters
Low-latency use cases such as fraud detection, live personalization, and real-time feature computation require results in a serving-ready OLTP store. Lakebase Postgres is a fully managed, serverless PostgreSQL database with autoscaling, branching, native Unity Catalog integration, and sub-10ms reads. Previously, writing to Lakebase from a streaming pipeline required developers to build custom foreach writers to manage batching, retries, and upserts — a complex task that was difficult to scale and maintain.

The new native sink handles these concerns internally. You can wire up a Lakebase write in minutes with a single `writeStream` call, without needing to manage performance, tuning, or maintenance.

## ⚙️ Key Features
- Fully managed, serverless PostgreSQL database with autoscaling and native Unity Catalog integration
- Sub-10ms read latency
- Native Lakebase sink for Apache Spark™ Structured Streaming
- Supports both micro-batch and Real-Time Mode
- Automatic upsert handling with `upsertKey` — maintains one row per key
- Built-in connection pooling, batching, and retries
- Seamless credentials management via running user or service principal
- Table creation if it does not exist
- Real-time data ingestion using `.toTable()` for Unity Catalog-registered tables
- Direct write using `format("postgresql")` for non-Unity Catalog tables or external PostgreSQL databases

## 🧩 Use Case Example: Real-Time Recommendation Features
A video streaming platform wants to recommend videos by leveraging users' recent activity. The pipeline ingests WATCH and LIKE events from Kafka, computes the last 6 videos watched and the last 3 liked per user, and upserts one feature row per user into Lakebase in hundreds of milliseconds. At inference time, a recommendation model looks up each user’s feature row by `user_id` to rank what to show next.

The pipeline uses `transformWithState` to maintain per-user state and emit one feature row per user, with writing to Lakebase handled by a single `writeStream` and `.toTable()` call.

## 🚀 Availability and Benchmarks
The native sink is now generally available. In testing, the pipeline processed ~20K events per second against 5 million active users using a 40-core classic compute (DBR 18 LTS) writing to an 8-CU Lakebase project with 5-minute RTM checkpoint intervals. End-to-end latency from Kafka input timestamp to row landing in Lakebase was 100–200 milliseconds, with query latency in single digits via Lakebase.

## 💬 Customer Feedback
- "We stream real-time data into Lakebase so our risk agent can pull a user's recent activity when it investigates an alert. We initially built that path with a custom ForeachWriter, which meant building and maintaining the write infrastructure ourselves. As part of our development work, we found that the native sink reduces the custom work required for connection pooling, batching, and retries." — Maria Marinova, Sr. Lead Software Engineer, DraftKings
- "Testing real-time data flows into Lakebase is an important part of validating how our risk agent can quickly access the freshest available user data when making decisions. As we evaluated the native sink, we found that its built-in connection pooling, batching, and retries reduce the custom infrastructure we need to build and maintain." — Georgi Stoychev, Sr. Software Automation Engineer, DraftKings

## 📊 Technical Details
| Feature | Description |
|---------|-------------|
| Upsert Key | Sink maintains one row per key |
| Connection Pooling | Built-in, managed automatically |
| Batching | Automatically handled for throughput |
| Retries | Transient failure handling with backoff |
| Credentials | Managed as running user or service principal |
| Table Creation | Automatically created if not present |
| Latency | End-to-end 100–200ms; query latency single-digit milliseconds |

## 🔗 Getting Started
For a deeper look at the implementation, see the companion repo — a self-serve example you can run end-to-end.

Image: https://www.databricks.com/sites/default/files/2023-08/databricks-default.png?v=1712162038

![figure](https://www.databricks.com/sites/default/files/2023-08/databricks-default.png?v=1712162038)

#Databricks #Lakebase #ApacheSpark #Real-TimeStreaming #FeatureEngineering

---

*Source: [Announcing General Availability of native Lakebase Postgres sink for Spark Structured Streaming](https://www.databricks.com/blog/announcing-general-availability-native-lakebase-postgres-sink-spark-structured-streaming)*
