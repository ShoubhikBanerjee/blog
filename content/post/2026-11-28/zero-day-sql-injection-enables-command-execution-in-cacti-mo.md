---
title: "Zero-Day SQL Injection Enables Command Execution in Cacti Monitoring Platform"
slug: "zero-day-sql-injection-enables-command-execution-in-cacti-monitoring-platform"
description: "A zero‑day SQL injection vulnerability in the open‑source network monitoring tool Cacti was publicly disclosed, accompanied by a proof‑of‑concept exploit that lets unauthenticated attackers execute..."
date: 2026-11-28T12:09:39+05:30
tags: [ZeroDay, Cacti, SQLInjection, Cybersecurity, NetworkMonitoring]
categories: ["AI", "Cybersecurity", "Network Monitoring", "Software Vulnerabilities", "Information Technology"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/27/cacti.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Zero-Day SQL Injection Enables Command Execution in Cacti Monitoring Platform

A zero‑day SQL injection vulnerability in the open‑source network monitoring tool Cacti was publicly disclosed, accompanied by a proof‑of‑concept exploit that lets unauthenticated attackers execute commands on vulnerable servers.

## 🔍 Overview
- The vulnerability allows unauthenticated attackers to inject SQL into the Cacti database.
- It can modify the commands executed by Cacti's real‑time poller.
- The exploit requires the Cacti guest account to be enabled.

## 🧩 How it Works
- Attackers store malicious SQL statements in a guest user's graph display preferences.
- These preferences are processed by Cacti, executing the SQL.
- The SQL modifies the poller configuration to run arbitrary OS commands.
- "I found a path from a fresh, unauthenticated HTTP session to command execution as the Cacti server user in four requests. No login. No valid API key. No phishing. Just four HTTP requests against the default guest surface," explains the researcher.

## ⚙️ Key Details
- Exploit name: **4HTTP2SHELL** (previously **4HTTP2ROOT**).
- Published on Thanksgiving Day by researcher ek0ms savi0r from the Church of Malware.
- GitHub repository: *Sad Girls 0day Club*.
- Tested against Cacti Core 1.2.31; earlier versions may also be vulnerable.
- The researcher expressed frustration: "Security researchers are not the bad guys. We're the ones trying to help. We're the ones who read the docs, wrote the repro, and sent the packet capture," and "We get cracked because we get gaslit for years by billion dollar companies that treat disclosure like a PR problem."

## 🚀 Availability
- Public PoC released with a video demonstration.
- The vulnerability was not reported to Cacti before its public release.

## 💡 Why it Matters
- Cacti can store credentials and SNMP passphrases used to access network devices; a compromise could expose other systems.
- Privileges gained depend on the account running the Cacti web server and poller processes; often a low‑privileged web server account rather than root.

## 📌 Mitigation
- Deactivate the Cacti guest account.
- Restrict access to the application's web interface to trusted networks.
- Review poller configurations for unexpected commands.
- Examine application logs for warnings involving non‑numeric values in graph display settings, which could indicate attempted exploitation.

As of November 27, there have been no reports of the vulnerability being exploited in attacks.

#ZeroDay #Cacti #SQLInjection #Cybersecurity #NetworkMonitoring

---

*Source: [Unpatched Cacti zero-day with public PoC gives remote code execution](https://www.bleepingcomputer.com/news/security/unpatched-cacti-zero-day-with-public-poc-gives-remote-code-execution/)*
