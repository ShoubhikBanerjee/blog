---
title: "Security Update Resolves Unauthorized Access in Database Registration Routing"
slug: "security-update-resolves-unauthorized-access-in-database-registration-routing"
description: "A minor security fix has been backported from version 1.0a43 to address a vulnerability that allowed unauthorized database downloads. This update resolves a security issue occurring when database..."
date: 2026-11-16T12:08:13+05:30
tags: [Cybersecurity, Database, SoftwarePatch]
categories: ["AI", "Information Security", "Software Development", "Data Management"]
author: "Shoubhik Banerjee"
draft: false
---

# Security Update Resolves Unauthorized Access in Database Registration Routing

A minor security fix has been backported from version 1.0a43 to address a vulnerability that allowed unauthorized database downloads. This update resolves a security issue occurring when database routes and names do not match.

## ⚙️ Key details

* **Affected Registration**: The issue involves databases registered using `add_database(db, name=..., route=...)`.
* **Vulnerability Condition**: The security flaw occurred when a database was registered with a `route` that differed from its `name`.
* **Access Restriction Bypass**: In these instances, actors who were denied access to the database could still download it from the `/<route>.db` endpoint.

## 🚀 Availability

* The security fix was backported from version 1.0a43.

#Cybersecurity #Database #SoftwarePatch

---

*Source: [Release: datasette 0.65.6](https://simonwillison.net/2026/Nov/15/datasette-2/)*
