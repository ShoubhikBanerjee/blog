---
title: "Unit 42 tracks Com-affiliated vishing and data extortion campaigns"
slug: "unit-42-tracks-com-affiliated-vishing-and-data-extortion-campaigns"
description: "Unit 42 has tracked and responded to numerous waves of vishing attacks conducted by Com-affiliated threat actors in recent months, leading to data theft and extortion attempts. Since early 2026, the..."
date: 2026-11-21T18:08:57+05:30
tags: [Unit42, ThreatIntel, Vishing, Comaffiliated, Cybersecurity]
categories: ["AI", "Threat Intelligence", "Incident Response", "Cybersecurity", "Adversary Activity"]
image: "https://unit42.paloaltonetworks.com/wp-content/uploads/2026/11/12_Cybercrime_Category_1920x900.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Unit 42 tracks Com-affiliated vishing and data extortion campaigns

Unit 42 has tracked and responded to numerous waves of vishing attacks conducted by Com-affiliated threat actors in recent months, leading to data theft and extortion attempts. Since early 2026, the team has attributed multiple data theft and extortion attempts to Bling Libra and other Com-affiliated threat actors.

## 🔍 Overview
- The attacks have targeted data-rich industries, such as financial services, healthcare, and legal services.
- Targeted organizations were primarily located in the U.S., UK, and Australia.
- Attackers use the threat group and activity cluster naming conventions tracked by Unit 42.

## 🧩 How it works
- **Initial Access:** Attackers establish access through vishing, where they pose as internal IT support and direct employees to servers using subdomains tailored to each targeted organization.
- **MFA Bypass:** These servers act as adversary-in-the-middle (AiTM) proxies that pass user credentials and multi-factor authentication (MFA) approvals to the attackers in real time.
- **Persistence:** In multiple instances, attackers have enrolled an unauthorized MFA device within minutes of authenticating to establish persistence.
- **Exfiltration:** Attackers have automated data exfiltration using Python scripts to target Microsoft 365 mailbox, OneDrive, and SharePoint content.
- **Extortion:** Following exfiltration, attackers have sent Microsoft Teams messages directly to employees, claiming data theft and directing recipients to a Tor-hosted negotiation site.

## ⚙️ Key details
- **CL-CRI-1264:** Identified in September 2026, this activity cluster primarily targets healthcare, pharmaceutical, and other medical organizations. Attackers targeted employees on both corporate workstations and personal mobile devices, reusing a single device named "Pixel 10a" across compromised accounts.
- **CL-CRI-1274:** Also identified in September 2026, this cluster avoided re-prompting for Duo MFA by replaying a persistent “keep me signed in” session token. They then used scripted access through `python-requests` and the Microsoft Graph SDK to collect and exfiltrate data from SharePoint and OneDrive environments. Extortion messages were sent internally via email and Microsoft Teams.
- **CL-CRI-1192:** During an investigation attributed to this cluster (which Google tracks under UNC6671), a malicious browser extension named "Google Chrome" (manifest version 1.6.111) was identified. The extension was not on the Chrome Web Store and was downloaded from an attacker-controlled server at `oskeysetup[.]com`, requiring manual sideloading using Developer Mode.

## 💡 Why it matters
- Organizations can access tailored adversary intelligence, direct analyst consultations, and specialized exposure tracking through Unit 42 Threat Intel Services and its Deep and Dark Web Service.
- If an organization thinks it might have been compromised or has an urgent matter, it should contact the Unit 42 Incident Response team.

#Unit42 #ThreatIntel #Vishing #Com-affiliated #Cybersecurity

---

*Source: [Dialing for Data: Inside the Com’s High-Profile Heists](https://unit42.paloaltonetworks.com/com-affiliate-vishing-attacks/)*
