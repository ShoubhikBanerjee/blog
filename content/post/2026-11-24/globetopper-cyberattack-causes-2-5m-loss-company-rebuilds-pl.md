---
title: "GlobeTopper cyberattack causes $2.5M loss, company rebuilds platform on AWS"
slug: "globetopper-cyberattack-causes-2-5m-loss-company-rebuilds-platform-on-aws"
description: "A cyberattack disrupted operations at B2B top-up solutions provider GlobeTopper, causing an estimated $2.5 million in lost revenue, while the attacker redeemed digital gift cards worth $70,000."
date: 2026-11-24T12:08:32+05:30
tags: []
categories: ["AI"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/23/giftcard.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# GlobeTopper cyberattack causes $2.5M loss, company rebuilds platform on AWS

A cyberattack disrupted operations at B2B top-up solutions provider GlobeTopper, causing an estimated $2.5 million in lost revenue, while the attacker redeemed digital gift cards worth $70,000.

## 🔍 Overview

GlobeTopper detected the intrusion on October 22, 2023, and the attacker redeemed digital gift cards worth $70,000. In a filing with the U.S. Securities and Exchange Commission (SEC), iQSTEL stated that GlobeTopper detected more unauthorized activity the day after it identified the attack.

## 🧩 What was accessed

During its investigation, the Company determined that the unauthorized party obtained API credentials and integration keys of certain GlobeTopper business customers. GlobeTopper says the attacker obtained certain client API credentials and integration keys, which have been revoked and replaced, and it has observed no unauthorized use of them yet.

## ⚙️ Key details

- Parent company: iQSTEL
- Service type: Business-to-business digital gift card distributor
- Customers affected: Various retailers, fintech apps, and rewards platforms using its API
- Notable clients: IKEA, Adidas, Spotify, Target, and Roblox
- Platform reach: Used by more than 4,000 brands across 65 countries
- Response actions: Suspended platform (October 22), took all affected servers offline (October 23), deployed rebuilt platform on AWS (October 31)
- Credential management: All affected credentials and integration keys have been revoked and rotated; new credentials issued with additional access restrictions
- Financial impact: Estimated $2.5 million in lost revenue; $70,000 in unrecoverable gift card redemptions
- Investigation status: Ongoing to determine whether other customer, personal, payment, or provider data was accessed or acquired
- Ransomware status: No ransomware groups have listed iQSTEL or GlobeTopper as victims on their extortion portals

## 🚀 Availability and Recovery

Commercial operations were restored in stages starting November 1. The company deployed a completely rebuilt platform on AWS on October 31.

## 💡 Why it matters

The incident highlights vulnerabilities in B2B digital distribution platforms. When API credentials are compromised, attackers can gain access to systems used by thousands of brands worldwide. GlobeTopper's experience demonstrates the importance of rapid response and system rebuilding in the face of cyberattacks. The inability to recover or block redeemed digital gift cards also illustrates challenges with digital asset recovery compared to traditional financial losses.

---

*Source: [GlobeTopper loses $2.5 million after hackers steal $70k in gift cards](https://www.bleepingcomputer.com/news/security/globetopper-loses-25-million-after-hackers-steal-70k-in-gift-cards/)*
