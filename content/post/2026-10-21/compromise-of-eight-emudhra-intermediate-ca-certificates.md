---
title: "Compromise of Eight eMudhra Intermediate CA Certificates"
slug: "compromise-of-eight-emudhra-intermediate-ca-certificates"
description: "The private keys of eight eMudhra intermediate CA certificates have been compromised, affecting certificates that chain to roots trusted by several major root programs and downstream trust stores."
date: 2026-10-21T06:09:12+05:30
tags: [eMudhra, Cybersecurity, Certificates, CACompromise]
categories: ["AI", "Cybersecurity", "Software Updates", "Internet Infrastructure"]
author: "Shoubhik Banerjee"
draft: false
---

# Compromise of Eight eMudhra Intermediate CA Certificates

The private keys of eight eMudhra intermediate CA certificates have been compromised, affecting certificates that chain to roots trusted by several major root programs and downstream trust stores.

## ⚙️ Key details
- The compromise involves eight eMudhra intermediate CA certificates.
- These certificates chain to roots trusted by:
    - Mozilla
    - Microsoft
    - Apple
    - Chrome root programs
    - Many downstream trust stores

## 🚀 Availability
Software that bundles trusted certificates requires updates. Current updates include:

| Software/Package | Version |
| :--- | :--- |
| uv | 0.13.4 |
| pip | 26.2.2 |
| certifi | 2026.10.19 |

Additionally, Linux distributions are required to update their ca-certificates packages.

#eMudhra #Cybersecurity #Certificates #CACompromise

---

*Source: [eMudhra Intermediate CA Compromise](https://simonwillison.net/2026/Oct/20/emudhra-certificates/)*
