---
title: "Q-Dir and DesktopOK Installers Compromised with Python-Based Malware"
slug: "q-dir-and-desktopok-installers-compromised-with-python-based-malware"
description: "Official distribution channels for the popular Windows utilities Q-Dir and DesktopOK were compromised to deliver trojanized installers containing Python-based remote access malware, according to a..."
date: 2026-11-28T22:07:57+05:30
tags: [WindowsSecurity, SupplyChainAttack, Trojan, QDir, DesktopOK, Cybersecurity]
categories: ["AI", "Security", "Malware Analysis", "System Administration", "Windows"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/27/malware.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Q-Dir and DesktopOK Installers Compromised with Python-Based Malware

Official distribution channels for the popular Windows utilities Q-Dir and DesktopOK were compromised to deliver trojanized installers containing Python-based remote access malware, according to a report from AhnLab’s Security Intelligence Center (ASEC).

## 🧩 Malware Capabilities

The malicious installers fetch a Python Remote Access Trojan (RAT) that registers a scheduled task to persist on infected devices. The malware supports the following capabilities:

* Shell command and Python code execution
* File transfer
* Screenshot capture
* System information collection, including a list of active security products

## 📊 Impacted Versions

ASEC confirmed that the compromise affected both new downloads and updates for existing installations. Not all listed versions were infected. The following release versions are impacted:

| Product | Affected Versions |
| :--- | :--- |
| Q-Dir | 12.83.0.0, 12.84.0.0, 12.85.0.0 |
| DesktopOK | 12.82.0.0, 12.85.0.0 |

## 🕵️ Security Detection Evasion

The malware collects a list of 1,206 processes matching various antivirus and endpoint detection and response (EDR) tools to relay to the command and control server. This allows operators to plan their next actions without getting detected. The targeted security products include:

* AhnLab V3
* CrowdStrike Falcon
* SentinelOne
* rend Micro
* Avast
* McAfee
* ESET
* Symantec
* Kaspersky
* Bitdefender
* Sophos
* Fortinet
* Elastic Security
* Malwarebytes
* FireEye

## 🛡️ Remediation and Verification

AhnLab researchers provided SHA-256 hashes to help users distinguish legitimate installers from malicious ones. Users are advised to check their downloads against the SHA-256 published on the official download page. 

Removing a trojanized version of Q-Dir or DesktopOK does not ensure the elimination of the Python RAT. Users who recently installed or updated these tools should treat their system as potentially compromised and check for:

* Suspicious Python execution environments
* Scheduled tasks
* Traces of external network communication

The trojanized versions are digitally signed using a certificate issued to the legitimate developer, Nenad Hrg, who distributes the tools through the SoftwareOK website. ASEC could not determine how the installers were replaced or the timeframe during which the malicious versions were distributed.

#WindowsSecurity #SupplyChainAttack #Trojan #QDir #DesktopOK #Cybersecurity

---

*Source: [Q-Dir and DesktopOK Windows utilities compromised to push Python RAT](https://www.bleepingcomputer.com/news/security/q-dir-and-desktopok-windows-utilities-compromised-to-push-python-rat/)*
