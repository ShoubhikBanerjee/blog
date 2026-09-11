---
title: "Graham Dumpleton Releases Wrapture Monkey Patching Library for Python"
slug: "graham-dumpleton-releases-wrapture-monkey-patching-library-for-python"
description: "Graham Dumpleton has released wrapture, a monkey patching library designed for both testing and observability, with new tutorials and documentation published since its initial release on August 31st."
date: 2026-09-11T22:04:55+05:30
tags: [Python, wrapture, monkeypatching, observability, softwaretesting]
categories: ["AI", "Software Development", "Python Programming", "Developer Tools"]
author: "Shoubhik Banerjee"
draft: false
---

# Graham Dumpleton Releases Wrapture Monkey Patching Library for Python

Graham Dumpleton has released wrapture, a monkey patching library designed for both testing and observability, with new tutorials and documentation published since its initial release on August 31st.

## 🔍 Overview
Wrapture is alpha software that serves as a tool for Python developers to handle testing and New Relic style tracing simultaneously. It is described as a "Swiss Army Knife" package for solving various problems.

## ⚙️ Key details
Developers can use wrapture for several specific functions:

* **Unit Testing**: Used for similar purposes as `unittest.mock`.
* **Call Recording**: Recording method calls as timelines and displaying them as trees.
* **Phased Behaviour**: Arranging patched methods to change behavior across multiple calls.
* **Attribute Patching**: Monkey patching dictionaries, generators, and attributes beyond just callables.
* **Tracing**: Live tracing of applications and "zero-code tracing" via a separate TOML file that requires no modification of Python code.
* **Performance Analysis**: Tools for recording timing information, both individually and aggregated across multiple calls.
* **Exporting**: Exporting traces to OpenTelemetry.

## 🧩 Instrumentation Support
The separate `wrapture-instrumenation` package provides instrumentation for the following:

| Target | Support |
| :--- | :--- |
| Web Frameworks | flask, fastapi, django, starlette |
| HTTP Clients/Servers | requests, httpx, http.client, urllib.request, urllib3, aiohttp.client, aiohttp.web, uvicorn, werkzeug.serving, wsgiref.simple_server |
| Databases/Data | sqlalchemy, sqlite3 |
| Other | grpc, jinja2, xmlrpc.client, xmlrpc.server |

## 🚀 Availability
In addition to the library, Graham Dumpleton has provided a set of interactive workshops implemented as JupyterLab notebooks.

#Python #wrapture #monkeypatching #observability #softwaretesting

---

*Source: [Don't sleep on wrapture](https://simonwillison.net/2026/Sep/11/wrapture/)*
