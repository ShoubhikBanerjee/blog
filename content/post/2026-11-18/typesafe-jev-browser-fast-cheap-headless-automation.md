---
title: "TypeSafe Jev Browser: Fast, Cheap, Headless Automation"
slug: "typesafe-jev-browser-fast-cheap-headless-automation"
description: "TypeSafe released a new tool that lets developers drive a real headless browser with minimal cost and effort."
date: 2026-11-18T06:16:59+05:30
tags: [JevBrowser, HeadlessAutomation, TypeSafe, NodeJS, WebAutomation]
categories: ["AI", "Web Automation", "Cloud Services", "Browser Automation", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/260253?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# TypeSafe Jev Browser: Fast, Cheap, Headless Automation

TypeSafe released a new tool that lets developers drive a real headless browser with minimal cost and effort.

## 🔍 Overview
- Provides fast and very cheap browser use via TypeSafe's Jev model.
- Accepts a task and a URL, and drives a real headless browser through an MCP server, CLI, or library.
- Returns the final page, a step trace with confidences, console errors, and a screenshot.

## 🧩 How it Works
- TypeSafe's Jev model picks one action per step from the page's clickable, typeable, and selectable elements, and scores how likely it is that the goal is met or the run is stuck.
- Code owns the loop, managing budgets, recovery, and stop gates.

## ⚙️ Key Details
| Env Variable | Description |
|--------------|-------------|
| `JEV_BROWSER_SKIP_BROWSER_DOWNLOAD` | set to 1 to opt out of automatic Playwright Chromium download |
| `JEV_BROWSER_AUTH_TOKEN` | required unless `HOST` is loopback |
| `JEV_BROWSER_MAX_CONCURRENCY` | default 4; limits concurrent browsers |
| `JEV_BROWSER_TRANSPORT` | set to `http` to use HTTP transport |
| `HOST` | defaults to `127.0.0.1`; set to `0.0.0.0` to serve beyond your machine |
| `PORT` | default `8080` |
| `JEV_BROWSER_MAX_SECONDS` | default `180`, capped at `600` |

- Listens on `PORT` (default `8080`) and serves MCP at `/mcp`, with a health check at `/health`.
- `--http` and `JEV_BROWSER_TRANSPORT=http` are equivalent; containers and service units can select the transport without argv.
- It speaks MCP `2026-07-28` and falls back to stateless serving for `2025`‑era clients, keeping no sessions so any number of replicas can sit behind a plain load balancer.
- Each in‑flight call runs its own headless Chromium for up to its time budget (`max_seconds`, default `180`, cap `600`). Admitted requests are capped at `JEV_BROWSER_MAX_CONCURRENCY` (default `4`; excess gets `429`).
- Reverse proxy or load balancer read timeouts must be at least as long as the largest `max_seconds` you allow, or it will cut healthy runs short.
- The server itself speaks plain HTTP; terminate TLS at a reverse proxy or load balancer before exposing it beyond loopback, and put connection limits and request rate limits at that ingress.

## 🚀 Availability
- Requires Node.js 22 or newer.
- Install from npm; Playwright's Chromium downloads automatically on install unless `JEV_BROWSER_SKIP_BROWSER_DOWNLOAD=1`.
- The service listens on `PORT` (default `8080`) and serves MCP at `/mcp`.
- No session state; any number of replicas can sit behind a plain load balancer.

## 💡 Examples
- Navigated Wikipedia from the Coffee article to Espresso in about 4 seconds, for $0.0016.
- Pulled the price off a live pricing page.
- Returned a full guide page as markdown.
- Produced an accessibility‑tree breakdown of a WordPress site.
- Filled a contact form and stopped without submitting it.

#JevBrowser #HeadlessAutomation #TypeSafe #NodeJS #WebAutomation

---

*Source: [jkudish/jev-browser](https://github.com/jkudish/jev-browser)*
