---
title: "F5 Patches NGINX nginx2root Vulnerabilities Enabling Remote Code Execution"
slug: "f5-patches-nginx-nginx2root-vulnerabilities-enabling-remote-code-execution"
description: "F5 has released security updates for multiple NGINX vulnerabilities, including two critical flaws dubbed 'nginx2root.' These vulnerabilities allow unauthenticated attackers to execute code remotely..."
date: 2026-11-20T14:26:01+05:30
tags: [Cybersecurity, NGINX, InfoSec, Linux, CloudSecurity]
categories: ["AI", "Cybersecurity", "Web Infrastructure", "Software Updates"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/19/nginx.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# F5 Patches NGINX nginx2root Vulnerabilities Enabling Remote Code Execution

F5 has released security updates for multiple NGINX vulnerabilities, including two critical flaws dubbed "nginx2root." These vulnerabilities allow unauthenticated attackers to execute code remotely on vulnerable web servers and can be chained with a Linux kernel bug to gain root access to the underlying host.

Researchers at Xint, Wiz, Ikotas Labs, Metnir, and Rapid7 discovered the two primary HTTP/2 vulnerabilities independently. Xint researchers demonstrated that by chaining one of these flaws with a separate vulnerability in the Linux kernel's SCTP subsystem, an attacker can escape an NGINX Docker container and gain root privileges.

## 🧩 How it works
The "nginx2root" vulnerabilities involve memory corruption and session management errors within the NGINX worker process:

*   **CVE-2026-123007:** A flow-control bug that causes memory corruption in an NGINX worker. It impacts versions 1.31.8 down to 1.9.5.
*   **CVE-2026-123633:** A use-after-free issue that occurs when NGINX accepts HTTP/2 connections and proxies them to a backend. When the worker runs low on connection slots, it may close an active connection and free memory that a request is still using.

## ⚙️ Key details
| Vulnerability | Description |
| :--- | :--- |
| CVE-2026-123007 | Memory corruption flaw in NGINX worker via HTTP/2 flow-control. |
| CVE-2026-123633 | Use-after-free vulnerability affecting HTTP/2 requests proxied to backends. |
| CVE-2026-118899 | High-severity DoS flaw causing an infinite loop over TLS 1.3. |
| CVE-2026-121810 | Use-after-free vulnerability affecting HTTP/3 reverse proxying. |
| CVE-2026-123634 | Use-after-free vulnerability affecting DNS resolution with subrequests. |
| CVE-2026-113425 | Use-after-free vulnerability affecting mail proxy authentication. |

## 🚀 Availability
F5 has fixed these issues in the latest versions of NGINX Open Source and NGINX Plus. System administrators are recommended to upgrade immediately:

*   **NGINX Open Source:** Update to 1.30.7 (stable) or 1.31.9 (mainline).
*   **NGINX Plus:** Update to 37.0.8.1 or 37.3.0.1.

As a temporary mitigation for the two "nginx2root" flaws, administrators can disable HTTP/2, although this does not address the other vulnerabilities included in the security update.

## 💡 Why it matters
Exploitability depends heavily on specific server configurations. Security researcher Florian Roth notes that these flaws are exploitable in non-default configurations and may not be an imminent threat for most deployments. The vulnerabilities require HTTP/2 to be enabled on a reachable listener, and CVE-2026-123633 specifically requires NGINX to be proxying requests to a backend.

According to Censys, approximately 8.8 million NGINX services were potentially exposed to CVE-2026-123007 as of November 19, based on version numbers and HTTP/2 support. More than 511,000 previously exposed services have already been patched or mitigated.

#Cybersecurity #NGINX #InfoSec #Linux #CloudSecurity

---

*Source: [Critical NGINX ‘NGINX2Root’ bugs let attackers hijack servers](https://www.bleepingcomputer.com/news/security/critical-nginx-nginx2root-bugs-let-attackers-hijack-servers/)*
