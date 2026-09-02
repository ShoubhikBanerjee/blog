---
title: "AI plugin updates execute_sql output format"
description: "A new version of the plugin has been released, changing the output format of `execute_sql` from an array of arrays to an array of objects. This is the first non-alpha release."
date: 2026-09-02T12:02:38+05:30
tags: [AI, plugin, SQL, outputformat, mcp]
categories: [AI]
author: "Shoubhik Banerjee"
draft: false
---

# AI plugin updates execute_sql output format

A new version of the plugin has been released, changing the output format of `execute_sql` from an array of arrays to an array of objects. This is the first non-alpha release.

## 🔍 Overview
The plugin now returns rows from `execute_sql` as an array of objects, improving clarity for weaker models by eliminating ambiguity in positional array elements.

## ⚙️ Key details
- Output format: array of objects (previously array of arrays)
- Dependency: requires `mcp>=2.1.1`
- Release status: first non-alpha version

## 🚀 Availability
The update is ready for use, as confirmed by the developer's own extensive testing.

#AI #plugin #SQL #outputformat #mcp

---

*Source: [Release: datasette-mcp 0.2](https://simonwillison.net/2026/Sep/1/datasette-mcp/)*
