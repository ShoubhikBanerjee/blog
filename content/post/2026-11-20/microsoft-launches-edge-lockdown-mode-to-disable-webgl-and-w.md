---
title: "Microsoft Launches Edge Lockdown Mode to Disable WebGL and WebGPU"
slug: "microsoft-launches-edge-lockdown-mode-to-disable-webgl-and-webgpu"
description: "Microsoft has introduced a new Edge Lockdown Mode that disables WebGL, WebGL2, and WebGPU APIs to reduce the browser’s attack surface."
date: 2026-11-20T18:09:02+05:30
tags: [Edge, LockdownMode, Cybersecurity, BrowserSecurity, WebGL]
categories: ["AI", "Computer Security", "Web Browsers", "Cyber Defense", "Microsoft"]
image: "https://www.bleepstatic.com/content/hl-images/2026/11/19/Microsoft_Edge.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Microsoft Launches Edge Lockdown Mode to Disable WebGL and WebGPU

Microsoft has introduced a new Edge Lockdown Mode that disables WebGL, WebGL2, and WebGPU APIs to reduce the browser’s attack surface.

## 🔍 Overview
- Edge Lockdown Mode is inspired by Apple’s Lockdown Mode and builds on Edge Enhanced Security Mode (Super Duper Secure Mode), which disables Just‑In‑Time Compilation (JIT) in the V8 engine.
- It blocks WebGL, WebGL2, and WebGPU APIs to stop privilege‑escapable attacks.

## 🧩 How it Works
- The feature focuses on the GPU process, a privileged component that handles complex graphics workloads across browser code, third‑party libraries, and device drivers.
- When a page attempts to use WebGL or WebGPU, the address bar shows a “Lockdown Enabled” indicator.

## ⚙️ Key Details
- Optional, extreme protection for users facing highly targeted attacks.
- Designed for journalists, executives, security researchers, and administrators (Gareth Evans, Partner Security Group Manager).
- Accepts reduced website compatibility for stronger defense.
- Applies to devices in highly restricted environments.
- Websites that rely on WebGL or WebGPU—especially games or maps—may not work as expected.
- Users can test the mode in Edge Canary by:
  1. Switching to the Canary release channel.
  2. Enabling the `#edge-sdsm-plus` flag.
  3. Restarting the browser.
  4. Toggling on Strict mode for “Enhance your security on the web” and blocking WebGL and WebGPU graphics.
- Microsoft estimates the feature could block around 60 % of privilege‑escalation attacks targeting Edge users.
- Planned extensions will add more mitigations beyond the GPU process.
- Experiment results will guide the final experience, adding clearer capability descriptions and site‑level exceptions.

## 🚀 Availability
- Currently available only in the Edge Canary channel.
- Requires a browser restart after enabling the flag.

## 💡 Why it Matters
- Provides high‑risk users with an extra layer of defense against targeted cyberattacks.
- Reduces the attack surface by preventing GPU‑based sandbox escapes.
- Complements Microsoft’s other security enhancements such as the Edge scareware sensor and the recent restrictions on Internet Explorer mode.


![figure](https://www.bleepstatic.com/images/news/u/1109292/2026/Lockdown%20Mode%20indicator.png)

#Edge #LockdownMode #Cybersecurity #BrowserSecurity #WebGL

---

*Source: [Microsoft tests new Edge Lockdown Mode that disables GPU APIs](https://www.bleepingcomputer.com/news/microsoft/microsoft-tests-new-edge-lockdown-mode-that-disables-gpu-apis/)*
