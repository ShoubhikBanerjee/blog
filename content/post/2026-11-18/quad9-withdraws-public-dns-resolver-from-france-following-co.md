---
title: "Quad9 Withdraws Public DNS Resolver from France Following Court Ruling"
slug: "quad9-withdraws-public-dns-resolver-from-france-following-court-ruling"
description: "Last month, the Swiss non-profit foundation Quad9 announced that it will withdraw its free public DNS resolver from France. This decision followed months of litigation and a French court ruling that..."
date: 2026-11-18T18:09:03+05:30
tags: [DNS, InternetInfrastructure, Quad9, Cloudflare, InternetPrivacy]
categories: ["AI", "Networking", "Internet Policy", "Cybersecurity"]
image: "https://blog.cloudflare.com/_emdash/api/media/file/01M7NJA0M7FAQEQZBW0K0W5KKS.png"
author: "Shoubhik Banerjee"
draft: false
---

# Quad9 Withdraws Public DNS Resolver from France Following Court Ruling

Last month, the Swiss non-profit foundation Quad9 announced that it will withdraw its free public DNS resolver from France. This decision followed months of litigation and a French court ruling that imposed daily financial penalties on Quad9 for failing to block domains associated with alleged copyright infringement.

## 🔍 Overview
The French court's ruling forced Quad9 to choose between crippling litigation and financial penalties, or fundamentally altering its service in a way that would undermine the privacy and security of its users. Left with no good option, Quad9 is choosing to withdraw its service. This withdrawal deprives French Internet users of a trustworthy tool and creates a real risk of disruption to their daily lives.

## 🧩 How it works
DNS resolvers are a foundational piece of the Internet's infrastructure.
- **Address Translation:** When a user types a website name, the DNS system translates that domain name into the IP address the device needs to connect.
- **Resolution:** A DNS resolver looks up that address and sends it back to the device, functioning like an operator finding a phone number in a directory.
- **Blocking Limitations:** The only way a DNS resolver can block content is by declining to return the IP address for a particular website. It cannot remove the actual infringing content from the Internet, nor can it take down the servers hosting it.

## ⚙️ Key details
Multiple public DNS resolvers are utilized globally, but they are increasingly facing regional legal pressures:

| Resolver Name | Provider | Details |
| :--- | :--- | :--- |
| 9.9.9.9 | Quad9 | Withdrawing from France; used by government bodies, educational institutions, hospitals, and utilities. |
| 1.1.1.1 | Cloudflare | Launched in April 2018 as a fast, reliable, privacy-first consumer DNS service that does not collect or sell user data. |
| 8.8.8.8 | Google | One of the best-known public resolvers. |
| OpenDNS | Cisco | Previously withdrawn from France, Portugal, and Belgium (temporarily) under similar circumstances. |

## 💡 Why it matters
If affected parties in France do not change their resolver before Quad9 removes its service, their Internet will fail with no explanation. Quad9 has no way to directly notify these users that their resolver will soon stop working.

This challenge is part of a broader trend. A Belgian court recently issued an order that would impose substantial penalties if Cloudflare, Google, and Cisco do not begin blocking websites through their public resolvers by early January 2027. Cloudflare, which has spent years advocating against orders of this kind, has raised concerns that unrelenting demands for blocking by public DNS resolvers will end up causing real harm to the Internet.

#DNS #InternetInfrastructure #Quad9 #Cloudflare #InternetPrivacy

---

*Source: [Quad9’s withdrawal from France: A canary in the coal mine](https://blog.cloudflare.com/quad9-withdrawal-from-france/)*
