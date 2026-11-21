---
title: "Official Python SDK Released for the Scrapfly Platform"
slug: "official-python-sdk-released-for-the-scrapfly-platform"
description: "The official Python SDK for the Scrapfly platform has been released, providing tools for web scraping, screenshots, AI extraction, crawling, and a remote anti-bot browser."
date: 2026-11-21T22:09:40+05:30
tags: [Python, WebScraping, Scrapfly, Automation, SDK]
categories: ["AI", "Software Development", "Data Extraction", "Python"]
image: "https://avatars.githubusercontent.com/u/54183743?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Official Python SDK Released for the Scrapfly Platform

The official Python SDK for the Scrapfly platform has been released, providing tools for web scraping, screenshots, AI extraction, crawling, and a remote anti-bot browser.

## 🧩 Overview

- Integrates with Scrapy, LlamaIndex, and LangChain.
- Covers Scrapfly API endpoints including web scraping, screenshots, AI extraction, crawling, and a remote anti-bot browser.
- Features optional installation extras for added capabilities and performance.

## ⚙️ Key details

- `AsyncScrapflyClient` added in 1.0.0 provides every method of `ScrapeClient` as coroutines, with streamed methods (`scrape_batch`, `crawl_prompt`) as async iterators.
- Up to 0.12, `ScrapflyClient` runs a call as a coroutine with `async_scrape`, `async_screenshot`, and `async_extraction`, while `concurrent_scrape` is an async generator.
- The `unblocker` parameter (previously named `asp`) turns on anti-bot bypass for blocking solutions such as Cloudflare, DataDome, PerimeterX, or Akamai.

## 🚀 Availability

| Extra | Purpose |
| --- | --- |
| `speedups` | Brotli compression and msgpack serialization |
| `parser` | Built-in HTML parser (lxml, beautifulsoup4, extruct) |
| `scrapy` | Scrapy integration |
| `browser` | Playwright-based cloud browser helpers |
| `browser-use` | Browser-use agent integration |
| `webhook-server` | Native webhook server using flask |
| `concurrency` | Kept for compatibility; concurrency needs no extra dependency |

- The `speedups` and `webhook-server` extras install `brotli` (CPython) or `brotlicffi`.
- Up to 0.12 they installed the archived `brotlipy`, requiring users to run `pip uninstall brotlipy` before upgrading.

#Python #WebScraping #Scrapfly #Automation #SDK

---

*Source: [scrapfly/python-scrapfly](https://github.com/scrapfly/python-scrapfly)*
