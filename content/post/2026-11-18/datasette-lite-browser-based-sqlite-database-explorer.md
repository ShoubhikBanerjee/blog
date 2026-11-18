---
title: "Datasette Lite: Browser-Based SQLite Database Explorer"
slug: "datasette-lite-browser-based-sqlite-database-explorer"
description: "Datasette Lite is a port of the Datasette Python application to run directly in the browser using WebAssembly and Pyodide. It allows users to browse SQLite databases, JSON files, CSV files, or SQL..."
date: 2026-11-18T22:09:17+05:30
tags: [Datasette, SQLite, WebAssembly, Pyodide, BrowserBased]
categories: ["AI", "Web Development", "Database Tools", "Software Development"]
image: "https://static.simonwillison.net/static/2026/datasette-lite-diag.webp"
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Lite: Browser-Based SQLite Database Explorer

Datasette Lite is a port of the Datasette Python application to run directly in the browser using WebAssembly and Pyodide. It allows users to browse SQLite databases, JSON files, CSV files, or SQL scripts without needing a full web server.

## 🔍 Overview
- Datasette Lite enables browsing of SQLite databases, JSON files, CSV files, or SQL scripts directly in the browser.
- Users can load specific versions of Datasette from PyPI or specific commits, tags, or branches from the Datasette GitHub repository.
- Over 100 versions of SQLite are available for use with Datasette.
- Additional Datasette plugins can be installed from PyPI or URLs to wheel files.

## 🧩 How it works
- Datasette Lite uses service workers to intercept HTTP requests and serve them from client-side code.
- Each tab has a unique session ID to ensure that requests are routed to the correct Datasette instance.
- A web worker runs a dedicated Datasette instance for each session.

## ⚙️ Key details
- Datasette Lite can load specific Datasette references, plugins, and SQLite versions.
- Users can install additional plugins using the `?install=` parameter.
- SQLite databases, JSON files, CSV files, or SQL scripts can be loaded using the `&url=` parameter.
- Metadata files can be loaded using the `&metadata=` parameter.
- Fragment hashes can be used to navigate to specific locations within Datasette.

## 🚀 Availability
- Datasette Lite is available at [lite.datasette.io](https://lite.datasette.io/).

## 💡 Why it matters
- Datasette Lite is a powerful tool for linking to demos of work-in-progress features or bug reproductions.
- It simplifies the process of demonstrating and fixing bugs by allowing users to share URLs with specific configurations.
- Datasette Lite is already being used as part of the Datasette development process.

## 📊 Example
- Example URL: [https://lite.datasette.io/?install=datasette-maplibre&url=https://simonw.github.io/datasette-maplibre/demo.db&metadata=https://simonw.github.io/datasette-maplibre/metadata.yml#/demo/capitals_and_countries%23map=0/4.2/180&color=continent](https://lite.datasette.io/?install=datasette-maplibre&url=https://simonw.github.io/datasette-maplibre/demo.db&metadata=https://simonw.github.io/datasette-maplibre/metadata.yml#/demo/capitals_and_countries%23map=0/4.2/180&color=continent)


![figure](https://static.simonwillison.net/static/cors-allow/2026/datasette-maplibre.webp)

![figure](https://static.simonwillison.net/static/2026/compare-sqlite.webp)

#Datasette #SQLite #WebAssembly #Pyodide #BrowserBased

---

*Source: [Running the full server-side Datasette Python app in the browser with service workers and Pyodide](https://simonwillison.net/2026/Nov/17/datasette-lite/)*
