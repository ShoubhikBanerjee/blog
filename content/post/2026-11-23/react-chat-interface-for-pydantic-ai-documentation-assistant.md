---
title: "React Chat Interface for Pydantic AI Documentation Assistant"
slug: "react-chat-interface-for-pydantic-ai-documentation-assistant"
description: "A new React‑based chat interface for Pydantic AI has been released, powering the documentation assistant at ai.pydantic.dev/web/."
date: 2026-11-23T22:18:20+05:30
tags: [React, Pydantic, AI, VercelSDK]
categories: ["AI", "Artificial Intelligence", "Web Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/110818415?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# React Chat Interface for Pydantic AI Documentation Assistant

A new React‑based chat interface for Pydantic AI has been released, powering the documentation assistant at ai.pydantic.dev/web/.

## 🔍 Overview

- React chat UI built with Vercel AI SDK.
- Connects to Pydantic AI's streaming chat API.
- Used as documentation assistant.

## 🧩 Features

- Streaming message responses with reasoning display.
- Collapsible visualization of tool call input and output.
- Conversation persistence via IndexedDB, with migration from legacy localStorage.
- Dynamic model and tool selection.
- Dark and light theme support.
- Mobile‑responsive sidebar.

## ⚙️ Configuration

- Startup configuration must be set before the UI module script runs when served below a same‑origin path prefix.
- `basePath` controls conversation URLs and browser navigation.
- `apiPath` points to the directory containing configure and chat endpoints, independent of `basePath`.
- Both accept same‑origin paths and are normalized with a trailing slash.
- If not set, `basePath` defaults to the normalized Vite base (offline and CDN builds use `/`) and `apiPath` defaults to `/api/`.
- Configuration works when a server injects the script into the single‑file offline artifact at request time; the artifact does not need to be rebuilt.

| Parameter | Default when unset | Role |
|---|---|---|
| basePath | normalized Vite base (`/` for offline/CDN) | Controls conversation URLs and navigation |
| apiPath | `/api/` | Directory for configure and chat endpoints |

## 🚀 Development & Availability

- Install dependencies with `pnpm install`.
- Start the Python backend: `pnpm run dev:server` (requires agent/ setup).
- Start the Vite dev server: `pnpm run dev`.
- Released under the MIT License.

#React #Pydantic #AI #VercelSDK

---

*Source: [pydantic/ai-chat-ui](https://github.com/pydantic/ai-chat-ui)*
