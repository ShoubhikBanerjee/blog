---
title: "Rust SDK Adds Stable 2026-07-28 MCP Version with New Features"
slug: "rust-sdk-adds-stable-2026-07-28-mcp-version-with-new-features"
description: "This release brings the stable MCP 2026‑07‑28 specification to the Rust SDK, while remaining fully compatible with the 2025‑11‑25 release and earlier versions."
date: 2026-11-17T22:09:21+05:30
tags: [Rust, MCP, SDK, Async, JSON]
categories: ["AI", "Programming Languages", "Software Development", "Networking"]
image: "https://avatars.githubusercontent.com/u/182288589?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Rust SDK Adds Stable 2026-07-28 MCP Version with New Features

This release brings the stable MCP 2026‑07‑28 specification to the Rust SDK, while remaining fully compatible with the 2025‑11‑25 release and earlier versions.

## 🔍 Overview
- The SDK implements the stable MCP **`2026-07-28`** specification.
- It remains fully compatible with the **`2025-11-25`** release and previous versions.

## 🧩 Features
- Server discovery & negotiation
- Transport‑neutral subscriptions
- Long‑running tasks
- Response caching
- Multi‑round‑trip requests
- Standard HTTP routing headers

## ⚙️ SDK Structure
- Repository crates:
  - [rmcp](crates/rmcp): core crate providing the RMCP protocol implementation
  - [rmcp‑macros](crates/rmcp‑macros): procedural macro crate for generating RMCP tool implementations
- Basic dependencies:
  - [tokio](https://github.com/tokio-rs/tokio)
  - [serde](https://github.com/serde-rs/serde)
- JSON Schema generation (version 2020‑12):
  - [schemars](https://github.com/GREsau/schemars)

## 📦 Installation & Setup
- Add the latest published version:
  ```bash
  cargo add rmcp --features server
  ```
- Or use the dev channel:
  ```bash
  cargo add rmcp --features server --git https://github.com/modelcontextprotocol/rust-sdk --branch main
  ```

## 🚀 Server and Client Lifecycle
- `serve()` uses the legacy MCP lifecycle:
  - The client sends `initialize`.
  - The server returns negotiated server information.
  - The client sends `notifications/initialized`.
- Use `ClientServiceExt::serve_with_lifecycle` to select another lifecycle explicitly.
- `ClientLifecycleMode::Initialize` is equivalent to the existing `serve()` behavior.
- Discover startup does not send `notifications/initialized`; discovery completes startup.
- Each subsequent request carries its protocol version, client information, and capabilities in `_meta`.
- For a server, `serve()` waits for peer input that establishes the protocol lifecycle, such as `initialize` from a legacy client.
- A stdio MCP server is normally launched by an MCP client as a child process.
- Running the executable alone in a terminal can leave this await pending because no client has sent protocol messages yet.
- After `serve()` returns, the service handles messages in the background.
- You can run other asynchronous work, then use `waiting()` to wait for shutdown.
- To cancel during startup, use `serve_with_ct()`.

## 🛠️ Building a Service
- Use [`ServerHandler`](crates/rmcp/src/handler/server.rs) or [`ClientHandler`](crates/rmcp/src/handler/client.rs) to build a service.
- Await protocol startup, then receive a handle to the running service.


#Rust #MCP #SDK #Async #JSON

---

*Source: [modelcontextprotocol/rust-sdk](https://github.com/modelcontextprotocol/rust-sdk)*
