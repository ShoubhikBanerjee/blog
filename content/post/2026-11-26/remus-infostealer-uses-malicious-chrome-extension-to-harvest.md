---
title: "Remus Infostealer Uses Malicious Chrome Extension to Harvest Gmail Emails"
slug: "remus-infostealer-uses-malicious-chrome-extension-to-harvest-gmail-emails"
description: "The Remus infostealer was found to exfiltrate Gmail messages using a stealthy malicious Chrome extension, a capability the operators advertised as a zero‑day exploit in Google’s email service."
date: 2026-11-26T22:08:01+05:30
tags: [Remus, ChromeExtension, Infostealer, Gmail]
categories: ["AI", "Cybersecurity", "Malware", "Browser Security"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/25/Gmail.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Remus Infostealer Uses Malicious Chrome Extension to Harvest Gmail Emails

The Remus infostealer was found to exfiltrate Gmail messages using a stealthy malicious Chrome extension, a capability the operators advertised as a zero‑day exploit in Google’s email service.
## 🔍 Overview
- On November 8 the developer began advertising an alleged Gmail zero‑day that could collect emails even after password changes and session revocations.
- Hudson Rock’s investigation was inconclusive; however, customer evidence matched the seller’s claim despite no technical proof of a zero‑day.
## 🧩 How it works
- A native DLL loads the extension into Google Chrome; Chrome is the only targeted browser.
- The DLL contains the extension as an unencrypted ZIP archive in its .rdata section.
- Because Chrome 137+ removed the command‑line option for loading extensions, Remus edits the victim’s Chrome profile, registers the extension, and enables Developer Mode to run it as an unpacked extension.
- The extension masquerades as “Google Sheets”, copies the description of Google Docs Offline, and requests permission to access all websites.
## ⚙️ Technical details
| Attribute | Detail |
|---|---|
| Name | Google Sheets |
| Fake description | Copies description of Google Docs Offline |
| Permissions requested | Access to all websites |
- Once active, it checks for unread emails every minute across up to 10 Gmail account slots and retrieves them in raw format.
- It sends the email subject, body, sender, and victim’s email address plus a campaign identifier to its command‑and‑control server.
- Failed uploads are queued and retried; a local record prevents duplicate exfiltration.
- The extension also parses attachment filenames but does not forward them, indicating incomplete implementation.
## 🛡️ Mitigation
- Install software only from trusted sources.
- Regularly review `chrome://extensions` for unexpected entries or Developer Mode activation.

#Remus #ChromeExtension #Infostealer #Gmail

---

*Source: [Remus malware steals Gmail messages via fake Google Sheets extension](https://www.bleepingcomputer.com/news/security/remus-malware-steals-gmail-messages-via-fake-google-sheets-extension/)*
