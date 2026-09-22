---
title: "Cloudflare Python Workers Reach General Availability"
slug: "cloudflare-python-workers-reach-general-availability"
description: "Cloudflare has announced that support for running Python code on its server-side Workers platform is now generally available following a two-year preview period."
date: 2026-09-22T12:02:55+05:30
tags: [Cloudflare, Python, WebAssembly, Pyodide, Serverless]
categories: ["AI", "Cloud Computing", "Programming Languages", "Software Development"]
author: "Shoubhik Banerjee"
draft: false
---

# Cloudflare Python Workers Reach General Availability

Cloudflare has announced that support for running Python code on its server-side Workers platform is now generally available following a two-year preview period.

## 💡 Why it matters
Cloudflare states that "Python is now a first-class, fully supported language on the Cloudflare Developer Platform." This release represents a significant investment in the Python ecosystem.

## ⚙️ Key details
Cloudflare achieves this functionality by running Python compiled to WebAssembly via Pyodide within its V8-based workerd runtime. Notable limitations include:

* Multiprocessing is non-functional in the WebAssembly VM.
* Threading is non-functional in the WebAssembly VM.

## 🛠️ Development Tools
Developers can utilize the pywrangler tool (packaged as workers-py on PyPI) to run a full local simulation of the Cloudflare stack. This tool executes code using Pyodide in WebAssembly within a 123MB workerd binary.

## 👥 Credits
The release announcement is credited to Gyeongjae Choi, Dominik Picheta, and Hood Chatham, with Gyeongjae Choi and Hood Chatham identified as Pyodide core maintainers.

#Cloudflare #Python #WebAssembly #Pyodide #Serverless

---

*Source: [Cloudflare Python Workers are now generally available](https://simonwillison.net/2026/Sep/21/cloudflare-python-worker/)*
