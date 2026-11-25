---
title: "Eclypsium Report: Most Infrastructure Security Fixes Address Bundled Software Flaws"
slug: "eclypsium-report-most-infrastructure-security-fixes-address-bundled-software-flaws"
description: "Eclypsium's November InfraTrust Pulse report indicates that the majority of infrastructure security advisories addressing exploited vulnerabilities over the past month involve flaws in third-party..."
date: 2026-11-25T22:10:10+05:30
tags: [Cybersecurity, Infrastructure, SupplyChain, VulnerabilityManagement, PatchManagement]
categories: ["AI", "Cybersecurity", "Infrastructure", "Security Operations"]
image: "https://www.bleepstatic.com/content/hl-images/2026/07/21/infratrust.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Eclypsium Report: Most Infrastructure Security Fixes Address Bundled Software Flaws

Eclypsium's November InfraTrust Pulse report indicates that the majority of infrastructure security advisories addressing exploited vulnerabilities over the past month involve flaws in third-party software bundled into products rather than code developed by the vendors themselves.

## 🔍 Overview
The report tracks 373 new security advisories published by 23 infrastructure vendors between October 15 and November 19, covering 3,880 vulnerabilities. Of these advisories, 98 were rated critical, and 38 contained vulnerabilities listed in CISA's Known Exploited Vulnerabilities (KEV) catalog. However, 33 of those 38 advisories fixed exploited flaws in bundled software components, primarily PHP, Node.js, and OpenSSH.

## ⚙️ Key Details
These vulnerabilities pose additional risks for enterprises because, even after a software developer releases a security fix, organizations must wait for infrastructure vendors to incorporate it into their products. "Your exposure to exploited flaws depends on how quickly each vendor rebuilds its products after an upstream fix ships," the report reads. As of November 20, PHP2Shell fixes were either partially available or had yet to be released for affected products from Fortinet, Juniper, Lenovo, HPE, Netgear, HP, and Siemens. The November 19 release of another 18 PHP security advisories further complicated patching efforts for infrastructure vendors and their customers.

## 🚨 Active Exploitations
Threat actors are chaining PHP vulnerabilities with other flaws to gain root access to compromised devices. An example is the two PHP vulnerabilities known as PHP2Shell (CVE-2026-109618 and CVE-2026-109619) highlighted in last month's InfraTrust report, which are now being exploited in attacks against Palo Alto Networks and Check Point firewalls. Check Point reported that destructive attacks deployed data-wiping malware on VMware ESXi hosts. Other notable active exploits include:

- **Cisco Expressway**: CVE-2026-76466, a critical vulnerability added to CISA's KEV catalog on November 20. On November 23, CISA flagged this flaw as actively exploited after Russian cybersecurity firm F6 spotted hackers using it to gain root privileges.
- **Palo Alto Networks and Check Point**: The PHP2Shell vulnerabilities and CVE-2026-123039 in Check Point gateways. Check Point warned that this flaw was being actively exploited to gain root privileges and establish persistence on vulnerable devices since late October.
- **Arista VeloCloud Orchestrator**: CVE-2026-114625, a critical vulnerability with a CVSS score of 9.9 that was exploited in zero-day attacks.
- **Cisco Secure Firewall ASA and FTD**: CVE-2026-76418, affecting devices configured for remote-access VPNs. The flaw was exploited in attacks to crash devices.
- **SonicWall SonicOS**: CVE-2026-19868, allowing multifactor authentication bypass on VPNs configured with single sign-on. SonicWall warned that it received reports that the flaw was exploited in zero-day attacks.

## 💡 Recommendations
Administrators should also prioritize installing Fortinet's October hardening updates, which addressed numerous vulnerabilities discovered using AI models. As AI makes it easier to discover and exploit vulnerabilities, InfraTrust warns that organizations must take additional steps to protect their devices while waiting for vendors to release security updates. These include:

- Removing management interfaces from the Internet
- Segmenting them internally to limit lateral movement
- Investigating previously exposed devices for backdoors that may remain even after security updates are installed

"Patching is table stakes, but what you do before the patch is available and after the exploit hits will determine whether you survive," the report concludes.

#Cybersecurity #Infrastructure #SupplyChain #VulnerabilityManagement #PatchManagement

---

*Source: [InfraTrust warns of exploited supply chain flaws in network appliances](https://www.bleepingcomputer.com/news/security/infratrust-warns-of-exploited-supply-chain-flaws-in-network-appliances/)*
