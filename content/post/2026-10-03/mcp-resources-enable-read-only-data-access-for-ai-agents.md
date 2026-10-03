---
title: "MCP Resources Enable Read‑Only Data Access for AI Agents"
slug: "mcp-resources-enable-readonly-data-access-for-ai-agents"
description: "MCP Resources give your AI agents read-only access to live data, files, and APIs without bloating the context window."
date: 2026-10-03T22:03:57+05:30
tags: [MCP, AIAgents, Resources, TypeScriptSDK]
categories: ["AI", "Artificial Intelligence", "AI Agents", "Software Development", "Data Integration"]
image: "https://suhailroushan.com/og-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# MCP Resources Enable Read‑Only Data Access for AI Agents

MCP Resources give your AI agents read-only access to live data, files, and APIs without bloating the context window.

## 🔍 Overview
- "MCP Resources solve that by letting you register typed, fetchable data sources that the AI can pull on demand."
- "Everyone obsesses over tools (function calling) but forgets that resources handle the \"read\" side of the equation."

## 🛠️ Tools vs Resources
- "If your agent needs to check a user's subscription status, read a config file, or query a database — that's a resource, not a tool."
- "If your agent needs to write data, that's a tool, not a resource."

## ⚙️ How it works
- "The fastest way to see resources in action is with the official TypeScript SDK."
- "Run this with npx tsx server.ts and connect it to any MCP client (Claude Desktop, Cursor, or your own)."
- "The client can now fetch users://123/preferences and get structured JSON back."
- "They use URI templates (RFC 6570) so you can parameterize them."
- "This is how you expose database rows, file paths, or API endpoints."
- "The client can request repo://facebook/react/commits?limit=25 and the template handles the parsing."
- "Note that all params come back as strings — cast them explicitly."

## 📦 Data handling
- "Resources support any MIME type: text/plain, application/pdf, image/png."
- "The client decides what to do with it."
- "Static resources (registered with server.resource() without template params) are for fixed endpoints like config://app-settings."
- "Templates are for dynamic lookups."
- "Use static when you have one canonical source; use templates when the data space is unbounded."
- "Every resource fetch hits your backend."
- "If the data doesn't change often, cache it in‑memory with a TTL."

## ⚠️ Limitations & Best Practices
- "Resources add latency and complexity."
- "If your resource throws, the client gets a cryptic failure."
- "A resource returning a 10MB JSON blob will kill your context window."
- "Cap responses at 100KB and paginate if needed."
- "I log the URI, timestamp, and response size to a structured logger."
- "Wrap your stdio transport in an authenticated HTTP/SSE transport (like streamable-http ) and validate tokens before the request reaches your handlers."

#MCP #AIAgents #Resources #TypeScriptSDK

---

*Source: [MCP Resources: A Practical Guide for Full-Stack Developers](https://suhailroushan.com/blog/mcp-resources)*
