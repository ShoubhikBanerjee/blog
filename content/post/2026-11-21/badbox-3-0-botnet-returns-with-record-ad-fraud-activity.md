---
title: "BADBOX 3.0 Botnet Returns with Record Ad Fraud Activity"
slug: "badbox-3-0-botnet-returns-with-record-ad-fraud-activity"
description: "The BADBOX malware botnet has resurfaced, generating a record 40 billion fraudulent advertising bid requests per day through infected Android-based devices."
date: 2026-11-21T22:09:40+05:30
tags: [BADBOX, Malware, AdFraud, Android, Cybersecurity]
categories: ["AI", "Cybersecurity", "Malware", "Ad Fraud", "Android"]
image: "https://www.bleepstatic.com/content/hl-images/2024/12/19/android-malware-botnet.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# BADBOX 3.0 Botnet Returns with Record Ad Fraud Activity

The BADBOX malware botnet has resurfaced, generating a record 40 billion fraudulent advertising bid requests per day through infected Android-based devices.

## 🔍 Overview
- The BADBOX 3.0 variant has grown into the largest documented ad-fraud operation by daily bid request volume.
- It was first discovered in early 2023 on a T95 Android TV box bought on Amazon.
- Germany's cybersecurity agencies warned in December 2024 that the botnet had infected tens of thousands of devices.
- In March 2025, a large-scale disruption operation took place where HUMAN and Shadowserver cut off more than 500,000 BADBOX 2.0 devices from their control servers, while Google removed 24 apps that spread the malware from Google Play.
- Google later sued the botnet's operators, saying the BADBOX 2.0 had infected over 10 million Android-based devices by April 2025.

## 🧩 How it works
- The malware performs ad fraud by playing video ads in hidden windows while impersonating legitimate streaming apps to make the requests appear legitimate.
- HUMAN also observed fraudulent server-side ad insertion (SSAI) requests that tricked advertisers into believing ads were played on streaming devices, even though no actual device or video ad was involved.
- A proxying module also enrolled infected devices in one of 11 residential proxy networks without the owners' knowledge or consent.
- One of those networks, PXYEDGE, was identified as the rebranded successor to IpMoYu, a residential proxy service previously linked to BADBOX 2.0.
- The researchers say PXYEDGE advertised approximately 200,000 proxy nodes, while their monitoring showed unique connections peaking at around 340,000.
- HUMAN says some of the ad fraud traffic was also routed through these residential proxies to appear legitimate and evade anti-abuse filters.

## ⚙️ Key details
- The infected devices fetch malware modules from public code repositories, while the same payloads are also mirrored across various hosting platforms for redundancy and to resist takedowns.
- HUMAN says it also participated in Google's disruption of the related XCPE malware operation earlier this month, which included taking down multiple C2 domains used by BADBOX 3.0.
- Additionally, one of the malware repositories was taken down, while HUMAN says its systems now filter fraudulent advertising traffic associated with BADBOX 3.0.

## 💡 Why it matters
- Users should only buy certified Android devices from reputable manufacturers and ensure that Play Protect is available and active.

![figure](https://www.bleepstatic.com/images/news/u/1220909/2026/November/volume.jpg)

#BADBOX #Malware #AdFraud #Android #Cybersecurity

---

*Source: [BADBOX botnet returns with record-breaking 40 billion daily ad requests](https://www.bleepingcomputer.com/news/security/badbox-30-botnet-returns-with-record-breaking-40-billion-daily-ad-requests/)*
