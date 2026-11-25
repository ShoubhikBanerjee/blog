---
title: "Cloudflare launches Search for Agents to enable AI-powered site search"
slug: "cloudflare-launches-search-for-agents-to-enable-ai-powered-site-search"
description: "Cloudflare today introduced Search for Agents, a new toggle in the Cloudflare dashboard that creates an AI Search instance for a zone, indexes its content, and makes the search API available from the..."
date: 2026-11-25T22:10:10+05:30
tags: [Cloudflare, SearchForAgents, AIsearch]
categories: ["AI", "Cloud Computing", "Artificial Intelligence", "Search Technology"]
image: "https://blog.cloudflare.com/_emdash/api/media/file/01M87EHBMCJY691A3ADBXCMG6A.png"
author: "Shoubhik Banerjee"
draft: false
---

# Cloudflare launches Search for Agents to enable AI-powered site search

Cloudflare today introduced Search for Agents, a new toggle in the Cloudflare dashboard that creates an AI Search instance for a zone, indexes its content, and makes the search API available from the customer’s own domain.

## 🔍 Overview
- Search for Agents is activated via a toggle in the Cloudflare dashboard.
- It is available to all customers, including the Free plan (with limits).
- Enabling the feature causes Cloudflare to create an AI Search instance, start indexing the zone’s content, and expose a searchable endpoint under the customer’s domain.

## 🧩 How it works
- The feature can be turned on from the Quick Actions section of the zone page or via the API.
- Once enabled, Cloudflare automatically creates the AI Search instance with default settings and begins crawling the site.
- The search endpoint is advertised on every page of the site to facilitate discoverability.
- If Markdown for Agents is also enabled, a request with `Accept: text/markdown` returns the same information in YAML front‑matter, allowing agents to pick up instructions easily.
- Depending on the AI Search configuration, agents may query the endpoint using natural‑language questions.

## ⚙️ Configuration
- The default AI Search instance can be re‑configured at any time, such as enabling reranking or changing cache settings.
- Search usage is subject to the zone’s domain settings, including bot‑management rules, AI Crawl Control, and Web Application Firewall configurations.

## 🚀 Availability
- Search for Agents can be enabled through the dashboard toggle or programmatically via the API.
- The feature is offered to all customers, including those on the Free tier, though the Free tier operates under unspecified limits.

## 💡 Benefits
- Provides a network‑level AI search API that any agent can discover and use without manual index setup.
- Keeps search functionality under the customer’s own domain, preserving control over security and traffic policies.
- Reduces operational overhead by automatically handling crawling, indexing, and endpoint advertisement.


#Cloudflare #SearchForAgents #AIsearch

---

*Source: [Introducing Search for Agents](https://blog.cloudflare.com/search-for-agents/)*
