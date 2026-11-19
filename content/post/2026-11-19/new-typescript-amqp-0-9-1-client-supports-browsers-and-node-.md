---
title: "New TypeScript AMQP 0-9-1 Client Supports Browsers and Node.js"
slug: "new-typescript-amqp-0-9-1-client-supports-browsers-and-node-js"
description: "A new TypeScript client for AMQP 0-9-1 has been released, supporting both Node.js and browsers via WebSocket. Developed and supported by CloudAMQP, the library is designed to replace other Node.js..."
date: 2026-11-19T22:12:49+05:30
tags: [AMQP, TypeScript, WebSockets, RabbitMQ, Messaging, CloudAMQP]
categories: ["AI", "Messaging", "Developer Tools", "Web Development", "Backend Infrastructure"]
image: "https://avatars.githubusercontent.com/u/1513401?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New TypeScript AMQP 0-9-1 Client Supports Browsers and Node.js

A new TypeScript client for AMQP 0-9-1 has been released, supporting both Node.js and browsers via WebSocket. Developed and supported by CloudAMQP, the library is designed to replace other Node.js AMQP libraries and enables developers to write browser applications that communicate directly with AMQP servers.

## 🔍 Overview
The library is Promise-based, integrating well with async/await, and works with any AMQP 0-9-1 broker, including RabbitMQ, LavinMQ, and Apache Qpid. It supports self-hosted instances and managed providers such as CloudAMQP or Amazon MQ, as they all use the same protocol. The codebase is transpiled from TypeScript, and running Node with the `--enable-source-maps` flag ensures proper stack traces.

## 🧩 How it works
The library offers two levels of abstraction:
*   **High-level (AMQPSession):** Provides automatic reconnection and consumer recovery. Users utilize `queue()` and `exchange()` handles for reconnect-safe operations.
*   **Low-level (AMQPClient / AMQPWebSocketClient):** Offers direct channel access with methods such as `queueDeclare`, `basicPublish`, and `basicConsume`.

The transport mechanism is determined by the URL scheme: `amqp://` or `amqps://` utilizes TCP, while `ws://` or `wss://` uses WebSocket. To establish a session with automatic reconnection and consumer recovery, developers call `AMQPSession.connect(url, options)`.

## ⚙️ Key details
The library is secure by default; publishes are not fulfilled until data is sent on the wire or, if Publish Confirms are enabled on the channel, until the server acknowledges that the message has been enqueued.

**Message Acknowledgement**
*   Messages are acknowledged after the callback returns.
*   If the callback throws, the message is negatively acknowledged (nacked) and requeued.
*   Developers can override this behavior by calling `msg.ack()` or `msg.nack()` directly.
*   Subscriptions created via `queue.subscribe()` are automatically re-established after a reconnection.
*   The `sub.consumerTag` and `sub.channel` properties reflect the current consumer and are updated upon reconnection.
*   Prefetch parameters in subscribe settings can be used to configure Quality of Service (QoS) on each connection.

**Codec Registry**
Developers can opt into a codec registry to handle serialization and deserialization based on content-type and content-encoding:
*   Built-in parsers support JSON and text; built-in coders support gzip and deflate.
*   Defaults can be set to avoid repeating configurations on every publish.
*   When codecs are configured, `msg.body` contains the decoded value; otherwise, it is a `Uint8Array`. The `CodecMode` generic infers this type at compile time.
*   Specific publishes can override defaults by passing `contentType` or `contentEncoding` in the options.
*   Custom codecs can be registered by merging them with the built-ins.
*   Decode failures surface as a plain `Error` rather than an `AMQPError`; in `subscribe()` contexts, these failures nack the message, honoring `requeueOnNack`.

#AMQP #TypeScript #WebSockets #RabbitMQ #Messaging #CloudAMQP

---

*Source: [cloudamqp/amqp-client.js](https://github.com/cloudamqp/amqp-client.js)*
