---
title: "ASUS patches critical Control Center Express vulnerabilities in v1.7.29"
slug: "asus-patches-critical-control-center-express-vulnerabilities-in-v1-7-29"
description: "ASUS released Control Center Express v1.7.29 to address three critical vulnerabilities that could allow remote attackers to gain administrative control of the management console and the devices it..."
date: 2026-11-20T22:08:48+05:30
tags: [ASUS, Security, Vulnerabilities, ITManagement]
categories: ["AI", "Cybersecurity", "IT Management", "Software Updates"]
image: "https://www.bleepstatic.com/content/hl-images/2025/11/26/Asus.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# ASUS patches critical Control Center Express vulnerabilities in v1.7.29

ASUS released Control Center Express v1.7.29 to address three critical vulnerabilities that could allow remote attackers to gain administrative control of the management console and the devices it manages.

## 🔍 Overview
- Control Center Express is a central dashboard used by IT administrators to monitor and remotely manage fleets of PCs.
- The product is marketed to businesses and IT service providers and supports more than 200 ASUS business, workstation, and Corporate Stable Model motherboards.

## ⚙️ Fixed Vulnerabilities
| CVE | Severity | Type | Impact |
|-----|----------|------|--------|
| CVE-2026-114202 | Critical (CVSS 10.0) | Hard‑coded cryptographic key | Unauthenticated remote attacker can forge an authentication token and gain administrator privileges with no prerequisites |
| CVE-2026-114204 | Critical | Hard‑coded key | Remote attacker with low privileges can forge a session token for a recently logged‑in account |
| CVE-2026-114205 | Critical | Authorization flaw | Low‑privileged user can create an administrator account |

## 🚀 Availability
- Versions earlier than **v1.7.29** are affected. The security bulletin lists versions through **v1.7.27**; the status of **v1.7.28** is unclear.
- Affected users should install **v1.7.29**, then update agents on managed devices via **Select Function → Client Agent Updater** and verify the agent versions.

## 📦 Related Updates
- **Control Center Enterprise** and **Control Center Datacenter** received patches for **CVE-2026-126574**, a critical authorization flaw that lets a low‑privileged Viewer role change an administrator’s password.
- **Armoury Crate** was updated to fix **CVE-2026-112115**, a high‑severity privilege escalation flaw affecting all versions up to 6.7.2.

## 💡 Why it matters
- The unauthenticated remote exploit (CVE‑2026‑114202) provides full administrative control without any user interaction, representing a worst‑case scenario for enterprise IT environments.
- Even the lower‑privilege flaws could enable attackers to elevate their access, potentially compromising large fleets of managed PCs.
- Prompt patching is essential to maintain the integrity of the management console and the devices under its control.

#ASUS #Security #Vulnerabilities #ITManagement

---

*Source: [ASUS warns of critical hard-coded key flaw in Control Center Express](https://www.bleepingcomputer.com/news/security/asus-warns-of-critical-hard-coded-key-flaw-in-control-center-express/)*
