---
title: "A2A Java SDK releases client and server support for agent communication"
slug: "a2a-java-sdk-releases-client-and-server-support-for-agent-communication"
description: "A new Java library has been released to support the execution of agentic applications as Agent2Agent (A2A) servers. This multi-module Maven library provides both client and server capabilities,..."
date: 2026-11-18T22:09:17+05:30
tags: [Java, AIagents, A2A, Maven, gRPC]
categories: ["AI", "AI Agents", "Developer Tools", "Programming Languages"]
image: "https://avatars.githubusercontent.com/u/217270365?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# A2A Java SDK releases client and server support for agent communication

A new Java library has been released to support the execution of agentic applications as Agent2Agent (A2A) servers. This multi-module Maven library provides both client and server capabilities, enabling A2A agent communication across JSON-RPC, gRPC, and REST transports.

## 🧩 How it works

The library facilitates agent-to-agent interaction by implementing the A2A Protocol. For gRPC support, the project copies the `a2a.proto` file from the A2A specification repository into the `spec-grpc/` project. The `java_package` option is adjusted to target the `org.a2aproject.sdk.grpc` package. Developers can regenerate the gRPC classes by building the module with the command `mvn clean install -Dskip.protobuf.generate=false`.

## ⚙️ Key details

- **Language Requirement**: Java 17 or later is required.
- **Transport Protocols**: Supports JSON-RPC, gRPC, and REST.
- **Licensing**: The project is licensed under the Apache 2.0 License.
- **Documentation**: Full documentation is available at a2aproject.github.io/a2a-java.

## 🚀 Availability and Integrations

Developers can add the A2A Java SDK reference server for JSON-RPC to their Maven projects. The SDK includes examples for cross-language integration, such as a Java A2A server communicating with a Python client, and a Java A2A client communicating with a Python server.

| Feature | Details |
| :--- | :--- |
| OpenTelemetry | Available as an optional add-on in the extras folder |
| JPA-backed task store | Available as an optional add-on in the extras folder |
| Kafka-based replicated queue manager | Available as an optional add-on in the extras folder |
| Vert.x and Android HTTP clients | Available as optional add-ons in the extras folder |

Integrations with Java runtimes are documented in the Server Integrations section of the reference materials.

#Java #AIagents #A2A #Maven #gRPC

---

*Source: [a2aproject/a2a-java](https://github.com/a2aproject/a2a-java)*
