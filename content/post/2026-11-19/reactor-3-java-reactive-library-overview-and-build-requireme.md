---
title: "Reactor 3 Java Reactive Library Overview and Build Requirements"
slug: "reactor-3-java-reactive-library-overview-and-build-requirements"
description: "Reactor 3 is a non-blocking Reactive Streams foundation for the JVM, implementing a Reactive Extensions-inspired API with efficient event streaming support."
date: 2026-11-19T22:12:49+05:30
tags: [ReactiveProgramming, Java, JVM, Reactor, ReactiveStreams]
categories: ["AI", "Software Development", "Java", "Reactive Programming", "JVM"]
image: "https://avatars.githubusercontent.com/u/4201559?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Reactor 3 Java Reactive Library Overview and Build Requirements

Reactor 3 is a non-blocking Reactive Streams foundation for the JVM, implementing a Reactive Extensions-inspired API with efficient event streaming support.

## ⚙️ Key details
- **Reactor 3 requires Java 8 or higher to run.**
- Reactor 3 does not officially support nor target Android.
- However, it should work fine with Android SDK 21 (Android 5.0) and above.
- Since `3.3.x`, the repository also contains `reactor-tools`, a Java agent aimed at helping with debugging of Reactor code.

## 🧩 How it works
Reactor functions as a Reactive Streams Publisher with basic flow operators. Its architecture includes:
- **Static factories on Flux**: Allow for source generation from arbitrary callback types.
- **Instance methods**: Allow for operational building, materialized on each subscription (such as `Flux#subscribe()`), or multicasting operations (such as `Flux#publish` and `Flux#publishNext`).

## 🚀 Availability and Build
The build process involves specific Java Development Kit (JDK) requirements due to support for Java Multi-Release JAR Files.

| Requirement | Detail |
| :--- | :--- |
| **Classpath JDKs** | JDK 8, 9, and 21 must be available. |
| **Toolchain Management** | Gradle Toolchains should automatically detect or provision the required JDKs. |
| **Active Shell JDK** | Must be compatible with JDK 17 or higher for Antora to build successfully. |
| **Missing JDK Errors** | Errors like `No matching toolchains found for requested specification` indicate a missing JDK that needs to be installed. |

Documentation is generated in `docs/build/site/index.html` and in `docs/build/distributions/reactor-core-<version>-docs.zip`. If a PDF file is included in the generated docs zip, the `-PforcePdf` option must be specified, which requires the `asciidoctor-pdf` command to be available in the PATH.

#ReactiveProgramming #Java #JVM #Reactor #ReactiveStreams

---

*Source: [reactor/reactor-core](https://github.com/reactor/reactor-core)*
