---
title: "Cloudflare Acquires Deno, Announces End of Deno Runtime Support"
slug: "cloudflare-acquires-deno-announces-end-of-deno-runtime-support"
description: "On 9 October 2026 Cloudflare announced it has acquired Deno."
date: 2026-10-10T12:03:23+05:30
tags: [Deno, Cloudflare, Serverless, OpenSource]
categories: ["AI", "Software Development", "Cloud Computing", "Open Source", "Programming Languages"]
author: "Shoubhik Banerjee"
draft: false
---

# Cloudflare Acquires Deno, Announces End of Deno Runtime Support

On 9 October 2026 Cloudflare announced it has acquired Deno.

## 🔍 Overview
- The Deno team released the first version of **celld** in August, an open‑source implementation of the Durable Objects pattern from Cloudflare Workers.
- Cloudflare’s acquisition aims to build on celld to “make workerd self‑hosting a first‑class supported way to build and run apps using the Workers programming model.”

## ⚙️ Key Details
- Cloudflare will support the Deno runtime for another year with monthly releases containing bug fixes and security updates.
- After that year Cloudflare will end its development of the Deno runtime.
- Deno will remain open source, and others are welcomed to continue its development.

## 🗣️ Statements from the Deno Creator
- “It’s a joint decision and I agree with it.”
- “I’m most invested in its success and have put the most work into it – and I no longer think it’s where I can do the most important work.”
- “There are some good ideas in Deno and it’s well engineered – but it ultimately is not solving big problems.”
- “It has been sucked into the gravity well of node compatibility, which forces it to behave exactly as Node does.”
- “Why reimplement Node? It works. Marginal performance or UX or security benefits are not enough. I’m interested in building powerful new abstractions.”

## 🧩 celld and the Workers Model
- celld works remarkably well, depending only on object storage for coordination and persistence.
- It is described as an entirely new model for server development, not just a slightly different API to interact with the file system or network.

## 🔐 Permissions System Comparison
| Platform | Permissions model available | Network host allow‑listing |
|----------|----------------------------|----------------------------|
| Deno | Fine‑grained allow‑list for files, folders, and network hosts | Supported |
| Node.js | Permissions added in v20.0.0 (April 2023) and stable in v22.13.0 (Jan 2025) | Not supported (network is either on or off) |

## 📅 Recent Related Articles (dates)
- “A new feature for my blog, built using my voice” – 9 Oct 2026
- “Claude Haiku 5.5” – 7 Oct 2026
- “We’re going to need default hard budget caps on pretty much everything” – 3 Oct 2026
- “OpenAI DevDay 2026 live blog” – 29 Sep 2026

#Deno #Cloudflare #Serverless #OpenSource

---

*Source: [Deno is joining Cloudflare](https://simonwillison.net/2026/Oct/9/deno-is-joining-cloudflare/)*
