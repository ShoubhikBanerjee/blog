---
title: ".NET SDK enables development of applications using the A2A v1.0 protocol"
slug: "net-sdk-enables-development-of-applications-using-the-a2a-v1-0-protocol"
description: "A new .NET SDK has been released that allows developers to build and host applications following the Agent2Agent (A2A) protocol, providing a robust implementation of the specification v1.0."
date: 2026-11-17T12:12:52+05:30
tags: [dotnet, AIagents, A2A, softwaredevelopment, protocol]
categories: ["AI", "AI Agents", "Software Development", "Protocols", "Programming"]
image: "https://avatars.githubusercontent.com/u/217270365?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# .NET SDK enables development of applications using the A2A v1.0 protocol

A new .NET SDK has been released that allows developers to build and host applications following the Agent2Agent (A2A) protocol, providing a robust implementation of the specification v1.0.

## 🧩 How it works
The library supports multiple communication methods, allowing agents to interact through message-based or task-based patterns. 
- Agent Capability Discovery: Retrieves agent capabilities and metadata through agent cards.
- Message-based Communication: Enables direct, stateless messaging with immediate responses.
- Task-based Communication: Allows for the creation and management of persistent, long-running agent tasks.
- Streaming Support: Facilitates real-time communication using Server-Sent Events.

## ⚙️ Key details
The SDK is built to integrate directly with web application stacks and supports multiple protocol bindings. 

| Component | Description |
| :--- | :--- |
| A2AClient | Primary client for making A2A requests to agents; supports streaming, non-streaming, and push notifications. |
| A2ACardResolver | Resolves agent card information from A2A-compatible endpoints. |
| A2AServer | Core server handling A2A JSON-RPC requests and coordinating task lifecycle. |
| IAgentHandler | Interface for agents to implement, providing methods for message handling and task cancellation. |
| TaskUpdater | API for emitting task lifecycle events such as start, complete, and fail. |
| MessageResponder | API for sending stateless message replies without task lifecycle management. |

All three protocol bindings—JSON-RPC, HTTP+JSON REST, and gRPC—share the same client contract and server pipeline. The gRPC binding is packaged as optional modules to prevent core consumers from being forced to depend on specific gRPC libraries.

## 🚀 Availability
The library targets .NET 8 and higher and includes built-in extensions for hosting A2A agents within web applications. 
- The v1.0 implementation is available as a NuGet package.
- A backward-compatible package is available during the transition period. 
- A configuration option allows developers to explicitly request a completed task response when calling v1 servers from v0.3 clients, which helps avoid returning an incomplete initial task snapshot.

#dotnet #AIagents #A2A #softwaredevelopment #protocol

---

*Source: [a2aproject/a2a-dotnet](https://github.com/a2aproject/a2a-dotnet)*
