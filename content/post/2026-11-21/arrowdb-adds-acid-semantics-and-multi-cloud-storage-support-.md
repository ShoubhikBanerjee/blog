---
title: "ArrowDB Adds ACID Semantics and Multi-Cloud Storage Support for Vector Databases"
slug: "arrowdb-adds-acid-semantics-and-multi-cloud-storage-support-for-vector-databases"
description: "A new update to a high-performance columnar storage engine built on Apache Arrow introduces ACID-like semantics and expanded cloud storage support, targeting vector databases and analytical workloads."
date: 2026-11-21T22:09:40+05:30
tags: [ApacheArrow, VectorDatabases, CloudStorage, CPlusPlus, DataEngineering]
categories: ["AI", "Data Storage", "Cloud Computing", "Databases", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/51735404?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ArrowDB Adds ACID Semantics and Multi-Cloud Storage Support for Vector Databases

A new update to a high-performance columnar storage engine built on Apache Arrow introduces ACID-like semantics and expanded cloud storage support, targeting vector databases and analytical workloads.

## 🔍 Overview

The update enhances the storage engine with manifest versioning and conflict resolution to provide ACID-like semantics. It is designed specifically for vector databases and analytical workloads, with a core implementation in C++ and bindings available for multiple languages.

## 🧩 How it works

The engine organizes columns into groups to optimize I/O and compression. It supports data-at-rest encryption and configurable compression. The primary format is Parquet, with additional support for Vortex and Lance formats.

## ⚙️ Key details

* **Core Implementation:** C++20 compiler required (GCC 10+, Clang 10+, Apple Clang 12+); CMake >= 3.20.0; Conan >= 2.0.
* **Language Bindings:**
    * Python: FFI bindings with PyArrow integration.
    * Java/Scala: JNI bindings.
    * Rust: DataFusion TableProvider integration.
    * C++: Primary core.
* **Data Integrity:** ACID-like semantics using manifest versioning and conflict resolution.

## 🚀 Availability

The engine supports major cloud storage providers, including:

* AWS S3 (including S3-compatible storage such as MinIO, Cloudflare R2, and RustFS)
* Google Cloud Storage
* Azure Blob Storage
* Aliyun OSS
* Tencent COS
* Huawei Cloud OBS

#ApacheArrow #VectorDatabases #CloudStorage #CPlusPlus #DataEngineering

---

*Source: [milvus-io/milvus-storage](https://github.com/milvus-io/milvus-storage)*
