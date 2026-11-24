---
title: "Qdrant .NET Client Adds gRPC Support and TLS Configuration"
slug: "qdrant-net-client-adds-grpc-support-and-tls-configuration"
description: "A new .NET client library for Qdrant has been released, allowing .NET applications to connect to the vector database at `http://localhost:6334` using gRPC."
date: 2026-11-24T22:08:41+05:30
tags: [Qdrant, dotnet, gRPC, vectorsearch, TLS]
categories: ["AI", "Artificial Intelligence", "Data Engineering", "Software Development"]
image: "https://avatars.githubusercontent.com/u/73504361?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Qdrant .NET Client Adds gRPC Support and TLS Configuration

A new .NET client library for Qdrant has been released, allowing .NET applications to connect to the vector database at `http://localhost:6334` using gRPC.

## 🔍 Overview
- Install the library with `dotnet add package Qdrant.Client`.
- The client connects by default to Qdrant on `http://localhost:6334`.
- Internally, the high‑level client relies on a low‑level gRPC client to communicate with Qdrant.

## 🧩 How it works
- The client creates a channel via `QdrantChannel.ForAddress`, which is used by both `QdrantClient("localhost")` and the `ClientConfiguration` overloads.
- When the channel is created, the client automatically adds a `qdrant-dotnet/<version>` token to the request `User-Agent` alongside the gRPC library token.
- This token enables server‑side tooling to attribute traffic to the .NET client and its version.
- On .NET Framework, where the underlying channel handler must be configured manually, the token is **not** added automatically.

## ⚙️ Configuration options
- Additional constructor overloads give developers more control over gRPC client configuration.
- TLS can be configured, validating the server certificate using its thumbprint, and API‑key authentication can be added.
- .NET Framework has limited support for gRPC over HTTP/2, but support can be enabled by:
  - Referencing `System.Net.Http.WinHttpHandler` version 6.0.1 or later.
  - Configuring `WinHttpHandler` as the inner handler for `GrpcChannelOptions`.

## 🚀 Usage example
```csharp
await client.CreateCollectionAsync("my_collection", new VectorParams { Size = 100, Distance = Distance.Cosine });
// Query examples (illustrative):
// return the 5 closest points
// return the 5 closest points where rand_number >= 3
```

## 📡 Compatibility notes
- On .NET Framework, manual configuration of the channel handler is required, and the automatic `User-Agent` token is not added.
- The client works out‑of‑the‑box on platforms where gRPC over HTTP/2 is supported without additional handlers.


#Qdrant #dotnet #gRPC #vectorsearch #TLS

---

*Source: [qdrant/qdrant-dotnet](https://github.com/qdrant/qdrant-dotnet)*
