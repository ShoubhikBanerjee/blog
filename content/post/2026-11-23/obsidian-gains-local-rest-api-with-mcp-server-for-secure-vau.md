---
title: "Obsidian Gains Local REST API with MCP Server for Secure Vault Access"
slug: "obsidian-gains-local-rest-api-with-mcp-server-for-secure-vault-access"
description: "A new plugin provides a secure REST API and Model Context Protocol (MCP) server for Obsidian vaults, enabling scripts, browser extensions, and AI agents to interact directly with vault contents."
date: 2026-11-23T22:18:20+05:30
tags: [Obsidian, RESTAPI, MCP, Vault, Plugin]
categories: ["AI", "Software Plugins", "API Development", "Data Access", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/527661?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Obsidian Gains Local REST API with MCP Server for Secure Vault Access

A new plugin provides a secure REST API and Model Context Protocol (MCP) server for Obsidian vaults, enabling scripts, browser extensions, and AI agents to interact directly with vault contents.

## 🔍 Overview

The plugin exposes a secure, authenticated REST API alongside an MCP server, both serving the same core capabilities. All requests are served over HTTPS with a locally generated certificate and gated behind API key authentication.

## 🧩 How it works

The MCP server runs at https://127.0.0.1:27124/mcp/ and requires a bearer token in the Authorization header. A plain HTTP endpoint is also available at http://127.0.0.1:27123/mcp/ if enabled.

## ⚙️ Key details

- **Authentication**: HTTPS with locally generated certificate, API key authentication, bearer token for MCP clients
- **Certificate**: CA is name-constrained to localhost, 127.0.0.1, and configured hostnames; HTTP endpoint available for easier setup
- **Download CA**: Certificate authority available at https://127.0.0.1:27134/obsidian-local-rest-api.crt
- **Vault operations**: Full CRUD on any file including binary files, surgically patch specific sections (headings, blocks, frontmatter), search with full-text or JsonLogic queries, follow vault events via Server-Sent Events
- **Active file**: Read or write the currently open note in Obsidian
- **Commands**: List and execute any Obsidian command, query tags with usage counts, open specific files in UI
- **Extensibility**: Other plugins can register their own routes via an API extension interface

## 🚀 Availability

After installing and enabling the plugin, users can find their API key and certificate in Settings → Local REST API.

#Obsidian #RESTAPI #MCP #Vault #Plugin

---

*Source: [coddingtonbear/obsidian-local-rest-api](https://github.com/coddingtonbear/obsidian-local-rest-api)*
