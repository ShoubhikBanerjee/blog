---
title: "Beep Locator: Using Claude Code to Triangulate a Mysterious Room Beep"
slug: "beep-locator-using-claude-code-to-triangulate-a-mysterious-room-beep"
description: "A box‑filled room in a house started emitting an intermittent beep; using Claude Code I built **Beep Locator** to pinpoint the source."
date: 2026-11-10T12:01:43+05:30
tags: [Claude, AcousticLocalization, Python, WebSockets]
categories: ["AI", "Artificial Intelligence", "Software Engineering", "Signal Processing", "Acoustics"]
image: "https://static.simonwillison.net/static/2026/beep-locator-card.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Beep Locator: Using Claude Code to Triangulate a Mysterious Room Beep

A box‑filled room in a house started emitting an intermittent beep; using Claude Code I built **Beep Locator** to pinpoint the source.

## 🔍 Overview
- The system was created to locate a mysterious beep that began sounding a few weeks ago in a room full of unpacked boxes.
- Claude Code generated the software, and the solution ran on a Python web server with a browser‑based UI.

## 🧩 How it works
- A primary UI is served by a Python web application server.
- Devices connect to the server via WebSockets after scanning a QR code or opening a URL.  The UI requests microphone access.
- Each listener records a 60‑second buffer of recent audio and runs a simple beep detection algorithm (see `detector.js`) that applies a Fast Fourier Transform and a high‑pass filter to find potential beeps.
- When a beep is reported, the server selects the device with the lowest round‑trip time and has it play a short chirp.
- The server then asks every listener to upload a clip spanning roughly 0.6 s before the beep to 0.8 s after the chirp.  The chirp aligns the clips, a crucial step for triangulation.
- The triangulated locations are plotted on a map; beeps appear as **X** marks and are logged in a “Sounds located” list.
- Additional UI features:
  - **Rough mode** – manually drag device icons to approximate positions, which are then refined using the sound data.
  - **Clapping mode** – generate test sounds by clapping; these appear as diamonds on the map.

## ⚙️ Key details
| Device | Role |
|--------|------|
| Two iPads | Listener |
| Phone | Listener |
| MacBook Pro | Listener |
| Surface Ultra | Listener |

- The system measures the interval between beeps and uses the triangulated positions to lock down the most likely source.
- Reported accuracy was about **40 cm**.

## 📈 Results
- After the system identified the beep location, digging in the indicated pile of boxes revealed an **ancient carbon monoxide detector** that needed its batteries replaced.

## 📚 References
- While building the project, Claude retrieved the 2007 paper **“BeepBeep: A High‑Accuracy Acoustic‑Based System for Ranging and Localization Using COTS Devices.”**

![figure](https://static.simonwillison.net/static/2026/beep-locator-ui.webp)

#Claude #AcousticLocalization #Python #WebSockets

---

*Source: [Locating the source of a mysterious beep with Claude](https://simonwillison.net/2026/Nov/9/mysterious-beeps/)*
