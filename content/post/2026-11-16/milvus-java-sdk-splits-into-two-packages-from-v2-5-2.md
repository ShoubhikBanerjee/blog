---
title: "Milvus Java SDK Splits Into Two Packages From v2.5.2"
slug: "milvus-java-sdk-splits-into-two-packages-from-v2-5-2"
description: "The Milvus Java SDK has been restructured starting with version 2.5.2. The SDK is now split into two separate packages: milvus-sdk-java and milvus-sdk-java-bulkwriter. This change was made because..."
date: 2026-11-16T22:14:27+05:30
tags: [Milvus, Java, SDK, AI, Development]
categories: ["AI", "Artificial Intelligence", "Software Development", "Machine Learning"]
image: "https://avatars.githubusercontent.com/u/51735404?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Milvus Java SDK Splits Into Two Packages From v2.5.2

The Milvus Java SDK has been restructured starting with version 2.5.2. The SDK is now split into two separate packages: milvus-sdk-java and milvus-sdk-java-bulkwriter. This change was made because BulkWriter requires a significant number of dependencies.

## 🧩 Available Packages

- **milvus-sdk-java**: The core Milvus Java SDK package
- **milvus-sdk-java-bulkwriter**: A separate package for BulkWriter functionality

## ⚙️ Key Details

The Milvus Java SDK has the following requirements:

- Java 8 or higher
- Build tools: Apache Maven or Gradle
- SLF4J is required for logging purposes and must be added to the classpath

Developers can add the Milvus SDK to their projects using either:

- Apache Maven
- Gradle

## 🚀 Availability

For Spring Boot applications (Java 17+), the `milvus-sdk-java-spring-boot-starter` package automatically configures a `MilvusClientV2` from `milvus.*` properties.

Examples for the Java SDK are available in the examples folder.

## 💡 Contributing

Contributors should:

- Read the contribution guidelines first
- Refer to the DEVELOPMENT.md file for development information

## 🛠️ Compatibility

The following table shows compatibilities between Milvus and Java SDK.

#Milvus #Java #SDK #AI #Development

---

*Source: [milvus-io/milvus-sdk-java](https://github.com/milvus-io/milvus-sdk-java)*
