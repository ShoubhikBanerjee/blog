---
title: "Threat actors compromised 24 Check Point servers across 22 organizations in cyberespionage campaign"
slug: "threat-actors-compromised-24-check-point-servers-across-22-organizations-in-cyberespionage-campaign"
description: "Threat actors exploited multiple vulnerabilities to compromise two dozen Check Point Security management servers in an ongoing campaign targeting 22 organizations, according to threat intelligence..."
date: 2026-11-24T22:08:41+05:30
tags: [cybersecurity, CheckPoint, GreyNoise, GT13, cyberespionage, AI]
categories: ["AI", "Cybersecurity", "Network Security", "Threat Intelligence", "Information Security"]
image: "https://www.bleepstatic.com/content/hl-images/2026/05/05/hacker.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Threat actors compromised 24 Check Point servers across 22 organizations in cyberespionage campaign

Threat actors exploited multiple vulnerabilities to compromise two dozen Check Point Security management servers in an ongoing campaign targeting 22 organizations, according to threat intelligence firm GreyNoise. The activity, tracked as GT13, was confirmed as ongoing between October 17 and November 2, though researchers believe the campaign remains active given the threat actors' persistent access to Check Point devices. The 22 victim organizations are spread across 17 countries and include government entities, financial services providers, and companies in the energy, transportation, mining, and manufacturing sectors.

## 🔍 Overview

The attackers launched their operations from 99 IP addresses that appear to come from compromised Check Point devices and ExpressVPN exit nodes. GreyNoise detected the activity and noted it resembled cyberespionage operations, although the attacker's motivation could not be conclusively determined. The researchers assessed that GT13 operated an AI-powered offensive tool, based on observed behavior, automation, and custom tooling, but this use of AI in the campaign remains unconfirmed.

## 🧩 How it works

The attack chain began with unknown means of initial compromise, though GreyNoise could not determine when or how the Check Point servers were breached. During post-compromise stages, the researchers observed the exploitation of CVE-2026-16232, an authentication bypass in Check Point SmartConsole that allows attackers to obtain an application login token and authenticate with administrator privileges. A Rejetto HTTP File Server, compromised by exploiting CVE-2026-61500, was used as an operational relay for managing intrusions and collecting stolen data from the compromised environments.

## ⚙️ Key details

The attackers leveraged automation and custom tooling, observed across more than 1,400 network sessions, 800 command-line artifacts, and 1,200 file-related activities. Their activities included:

- Stealing firewall databases, credentials, configuration data, and internal certificate authority files
- Generating a new certificate in one victim's environment
- Unloading security policies, effectively disabling firewall protections
- Conducting internal network reconnaissance and attempting lateral movement

On October 26, the attacker performed a bulk certificate management operation across all 24 compromised Check Point servers, which failed, but still helped GreyNoise identify victims. The researchers also observed attempts to exploit multiple additional vulnerabilities: CVE-2025-5777 (Citrix NetScaler), CVE-2024-21893 (Ivanti), CVE-2026-41089 (Windows NetLogon), CVE-2026-98432 (Linux IPv4 UAF), and CVE-2026-16232 (Check Point SmartConsole auth bypass to Run Script).

The campaign targeted additional enterprise systems including:

| System | Vulnerability | Notes |
|--------|---------------|-------|
| Citrix NetScaler | CVE-2023-4966 | Targeted in lateral movement | 
| Ivanti Connect Secure | CVE-2024-21893 | Targeted during campaign | 
| VMware vCenter | CVE-2021-21972, CVE-2023-34048 | Multiple vulnerabilities exploited | 
| Microsoft Exchange | CVE-2021-26855/34473 | Targeted during intrusions | 
| Microsoft Netlogon | CVE-2020-1472 | Part of lateral movement attempts | 

BleepingComputer has contacted Check Point to ask if they have better visibility into those attacks and which flaw was exploited for initial access, and we are waiting for their response.

## 💡 Why it matters

Although GreyNoise lost visibility into the campaign operations on November 2, the researchers believe it could still be ongoing. The company has notified international government partners and CERTs to alert impacted organizations and shared indicators of compromise (IoCs) that could help identify additional intrusions or block future attempts. Check Point warned about CVE-2026-16232 in July, marking it as an actively exploited zero-day vulnerability.

The campaign demonstrates sophisticated attack capabilities using compromised infrastructure and automation tools to conduct large-scale credential theft and lateral movement across critical infrastructure sectors including government, finance, and energy.

#cybersecurity #CheckPoint #GreyNoise #GT13 #cyberespionage #AI

---

*Source: [Hackers compromise Check Point Servers in 22 organizations](https://www.bleepingcomputer.com/news/security/hackers-compromise-check-point-servers-in-22-organizations/)*
