---
title: "Exposed API Leads to Customer Credential Exposure at Radware"
slug: "exposed-api-leads-to-customer-credential-exposure-at-radware"
description: "Cybersecurity company Radware experienced a data breach after an unauthorized party accessed an unauthenticated internal Cloud WAF management API left reachable from the public internet on November..."
date: 2026-11-25T18:07:47+05:30
tags: [Cybersecurity, DataBreach, Radware, CloudSecurity, APISecurity]
categories: ["AI", "Cybersecurity", "Data Breaches", "Cloud Security"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/24/Radware.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Exposed API Leads to Customer Credential Exposure at Radware

Cybersecurity company Radware experienced a data breach after an unauthorized party accessed an unauthenticated internal Cloud WAF management API left reachable from the public internet on November 19, 2026.

## 🔍 Incident Overview

Radware detected the unauthorized access on a Thursday, ten hours after the initial intrusion. Upon detection, the company took several immediate response actions:

- Blocked the originating IP address and disabled public access to the internal management API.
- Revoked and replaced all internal account credentials.
- Initiated a root cause analysis report, which was later shared by an anonymous source with BleepingComputer.

Founded in 1996 and headquartered in Tel Aviv, Radware provides application delivery and DDoS protection services to more than 12,500 enterprise and telecom carrier customers worldwide.

## ⚙️ Impacted Systems and Data

The exposure was limited to specific account management details and log export configurations, while core traffic inspection remained unaffected.

| System / Data Category | Status According to Radware |
| --- | --- |
| Customer contact details | Potentially accessed |
| Log export credentials (AWS S3, Azure Blob Storage, SFTP) | Potentially accessed for a subset of customers |
| WAF traffic inspection and certificates | Not exposed |
| End-users' data and customer application traffic | Not exposed |
| Cloud DDoS services and data | Not exposed |

Radware stated that WAF traffic inspection and protection have continued without interruption, with no evidence found of policy changes or access to customer application traffic.

## 💡 Customer Action Advised

Radware strongly advised affected AppSec (WAF, BOT) customers to take immediate remedial steps:

- Rotate exposed Cloud WAF log export credentials, including Azure Blob Storage keys or SAS tokens, AWS S3 access keys, or SFTP credentials, as soon as possible.
- Review access logs on cloud storage accounts for unexpected access dating back to at least November 19.

The company noted it has already received reports from customers regarding AWS alerts for an unfamiliar IP address attempting to access their log-export buckets.

## 📊 Investigation and Public Response

Radware is continuing to investigate the incident to determine whether any exposed API keys or customer information were used without authorization. As of the report, Radware has not issued a public statement, filed a breach report with the US Securities and Exchange Commission, or provided an immediate response to inquiries from BleepingComputer.

#Cybersecurity #DataBreach #Radware #CloudSecurity #APISecurity

---

*Source: [Radware discloses breach exposing customer cloud access keys](https://www.bleepingcomputer.com/news/security/radware-discloses-breach-exposing-customer-cloud-access-keys/)*
