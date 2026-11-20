---
title: "Puppeteer updates installation workflow and adds WebMCP and MCP support"
slug: "puppeteer-updates-installation-workflow-and-adds-webmcp-and-mcp-support"
description: "Puppeteer, a JavaScript library for controlling Chrome or Firefox, has updated its installation behavior to accommodate modern package manager security defaults, while expanding its capabilities with..."
date: 2026-11-20T18:09:02+05:30
tags: [Puppeteer, JavaScript, BrowserAutomation, DevTools, MCP, WebDevelopment]
categories: ["AI", "Web Development", "Automation", "Developer Tools", "Browser Technology"]
image: "https://avatars.githubusercontent.com/u/6906516?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Puppeteer updates installation workflow and adds WebMCP and MCP support

Puppeteer, a JavaScript library for controlling Chrome or Firefox, has updated its installation behavior to accommodate modern package manager security defaults, while expanding its capabilities with new API support and an MCP server integration.

## 🔍 Overview
Puppeteer provides a high-level API to control Chrome or Firefox over the DevTools Protocol or WebDriver BiDi. By default, the tool runs in headless mode, meaning no visible user interface is displayed. Recent developments include the introduction of a Puppeteer-based Model Context Protocol (MCP) server for browser automation and debugging, as well as support for the experimental WebMCP API.

## ⚙️ Key details
Modern package managers, including npm, pnpm, Yarn, Bun, and Deno, now block dependency install scripts by default. Because Puppeteer traditionally downloaded a compatible Chrome binary during the `npm i puppeteer` installation step, this security feature can prevent the browser from downloading, leading to runtime errors.

To address this, developers have two main options:
* Manually download the required browsers after installation by running the command `npx puppeteer browsers install`.
* Configure the package manager to allow the specific install script to run. For example, with npm, developers can add "puppeteer" to the "allowScripts" array in the `package.json` file.

Alternatively, developers can use `npm i puppeteer-core` to install Puppeteer as a library without automatically downloading Chrome.

## 🧩 How it works
A standard workflow involves launching a browser instance, opening a new page, navigating to a URL, and interacting with elements using locators and keyboard actions. The library supports querying elements by CSS selectors or by accessible names, allowing for robust interaction with web content.

## 💡 Why it matters
The updates ensure Puppeteer remains compatible with the default security settings of contemporary package managers while expanding its utility through the installation of the `chrome-devtools-mcp` server. This allows for enhanced browser automation and debugging workflows.

#Puppeteer #JavaScript #BrowserAutomation #DevTools #MCP #WebDevelopment

---

*Source: [puppeteer/puppeteer](https://github.com/puppeteer/puppeteer)*
