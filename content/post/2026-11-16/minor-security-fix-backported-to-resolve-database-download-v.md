---
title: "Minor Security Fix Backported to Resolve Database Download Vulnerability"
slug: "minor-security-fix-backported-to-resolve-database-download-vulnerability"
description: "On 15th November 2026, a minor security patch was backported from version 1.0a43 to address a database access control issue."
date: 2026-11-16T16:01:27+05:30
tags: [Security, BugFix, Patch, Database]
categories: ["AI", "Cybersecurity", "Software Development", "Database Administration"]
author: "Shoubhik Banerjee"
draft: false
---

# Minor Security Fix Backported to Resolve Database Download Vulnerability

On 15th November 2026, a minor security patch was backported from version 1.0a43 to address a database access control issue.

## ⚙️ Key details

* **Affected function:** Databases registered using `add_database(db, name=..., route=...)` where the specified `route` differed from the `name` parameter.
* **Vulnerability:** Unauthenticated or unauthorized actors who were denied access could still download the database file directly via `/<route>.db`.
* **Resolution:** A fix for this route mismatch vulnerability was backported from version 1.0a43.

#Security #BugFix #Patch #Database

---

*Source: [Release: datasette 0.65.6](https://simonwillison.net/2026/Nov/15/datasette-2/)*
