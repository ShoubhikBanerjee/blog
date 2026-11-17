---
title: "Datasette Lite runs full Python web app in browser via WebAssembly"
slug: "datasette-lite-runs-full-python-web-app-in-browser-via-webassembly"
description: "Datasette Lite allows the full server-side Datasette Python web application to run directly inside a user's browser using WebAssembly and Pyodide."
date: 2026-11-17T22:09:21+05:30
tags: [Datasette, WebAssembly, Pyodide, SQLite, Python]
categories: ["AI", "Web Development", "Databases", "Open Source", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/9599?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Lite runs full Python web app in browser via WebAssembly

Datasette Lite allows the full server-side Datasette Python web application to run directly inside a user's browser using WebAssembly and Pyodide.

## 🧩 How it works
When the demo is launched, the browser downloads and executes a full Python interpreter, installs the `datasette` package and its dependencies, and starts the application in a Web Worker.

- Datasette pages are displayed in a full-window `<iframe>` pointing to URLs under `/app/<session>/`.
- A service worker (`sw.js`) intercepts requests (link clicks, form submissions, fetch calls, static assets) and relays them to the Datasette ASGI application running in Pyodide.
- This architecture supports Datasette's own JavaScript, plugin assets, POST forms, CSRF protection, sign-in cookies, and file uploads/downloads.
- Streaming responses, such as server-sent events or CSV exports, are processed as they are produced.
- If a client disconnects or aborts a fetch, the Datasette application is notified that the client has disconnected.
- Cookies are stored in a cookie jar inside the Python ASGI bridge, lasting until the tab is closed or reloaded.

## ⚙️ Key details
- **Browser Requirements**: Requires a browser with service worker support. Private browsing modes that disable service workers are not compatible.
- **Web Worker Support**: Requires module workers (Chrome 80, Safari 15, Firefox 114 or later).
- **Python Version**: Uses Python 3.14 from Pyodide 314.0.8.
- **Error Handling**: 
  - `503` returned if the tab has already been closed or reloaded.
  - `504` returned if the tab stops answering partway through a request (after four minutes).
  - `500` returned if the Pyodide worker itself fails.
  - `409` returned if a tab was opened before an incompatible update.
- **Session Management**: Each tab receives a random session identifier, allowing multiple instances with different data to run simultaneously.
- **Navigation**: The page mirrors the iframe's location into its fragment to ensure the back button works and URLs are bookmarkable.
- **Security**: Links to external sites open in a new window with `noopener`.

## 🚀 Availability and Versioning
Datasette Lite uses the most recent Datasette release from PyPI by default, including alpha and beta previews.

- **Stable Release**: Append `?ref=stable` to the URL.
- **Specific Release**: Pass a version number as `?ref=`.
- **Preview Release**: `?ref=pre` is equivalent to leaving `?ref` out.
- **Source Code**: Other `?ref` values are treated as branches, tags, or commits in the `simonw/datasette` GitHub repository. 
  - Example: `https://lite.datasette.io/?ref=main` runs the latest development code.
  - Short SHAs made up only of digits are read as version numbers; full 40-character SHAs are required for specific commits.
  - `?ref` values that look like version numbers are always installed from PyPI.
- **Plugin Installation**: `?install=` works for plugins, requiring a commit with a `pyproject.toml`.
- **CORS Handling**: GitHub source zip files are downloaded through a Cloudflare Worker to add necessary CORS headers.

#Datasette #WebAssembly #Pyodide #SQLite #Python

---

*Source: [simonw/datasette-lite](https://github.com/simonw/datasette-lite)*
