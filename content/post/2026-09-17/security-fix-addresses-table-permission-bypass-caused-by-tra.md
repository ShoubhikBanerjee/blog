---
title: "Security Fix Addresses Table Permission Bypass Caused by Trailing Newlines"
slug: "security-fix-addresses-table-permission-bypass-caused-by-trailing-newlines"
description: "A security fix has been released to address a vulnerability that allowed requested table names to bypass standard permission controls. The issue centered on how specific character formatting could..."
date: 2026-09-17T06:05:39+05:30
tags: [CyberSecurity, DataPrivacy, SoftwareSecurity, SecurityFix]
categories: ["AI", "Cybersecurity", "Data Security", "Software Engineering"]
author: "Shoubhik Banerjee"
draft: false
---

# Security Fix Addresses Table Permission Bypass Caused by Trailing Newlines

A security fix has been released to address a vulnerability that allowed requested table names to bypass standard permission controls. The issue centered on how specific character formatting could lead to the unauthorized exposure of data.

## 🔍 Overview

The update resolves a security flaw where a trailing newline included in a requested table name could bypass table permissions. This bypass allowed for the potential exposure of private rows that should have remained restricted.

## ⚙️ Key details

*   **Vulnerability Type:** Permission bypass via trailing newline in table names.
*   **Impact:** Exposure of private rows.
*   **Reported by:** dpfkdlemtp.
*   **Reference ID:** GHSA-h547-rmjf-5m2m.

#CyberSecurity #DataPrivacy #SoftwareSecurity #SecurityFix

---

*Source: [Release: datasette 0.65.5](https://simonwillison.net/2026/Sep/16/datasette-2/)*
