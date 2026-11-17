---
title: "Monid Platform Connects AI Agents to 72+ API Providers"
slug: "monid-platform-connects-ai-agents-to-72-api-providers"
description: "Monid has introduced a connector layer that enables AI agents to access over 2,000 tools across 72 different providers using a single base URL and one key."
date: 2026-11-17T12:12:52+05:30
tags: [A, I, A, g, e, n, t, s, A, P, I, I, n, t, e, g, r, a, t, i, o, n, O, p, e, n, S, o, u, r, c, e, D, e, n, o, C, o, n, n, e, c, t, o, r, L, a, y, e, r]
categories: ["AI", "A", "I", "A", "g", "e", "n", "t", "s", ",", "A", "P", "I", "D", "e", "v", "e", "l", "o", "p", "m", "e", "n", "t", ",", "S", "o", "f", "t", "w", "a", "r", "e", "A", "r", "c", "h", "i", "t", "e", "c", "t", "u", "r", "e", ",", "O", "p", "e", "n", "S", "o", "u", "r", "c", "e"]
image: "https://avatars.githubusercontent.com/u/273455304?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Monid Platform Connects AI Agents to 72+ API Providers

Monid has introduced a connector layer that enables AI agents to access over 2,000 tools across 72 different providers using a single base URL and one key.

## 🔍 Overview
An agent can reach tools across categories including:

*   Web search and scraping
*   People and company enrichment
*   Social platforms
*   Reviews and market data
*   Video, image, and voice generation

## 🧩 How it works
This repo serves as the connector layer, a generic framework that describes how an endpoint is called, what it accepts, and what it returns. A coding agent can write a connector by pointing at API docs and the repo; adding an API to Monid becomes a pull request.

For providers whose product is a durable owned thing (e.g., Saperly's phone numbers), a resource definition (`resources/<slug>/resource.ts`) declares the stored-snapshot shape, platform lifecycle (verify/release/refresh), live views, and usage rate card. Endpoints then bind to these resources purpose-keyed.

## ⚙️ Key details

*   **Usage Metering:** Usage is metered per call based on the connector's definition (flat charge, per returned result, or rate per unit like a thousand characters or a second of video). The engine settles the model on the raw response envelope before any output mapping. Vendor errors, unmatched companies, or unresolved people return data but settle at zero cost.
*   **Endpoint Selection:** The `discover` engine ranks the whole catalog by job, price, live health, and observed latency (p50 and p95), returning hints for cheaper or better-fitting endpoints. The API is picked at call time against everything available, not pinned in code.
*   **The Contract:** A provider declares identity, auth, and usage counting. An endpoint declares the request and input schema. There is no client, adaptor, or per-provider execution path.
*   **Meta Description:** The `meta.description` should be written like the product, as it is what `discover` ranks and `inspect` returns. It should explain what the endpoint really does, what it will not do, and which endpoint to reach for instead.
*   **Pricing:** There are three verbs, and the first two are free.

## 🚀 Availability
*   Requires Deno 2.x.
*   Agents can run a real endpoint with their own vendor key.
*   To get started, an agent should fetch `https://monid.ai/SKILL.md` and save it to their skill directory.

#A #I # #A #g #e #n #t #s #, # #A #P #I # #I #n #t #e #g #r #a #t #i #o #n #, # #O #p #e #n # #S #o #u #r #c #e #, # #D #e #n #o #, # #C #o #n #n #e #c #t #o #r # #L #a #y #e #r

---

*Source: [monid-ai/monid](https://github.com/monid-ai/monid)*
