---
title: "Langfuse CLI v4 released with new commands and API versioning"
slug: "langfuse-cli-v4-released-with-new-commands-and-api-versioning"
description: "Langfuse has released a new CLI tool, `@langfuse/cli`, which allows users to interact with the Langfuse API directly from the command line. This new release includes updates to command aliases, input..."
date: 2026-11-20T22:08:48+05:30
tags: [Langfuse, CLI, API, DeveloperTools]
categories: ["AI", "Developer Tools", "APIs", "DevOps"]
image: "https://avatars.githubusercontent.com/u/134601687?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Langfuse CLI v4 released with new commands and API versioning

Langfuse has released a new CLI tool, `@langfuse/cli`, which allows users to interact with the Langfuse API directly from the command line. This new release includes updates to command aliases, input handling for complex JSON structures, and specific versioning rules for self-hosted versus cloud deployments.

## 📦 Package details
*   **Package name:** `@langfuse/cli`
*   **Executable:** `langfuse`
*   **Legacy name:** Previously published under `langfuse-cli`; the new name is recommended for all future use.

## ⚙️ Configuration and Host Selection
The CLI does not automatically read `.env` files. Users must manually configure API access and host selection. Host selection follows a specific priority order:

| Priority | Configuration Method |
| :--- | :--- |
| 1 | `LANGFUSE_BASE_URL` |
| 2 | `LANGFUSE_HOST` |
| 3 | EU default |

To authenticate, users create a project API key pair under **Project settings → API Keys**.

## 🧩 Command and Input Features
*   **Lossless input:** `--body-json` and `--body-file` flags provide a lossless input path for nested objects, arrays, unions, and free-form JSON.
*   **Pagination:** The CLI can fetch every page of a paginated list, supporting both page- and cursor-based endpoints, with a maximum of 1000 items.
*   **Aliases:** OpenAPI tags and explicit route versions remain accepted aliases (e.g., `scores-v3 list` for the canonical `scores list`).
*   **Schema:** Verbose OpenAPI `operationId` values are available in `api schema --json` but are never required as CLI commands.

## 🌐 Availability and Versioning
*   **V3 API Snapshots:** Available on self-hosted deployments only.
*   **Langfuse Cloud:** Supports v4 and up.
*   **Backward Compatibility:** Users can use an API snapshot compatible with an older self-hosted deployment.

#Langfuse #CLI #API #DeveloperTools

---

*Source: [langfuse/langfuse-cli](https://github.com/langfuse/langfuse-cli)*
