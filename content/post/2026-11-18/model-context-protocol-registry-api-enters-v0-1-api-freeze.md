---
title: "Model Context Protocol Registry API Enters v0.1 API Freeze"
slug: "model-context-protocol-registry-api-enters-v0-1-api-freeze"
description: "The community-driven Model Context Protocol (MCP) registry service has launched in preview and its Registry API (v0.1) has entered an API freeze."
date: 2026-11-18T22:09:17+05:30
tags: [MCP, ModelContextProtocol, API, Registry, OpenSource]
categories: ["AI", "Software Development", "Artificial Intelligence", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/182288589?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Model Context Protocol Registry API Enters v0.1 API Freeze

The community-driven Model Context Protocol (MCP) registry service has launched in preview and its Registry API (v0.1) has entered an API freeze. 

## 🔍 Overview
- The MCP registry provides MCP clients with a list of MCP servers, functioning like an app store for MCP servers.
- The registry has launched in preview with an announcement blog post.
- While the system is now more stable, this is still a preview release and breaking changes or data resets may occur.
- A general availability (GA) release will follow later.

## ⚙️ Key details
- For the next month or more, the API will remain stable with no breaking changes, allowing integrators to confidently implement support.
- This freeze applies to v0.1 while development continues on v0.
- This period will be used to validate the API in real-world integrations and gather feedback to shape v1 for general availability.
- Publishing an MCP server does not happen through a pull request to the repository; adding a server.json, a server directory, or an entry in data/seed.json will not publish or list your server, even if the PR is merged.
- Users must use the mcp-publisher CLI from their server's own project instead.

## 🚀 Availability
- The registry uses ko to build container images, and pre-built Docker images are automatically published to GitHub Container Registry.
- Starting the registry at localhost:8080 with PostgreSQL uses ephemeral storage that resets each time containers are restarted.
- By default, the registry seeds from the production API with a filtered subset of servers to keep startup fast.
- The image does not bundle PostgreSQL, so users must run their own and point the registry at it via MCP_REGISTRY_DATABASE_URL.
- Setup can be configured with environment variables in docker-compose.yml, and .env.example provides a reference.
- Docker run commands are available for ghcr.io/modelcontextprotocol/registry:latest, :main, :v1.0.0, and :main-20250906-abc123d.

## 👥 Contributors
- Radoslav (Rado) Dimitrov (Stacklok) [@rdimitrov] - WG Lead
- Tadas Antanavicius (PulseMCP) [@tadasant]
- Bob Dickinson (TeamSpark) [@BobDickinson]
- Preeti (Pree) Dewani (Ravenmail) [@pree-dew]

## 💡 Collaboration
- Multiple channels are used for collaboration as detailed on modelcontextprotocol.io/community/communication.

#MCP #ModelContextProtocol #API #Registry #OpenSource

---

*Source: [modelcontextprotocol/registry](https://github.com/modelcontextprotocol/registry)*
