---
title: "GitHub Login Plugin for agent.datasette.io Receives 1.0 Release"
slug: "github-login-plugin-for-agent-datasette-io-receives-1-0-release"
description: "The GitHub login plugin used on the agent.datasette.io demo site has received a 1.0 release. The update resolves an issue where authenticated user sessions were expiring prematurely due to missing..."
date: 2026-09-20T18:01:49+05:30
tags: [Datasette, GitHubLogin, WebDevelopment, SoftwareRelease]
categories: ["AI", "Software Development", "Web Security", "Open Source"]
author: "Shoubhik Banerjee"
draft: false
---

# GitHub Login Plugin for agent.datasette.io Receives 1.0 Release

The GitHub login plugin used on the agent.datasette.io demo site has received a 1.0 release. The update resolves an issue where authenticated user sessions were expiring prematurely due to missing cookie parameters.

## 🔍 Overview

While running the GitHub login plugin on the agent.datasette.io demo site, it was observed that authenticated sessions were not lasting very long. Investigation revealed that the plugin was setting cookies without a `Max-Age` parameter. Consequently, these cookies were expiring at the end of a browser session. This behavior occurs frequently in Mobile Safari, regardless of how the application is being used.

## ⚙️ Key details

The update includes the following changes and technical details:
* **Session Fix:** The cookie expiration issue was resolved in pull request #80 by addressing the missing `Max-Age` parameter.
* **Compatibility:** The plugin has been thoroughly tested against both Datasette 0.65.x and Datasette 1.0ax.
* **Version Bump:** Because the plugin has been around for a significant period and is fully tested, it has been officially promoted to a 1.0 release.

#Datasette #GitHubLogin #WebDevelopment #SoftwareRelease

---

*Source: [Release: datasette-auth-github 1.0](https://simonwillison.net/2026/Sep/19/datasette-auth-github/)*
