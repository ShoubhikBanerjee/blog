---
title: "Autumn-27 ARTEX Open-Source Fork Now Maintained by ChainReactors"
slug: "autumn-27-artex-open-source-fork-now-maintained-by-chainreactors"
description: "The Autumn-27/ARTEX project, an AI autonomous penetration testing system originally built with a Go backend and Next.js frontend, has seen its open-source continuation. The repository RuoJi6/ARTEX is..."
date: 2026-11-26T18:08:23+05:30
tags: [ARTEX, PenetrationTesting, OpenSource, SecurityTools, ChainReactors]
categories: ["AI", "Cybersecurity", "Open Source", "AI Agents", "Development Tools"]
image: "https://avatars.githubusercontent.com/u/79234113?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Autumn-27 ARTEX Open-Source Fork Now Maintained by ChainReactors

The Autumn-27/ARTEX project, an AI autonomous penetration testing system originally built with a Go backend and Next.js frontend, has seen its open-source continuation. The repository RuoJi6/ARTEX is a fork of the original Autumn-27/ARTEX, preserving the upstream commit history and AGPL-3.0 license. It is now maintained by ChainReactors.

## 🧩 How it works
The system integrates with external data sources to streamline asset collection. Specifically, it supports direct synchronization of asset data from ScopeSentry, eliminating the need for manual repeated collection. Users configure the ScopeSentry address and API key on the "Asset Sync" page, select targets and asset types (such as domains, subdomains, IPs, ports, sites, or endpoints) by project or task dimension, and import data to merge it into the ARTEX asset graph for agent exploration.

## ⚙️ Key details
*   **Database & LLM:** The system depends on PostgreSQL and requires an LLM configuration for exploration, supporting either `ANTHROPIC_API_KEY` or `OPENAI_API_KEY` (configurable via CLI or UI).
*   **MCP Support:** Remote MCP can be configured in system settings using `http` (Streamable HTTP) or `sse` (legacy SSE).
*   **Dockerization:** The `ruoji6/artex` Docker image is built and published via GitHub Actions. It includes common tools like ripgrep, curl, vim, npm, and nmap. The image supports `linux/amd64` and `linux/arm64` architectures, with Docker automatically selecting the matching host architecture.
*   **Persistence:** The `./skills` and `./data` directories are persisted via bind mounts.

## 🚀 Availability
*   **Docker Setup:** The installation script automatically detects and installs Docker. Users can choose between "All Docker" (which generates a `.env` file and runs `docker compose up -d`) or local compilation. 
*   **Local Setup:** For local runs, users select a database option, generate a `config.json`, and compile an embedded single binary. 
*   **Access:** After installation, the service is accessible at `http://localhost:8787`, requiring an initial setup at `/setup` to set the admin password.
*   **Download:** Release packages are available for download from the repository's Releases page. Linux ARM64 users (including ARM64 Kali) should select the `linux-arm64` build, while x86_64 users select `linux-amd64`. 
*   **Execution:** Users must launch the application using `start.sh` or `start.bat` rather than running `./artex` directly. These scripts act as daemons that restart the program based on exit codes, which is required for the "one-click update" feature to function correctly.

#ARTEX #PenetrationTesting #OpenSource #SecurityTools #ChainReactors

---

*Source: [RuoJi6/ARTEX](https://github.com/RuoJi6/ARTEX)*
