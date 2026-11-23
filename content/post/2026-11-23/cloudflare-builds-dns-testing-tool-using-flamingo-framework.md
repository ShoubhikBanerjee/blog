---
title: "Cloudflare Builds DNS Testing Tool Using Flamingo Framework"
slug: "cloudflare-builds-dns-testing-tool-using-flamingo-framework"
description: "After a DNS service rollout, unit tests passed and dashboards showed green, but production suddenly broke. Some record changes sat unpublished for hours due to a scheduling bug, causing slow hostname..."
date: 2026-11-23T22:18:20+05:30
tags: [DNS, Testing, Infrastructure, Cloudflare]
categories: ["AI", "Network Engineering", "Software Development", "System Testing", "Cloud Infrastructure"]
image: "https://blog.cloudflare.com/_emdash/api/media/file/01M7XNS6Z54W4GPXME90VX9S44.png"
author: "Shoubhik Banerjee"
draft: false
---

# Cloudflare Builds DNS Testing Tool Using Flamingo Framework

## 🔍 Overview

After a DNS service rollout, unit tests passed and dashboards showed green, but production suddenly broke. Some record changes sat unpublished for hours due to a scheduling bug, causing slow hostname resolution and certificate issuance delays. DNS failures are hard to catch because they are slow, spread across the network, and only partially impact where they cause problems.

## 🧩 How it works

The Cloudflare DNS team extended Flamingo, their end-to-end testing framework, to test DNS the way customers experience it: constantly, from every data center, and against production. Flamingo's modular design lets teams add support for other networking protocols. Originally built around complex multi-step HTTP testing, its capabilities have increased substantially over the years.

## ⚙️ Key details

Flamingo is built from the ground up with Cloudflare's infrastructure in mind:

- Built a control plane and scheduler that let teams target specific environments, data centers, or percentages of metals
- Integrates with custom reporting, metrics, and analytics tooling
- Needs predictable performance and runs well on bare-metal servers in resource-constrained environments
- Uses a custom domain-specific language (DSL) consisting of a simple setup-request-response format
- Written in Rust due to its consistent performance characteristics and strong type system
- The type system enables modularity through strongly-typed enumerations for input and output in the action runner

With just five lines of code, a script can run anywhere on Cloudflare's edge and scale to thousands of requests per minute. The data from millions of data points is turned into a graph defining how the service is actually performing in the real world.

| Component | Description |
|-----------|-------------|
| Control plane and scheduler | Let teams target specific environments, data centers, or percentages of metals |
| DSL | Uses simple setup-request-response format, only 5 lines of code for scalable testing |
| Rust | Provides consistent performance and strong type system for modularity |

## 💡 Why it matters

Unit testing alone is not enough for complex network pathways with multiple systems. We need to run constant automated testing against real systems and measure outcomes to make informed decisions on service health. Flamingo measures the behavior of production environments to ensure lower-tier code behaves as expected. The DNS measurements now decide whether a release goes ahead or gets rolled back.

#DNS #Testing #Infrastructure #Cloudflare

---

*Source: [Probing DNS at Cloudflare](https://blog.cloudflare.com/probing-dns-at-cloudflare/)*
