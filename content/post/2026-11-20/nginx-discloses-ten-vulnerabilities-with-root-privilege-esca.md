---
title: "nginx Discloses Ten Vulnerabilities with Root Privilege Escalation"
slug: "nginx-discloses-ten-vulnerabilities-with-root-privilege-escalation"
description: "On November 18, 2026, F5 and nginx.org disclosed ten vulnerabilities in nginx, marking a critical patch-now event for the world's web servers. The disclosure includes five memory corruption flaws..."
date: 2026-11-20T12:08:10+05:30
tags: [nginx, Security, CVE, Linux, WebServers]
categories: ["AI", "Cybersecurity", "Network Infrastructure", "Software Updates", "Linux Security"]
image: "https://blog.cloudflare.com/_emdash/api/media/file/01M7V71D39CP022CDY7A74N17J.01M7V71DNGTRW0VD6JXCKH83R6.png"
author: "Shoubhik Banerjee"
draft: false
---

# nginx Discloses Ten Vulnerabilities with Root Privilege Escalation

On November 18, 2026, F5 and nginx.org disclosed ten vulnerabilities in nginx, marking a critical patch-now event for the world's web servers. The disclosure includes five memory corruption flaws detailed by the Xint research team under the name nginx2root, which an unauthenticated attacker can exploit to crash a worker or run commands on the server.

## 🔍 Overview

nginx is an HTTP web server that also functions as a reverse proxy, content cache, load balancer, TCP/UDP proxy server, and mail proxy server. Because it runs a large share of the world's web servers, immediate action is required. F5 rates the five nginx2root vulnerabilities as High (CVSS 3.1: 8.1) and Critical (CVSS 4.0: 9.2), noting that code execution requires disabling or bypassing Address Space Layout Randomization (ASLR).

## 🧩 How it Works

The most serious bugs in nginx2root reside in how nginx parses and manages HTTP/2 and HTTP/3 connections. To trigger them, an attacker must send a carefully ordered stream of protocol frames directly to the nginx process, including billions of WINDOW_UPDATE frames, SETTINGS frames that hold response data back, PING frames that fill send buffers, partial HEADERS frames, and RST_STREAM at specific moments. Additionally, Xint identified a Linux kernel bug in the SCTP send path that allows an attacker who has already gained code execution as the nginx worker to escalate to root privileges on the host, including from within a Docker container.

## ⚙️ Key Details

The following table lists the five nginx2root vulnerabilities and their specific trigger conditions:

| CVE ID | Flaw Type | Trigger Condition | First Affected Version |
| :--- | :--- | :--- | :--- |
| CVE-2026-123007 | Integer overflow leading to out-of-bounds heap read/write | HTTP/2 enabled | 1.9.5 (2015) |
| CVE-2026-123633 | Use-after-free | HTTP/2 with proxy_pass to a backend, worker low on worker_connections | 1.19.7 |
| CVE-2026-121810 | Use-after-free | HTTP/3 (QUIC) with proxy_pass to a backend | 1.25.0 |
| CVE-2026-123634 | Use-after-free | resolver + proxy_pass with variables + a subrequest (mirror or SSI) | 0.6.18 |
| CVE-2026-113425 | Use-after-free | Mail proxy with proxy on and auth_http | 0.5.33 |

The same releases fix five other nginx CVEs, including CVE-2026-118899, which is an infinite loop while reading a request body over TLS 1.3 that allows an unauthenticated attacker to stall a worker.

## 🚀 Protection Status

If your nginx server is reachable only through Cloudflare's proxy, attackers cannot reach the vulnerable code paths for the most serious bugs. Cloudflare's edge is not affected because much of the proxy handling customer traffic now runs on FL2, written in Rust. For proxied hostnames, Cloudflare terminates every client HTTP/2 and HTTP/3 connection at the edge and opens a separate connection to your origin, ensuring the attacker's frames never reach your nginx. However, the resolver and mail proxy vulnerabilities depend on specific configurations and are not protected by the proxy in all cases.

## 💡 Why it Matters

Xint ran exploits over the public Internet against servers on AWS, GCP, and Azure. A Shodan search prior to disclosure found 56.7 million hosts matching product:nginx, with 98.9% of those reporting a version falling in the affected range. As of November 19, Censys's tracker counts about 8.8 million services running a potentially affected version with HTTP/2 enabled. While no kernel fix was available as of November 18 and no vulnerabilities are yet in CISA's Known Exploited Vulnerabilities catalog, users should update to nginx 1.30.7 or 1.31.9 (or their vendor's fixed build) and restart to mitigate these risks.

#nginx #Security #CVE #Linux #WebServers

---

*Source: [nginx2root: five new nginx vulnerabilities, and how Cloudflare protects origins from the worst of them](https://blog.cloudflare.com/nginx2root/)*
