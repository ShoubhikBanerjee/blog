---
title: "pCloud Pass users report unauthorized device connections following cyberattack"
slug: "pcloud-pass-users-report-unauthorized-device-connections-following-cyberattack"
description: "The pCloud Pass password manager was recently targeted by a cyberattack, resulting in users reporting that unknown devices had connected to their accounts, some with two-factor authentication (2FA)..."
date: 2026-11-28T12:09:39+05:30
tags: [pCloud, PasswordManager, Cybersecurity, DataBreach, 2FA]
categories: ["AI", "Cybersecurity", "Data Breach", "Security", "IT News"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/27/pcloud-logo.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# pCloud Pass users report unauthorized device connections following cyberattack

The pCloud Pass password manager was recently targeted by a cyberattack, resulting in users reporting that unknown devices had connected to their accounts, some with two-factor authentication (2FA) enabled. The attack was contained by the pCloud team, though a small number of user email addresses were exposed.

## 🔍 Overview

According to pCloud, a cyberattack targeting pCloud Pass occurred and was promptly contained. The company stated that a small number of pCloud Pass user email addresses were exposed and that login attempts were made. The system automatically sent notifications to each of these affected addresses.

## ⚙️ Key details

- Users reported receiving notifications warning that an unfamiliar device named "pd" connected to their account from IP address 45.131.244.7 in Luxembourg.
- The IP address is reportedly part of pCloud's own infrastructure.
- Notifications were received by customers who had 2FA enabled.
- Some users who never used the password manager, including those with deleted storage accounts, also received the alerts.
- PCloud stated the attack was isolated to the password manager, and cloud storage services were not affected.
- Passwords, notes, and other information stored in pCloud Pass are encrypted on customer devices and were not compromised.
- It is unknown whether encrypted password vaults were accessed or stolen during the attack.
- A reader noted that the "Open settings" link in the email notifications pointed to passqa1.pcloud.com, a QA environment, rather than the production site.

## 💡 Why it matters

Threat actors who obtain encrypted password vaults can attempt to crack them offline, bypassing the service's login rate limits and two-factor authentication protections. This risk was demonstrated in the 2022 LastPass breach, where stolen encrypted password vaults were linked to cryptocurrency thefts after attackers cracked weak or reused master passwords.

## 🛡️ Security advice

- pCloud is warning customers to watch for phishing attacks.
- The company states it will never ask for master passwords or recovery words over email, phone, or chat.
- PCloud noted that advancements in artificial intelligence are accelerating the discovery of software vulnerabilities, though it did not state that this specific attack was AI-powered.

![figure](https://www.bleepstatic.com/images/news/security/attacks/p/pcloud/pcloud-email.jpg)

#pCloud #PasswordManager #Cybersecurity #DataBreach #2FA

---

*Source: [pCloud confirms password manager hack after suspicious login alerts](https://www.bleepingcomputer.com/news/security/pcloud-confirms-password-manager-hack-after-suspicious-login-alerts/)*
