---
title: "New Connector Enables Qdrant as a Storage Destination in Apache Spark"
slug: "new-connector-enables-qdrant-as-a-storage-destination-in-apache-spark"
description: "A new connector has been released that enables Qdrant to serve as a storage destination in Apache Spark, a distributed computing framework designed for big data processing and analytics."
date: 2026-11-22T12:09:58+05:30
tags: [Qdrant, ApacheSpark, VectorDatabase, BigData, DataEngineering]
categories: ["AI", "Big Data", "Vector Databases", "Data Integration"]
image: "https://avatars.githubusercontent.com/u/73504361?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Connector Enables Qdrant as a Storage Destination in Apache Spark

A new connector has been released that enables Qdrant to serve as a storage destination in Apache Spark, a distributed computing framework designed for big data processing and analytics.

## ⚙️ Key features

The connector supports several options for handling and structuring data:

* **Vector Ingestion**: The connector supports ingesting multiple named or unnamed, dense or sparse vectors.
* **Compatibility Options**: The `embedding_field` and `vector_name` options are maintained for backward compatibility. It is recommended to use `vector_fields` and `vector_names` for named vectors.
* **Collection Requirements**: Before loading data using the connector, a collection must be created in advance with the appropriate vector dimensions and configurations.

## 🚀 Setup and availability

To integrate the connector into a Spark environment, users must get the JAR file from one of the available sources:

* **Prepackaged JAR**: The packaged `jar` file can be found on GitHub Releases or Maven Central.
* **Building from Source**: Users can build the `jar` from source. This requires having JDK@8 and Maven installed. Running the build command in the project root writes the JAR file into the `target` directory by default.

#Qdrant #ApacheSpark #VectorDatabase #BigData #DataEngineering

---

*Source: [qdrant/qdrant-spark](https://github.com/qdrant/qdrant-spark)*
