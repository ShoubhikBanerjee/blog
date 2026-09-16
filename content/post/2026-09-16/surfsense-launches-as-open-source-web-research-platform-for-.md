---
title: "SurfSense Launches as Open-Source Web Research Platform for AI Agents"
slug: "surfsense-launches-as-open-source-web-research-platform-for-ai-agents"
description: "SurfSense is a new open-source NotebookLM alternative designed for AI agents, providing an open web research platform with live data connectors."
date: 2026-09-17T00:45:10+05:30
tags: [SurfSense, OpenSource, AIAgents, WebResearch, MCP]
categories: ["AI", "AI Agents", "Open Source", "Web Scraping"]
image: "https://avatars.githubusercontent.com/u/122026167?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# SurfSense Launches as Open-Source Web Research Platform for AI Agents

SurfSense is a new open-source NotebookLM alternative designed for AI agents, providing an open web research platform with live data connectors.

## 🔍 Overview
SurfSense allows agents to research the live web using structured data delivered through one REST API or MCP server. The platform includes an agent harness with built-in credit metering, retries, and structured output, enabling agents to generate cited briefs from questions without additional plumbing.

## 🧩 How it works
The platform provides several methods for integration and data retrieval:

* **REST API**: Every connector is a REST endpoint that returns structured JSON, including pages, reviews, transcripts, comments, posts, and SERPs.
* **MCP Server**: Exposes connectors as native tools (such as `surfsense_google_search` and `surfsense_reddit_scrape`) for use with Cursor, Claude, or other agent frameworks.
* **External Connectors**: Supports any MCP server with one-click OAuth for services including Jira, Slack, and Notion.
* **Agent Automation**: Scheduled and event-triggered agents convert findings into alerts and briefs, while a built-in knowledge base keeps findings searchable with citations.

## ⚙️ Key details
SurfSense provides access to structured data from various platforms:

| Source | Available Data |
| :--- | :--- |
| Reddit | Subreddit streams, posts, and comments without official API rate limits |
| YouTube | Comment threads, videos, and transcripts at scale |
| Instagram | Posts, reels, and public profiles without the Graph API |
| TikTok | Profiles, hashtags, comments, and videos without Research API approval |
| Google Maps | Reviews, ratings, and places for local business research |
| Google Search | Live SERPs for monitoring and search research |
| Indeed | Public job postings with full descriptions and salaries |
| Amazon | Public product data including best-seller ranks, offers, sellers, ratings, and prices |
| Walmart | Public product data, variants, sellers, ratings, prices, and full review history |
| Web Crawl | Clean, structured content from any page on the open web |

## 🚀 Availability
SurfSense is open source and self-hostable, allowing research to remain on the user's own infrastructure. Self-hosting remains free and open source, supporting collaborative chats, presentations, podcasts, reports, and chat with citations.

#SurfSense #OpenSource #AIAgents #WebResearch #MCP

---

*Source: [MODSetter/SurfSense](https://github.com/MODSetter/SurfSense)*
