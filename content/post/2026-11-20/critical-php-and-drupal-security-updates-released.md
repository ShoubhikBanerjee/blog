---
title: "Critical PHP and Drupal Security Updates Released"
slug: "critical-php-and-drupal-security-updates-released"
description: "On November 19, security updates were released for 18 vulnerabilities in the PHP development ecosystem, alongside the patching of a critical remote code execution flaw in the Drupal content..."
date: 2026-11-20T22:08:48+05:30
tags: [PHP, Drupal, SecurityUpdates, Vulnerabilities, CVE]
categories: ["AI", "Software Security", "Web Development", "Cybersecurity", "Open Source"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/19/php-logo-cyber.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Critical PHP and Drupal Security Updates Released

On November 19, security updates were released for 18 vulnerabilities in the PHP development ecosystem, alongside the patching of a critical remote code execution flaw in the Drupal content management system. These updates address severe security issues that could allow unauthenticated attackers to execute code remotely on vulnerable servers.

## 🚀 PHP Security Updates
The PHP dev team released updates for all supported branches, with versions 8.5.13, 8.4.28, 8.3.37, and 8.2.36 now available. Security firm Aikido reports that these updates address 18 CVEs affecting PHP's core engine, session handling, PHP-FPM, CGI, and other components. The most serious flaw, CVE-2026-129289, is a critical PHP-FPM request smuggling vulnerability with a CVSS score of 9.2. This vulnerability affects certain nginx, Apache, HAProxy, and LSAPI configurations that reuse backend connections to PHP-FPM; standard configurations that do not reuse connections are not affected. As a temporary mitigation, administrators can disable persistent backend connections to ensure they are closed after each request. Third-party maintainer Ondrej Surý has released patched packages for unsupported versions back to PHP 5.6, and Aikido has released hardened container images for similar unsupported versions.

## 🧩 PHP Vulnerability Details
The following vulnerabilities were fixed in the November updates:

| CVE Identifier | Description |
| :--- | :--- |
| CVE-2026-129474 | Use-after-free vulnerability involving magic method backtraces |
| CVE-2026-129496 | Timezone cache use-after-free vulnerability |
| CVE-2026-126714 | Vulnerability involving partially overwritten session files |
| CVE-2026-115560 | Session serializer mismatch vulnerability |
| CVE-2026-129291 | PHP-FPM epoll use-after-free vulnerability |
| CVE-2026-128090 | PHAR OpenSSL signature bypass vulnerability |

Additional fixes address memory corruption, information disclosure, cross-site scripting, denial-of-service issues, and unsafe handling of HTTPS and FTPS URLs. As a temporary mitigation for CVE-2026-115560, PHP recommended disabling session upload progress by setting session.upload_progress.enabled=0. This vulnerability was disclosed in an October 23 informational advisory.

## 🛡️ Drupal Critical Flaws
The Drupal Security Team has patched a critical remote code execution vulnerability, tracked as CVE-2026-132165. Discovered by Anthropic's OSS Scanner, this flaw allows anonymous users to exploit the installer to attempt to reinstall Drupal, potentially leading to site takeover or remote code execution. The security team warned that at least one critical vulnerability can be exploited by anonymous users. Drupal administrators are urged to upgrade to versions 10.6.22, 11.3.22, or 11.4.13. For those who cannot immediately upgrade, it is recommended to secure the Drupal installer by blocking access to /core/install.php in the web server configuration or the .htaccess file. This update also addresses a moderately critical gadget chain vulnerability (CVE-2026-132166). The US Cybersecurity and Infrastructure Security Agency (CISA) has flagged five Drupal vulnerabilities as exploited in the wild since November 2021.

#PHP #Drupal #SecurityUpdates #Vulnerabilities #CVE

---

*Source: [PHP security updates fix 18 flaws, including critical RCE bugs](https://www.bleepingcomputer.com/news/security/php-security-updates-fix-18-flaws-including-critical-rce-bugs/)*
*Source: [Drupal patches critical RCE flaw, warns exploits may surface quickly](https://www.bleepingcomputer.com/news/security/drupal-patches-critical-rce-flaw-warns-exploits-may-surface-quickly/)*
