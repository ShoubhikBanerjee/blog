---
title: "Eido 0.0.2 Adds Browser Automation and Localization to Native AI Workspace"
slug: "eido-0-0-2-adds-browser-automation-and-localization-to-native-ai-workspace"
description: "Eido 0.0.2 is now available for Apple Silicon Macs running macOS 13 or later. This update introduces browser and desktop automation capabilities, expanded localization options, and interface..."
date: 2026-11-17T22:09:21+05:30
tags: [Eido, Zed, AIWorkspace, BrowserAutomation, macOS, PiAgent]
categories: ["AI", "AI Agents", "Developer Tools", "Automation", "Software Updates"]
image: "https://avatars.githubusercontent.com/u/118103359?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Eido 0.0.2 Adds Browser Automation and Localization to Native AI Workspace

Eido 0.0.2 is now available for Apple Silicon Macs running macOS 13 or later. This update introduces browser and desktop automation capabilities, expanded localization options, and interface refinements for the native AI workspace built on Zed and the official pi agent.

## 🌐 Localization Updates

The interface now supports English and Simplified Chinese. Users can select Follow System, English, or 简体中文 at the top of the Settings menu. While common Eido controls and menus are localized, user content, code, model output, and tool identifiers remain unchanged.

## 🖥️ Interface Refinements

Several visual and usability improvements have been applied to the workspace:
* Interface and conversation text default to 16px.
* Ordinary completed tasks no longer leave a detached “Run finished” label; important status messages stay aligned with the input area.
* Existing custom font preferences are preserved.
* Users can drag the empty area in the top toolbar to move a non-fullscreen window on macOS.

## 🌐 Browser and Computer Use

The update introduces experimental features for extending tasks to websites and desktop applications. These capabilities are disabled by default and require separate DeepSeek service configuration. The release includes Chromium and its desktop driver. Users can also connect an existing Poki MCP installation to supported iPhone workflows, though Poki and device preparation are separate setup steps. Automation compatibility varies by website, application, and device.

To enable Computer Use, users must update global settings and grant specific macOS permissions:
1. Open **System Settings → Privacy & Security**.
2. Allow **Eido** under **Accessibility** and **Screen & System Audio Recording** (called **Screen Recording** on some macOS versions).
3. Restart Eido.

These permissions allow input and window capture. Note that replacing a locally signed build can require re-enabling these permissions, and permission previously granted to a standalone Cua Driver does not apply to Eido.

## 🧩 Workflow and Configuration

The update retains pi's public configuration and authentication interfaces while updating runtime adaptation. Key workflow features include:
* Reference relevant files with `@` and attach supporting material.
* Continue earlier tasks with their saved context.
* Review proposed file changes in the native editor before accepting them.
* Search and fetch sources, inspect saved evidence, extract PDF/image text, and connect requirements with proposed changes and checks.

Model and thinking controls are located beside the composer in **AI → pi Models & Credentials**. Configuration and task history are stored outside the application bundle and are preserved during local updates.

## ⚙️ Key Details

* **Bundled Agent**: pi 1.5.2
* **Signing Status**: Locally signed; has not been notarized by Apple.
* **Release Assets**: Include SHA-256 checksums, Eido source, and corresponding source for the native components.

#Eido #Zed #AIWorkspace #BrowserAutomation #macOS #PiAgent

---

*Source: [tony3liu/eido](https://github.com/tony3liu/eido)*
