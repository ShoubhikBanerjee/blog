---
title: "Go client released for Qdrant vector search engine"
slug: "go-client-released-for-qdrant-vector-search-engine"
description: "The Go client for the Qdrant vector search engine has been released, making it easier for developers to integrate vector search capabilities into their Go applications. Internally, the high-level..."
date: 2026-11-18T06:16:59+05:30
tags: [Go, Qdrant, VectorSearch, gRPC, TLS, AI]
categories: ["AI", "Developer Tools", "AI Infrastructure", "Search Technology"]
image: "https://avatars.githubusercontent.com/u/73504361?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Go client released for Qdrant vector search engine

The Go client for the Qdrant vector search engine has been released, making it easier for developers to integrate vector search capabilities into their Go applications. Internally, the high-level client uses a low-level gRPC client to interact with Qdrant, abstracting away the complexity of direct API calls. The client supports secure communication with TLS 1.3 as the minimum required version when UseTLS is enabled.

## 📦 Availability

The client can be installed using the Go package manager:

- `go get -u github.com/qdrant/go-client`

## 🔐 Security

- Uses TLS 1.3 as the minimum security version when `UseTLS: true` is set

## 🧩 Architecture

- High-level client provides simplified API for common operations
- Low-level gRPC client handles direct communication with Qdrant server

## 💡 Why it matters

This release enables Go developers to leverage Qdrant's vector search capabilities without implementing low-level networking code, accelerating the development of AI and machine learning applications that require semantic search functionality.

#Go #Qdrant #VectorSearch #gRPC #TLS #AI

---

*Source: [qdrant/go-client](https://github.com/qdrant/go-client)*
