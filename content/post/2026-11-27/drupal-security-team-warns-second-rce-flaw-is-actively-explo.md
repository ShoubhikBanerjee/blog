---
title: "Drupal Security Team Warns Second RCE Flaw Is Actively Exploited"
slug: "drupal-security-team-warns-second-rce-flaw-is-actively-exploited"
description: "The Drupal security team announced that attackers are exploiting a second critical vulnerability that allows them to breach and hijack unpatched websites. This follows the recent patching of a remote..."
date: 2026-11-27T22:09:22+05:30
tags: [Drupal, Security, CVE2026136716, WebSecurity, VulnerabilityManagement]
categories: ["AI", "Web Security", "Vulnerability Management", "Cryptography", "Software Development"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/27/Drupal_headpic.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Drupal Security Team Warns Second RCE Flaw Is Actively Exploited

The Drupal security team announced that attackers are exploiting a second critical vulnerability that allows them to breach and hijack unpatched websites. This follows the recent patching of a remote code execution flaw known as CVE-2026-132165, or Fail2Install, which allowed anonymous users to take over vulnerable sites by abusing the Drupal installer. An update to the original security advisory warned that threat actors began exploiting the initial flaw one day after patches were released.

## 🧩 The New Vulnerability

The new security issue, tracked as CVE-2026-136716, was patched one week after the initial release. It addresses attack vectors that were left unpatched in the previous advisory and also enables attackers to hijack vulnerable Drupal sites. While most installations are covered by the patch, certain sites in unusual or incomplete install states remain vulnerable to site takeover, including production environments.

## 🔍 Detection Challenges

According to Drupal, it is not apparent in the user interface if a site is in the affected vulnerable state. Furthermore, sites that are already compromised may no longer be in the vulnerable state. The team emphasized that this issue is being exploited in the wild, and any site that left its installer remotely accessible following SA-CORE-2026-017 may still have been compromised.

## ⚙️ Recommended Actions


Drupal has warned users that any unsecured website may have been compromised and advised administrators to ensure the user 1 email address is one they control, considering a reset if necessary. Site logs should be checked for unauthorized access, with a focus on unexpected changes to or by the user 1 account.

For those who cannot immediately upgrade to Drupal 10.6.23, 11.3.23, or 11.4.14, the following mitigation is recommended:

* Secure the installer on all new and existing sites by blocking access to `/core/install.php` in the web server configuration or the `.htaccess` file in the web root.
* Follow the provided guide if evidence suggests the site may have been compromised.

## 💡 Broader Context

The US Cybersecurity and Infrastructure Security Agency (CISA) has flagged six Drupal security flaws as being abused in the wild since November 2021. Two of these flaws have also been exploited in ransomware attacks.

#Drupal #Security #CVE-2026-136716 #WebSecurity #VulnerabilityManagement

---

*Source: [Drupal warns of new site takeover flaw exploited in attacks](https://www.bleepingcomputer.com/news/security/drupal-warns-of-new-access-bypass-flaw-exploited-in-attacks/)*
