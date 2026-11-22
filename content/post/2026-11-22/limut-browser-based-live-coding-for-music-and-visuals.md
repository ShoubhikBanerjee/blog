---
title: "Limut – Browser‑Based Live‑Coding for Music and Visuals"
slug: "limut-browserbased-livecoding-for-music-and-visuals"
description: "Limut is a new browser‑based live‑coding environment for music and visuals, built to be instantly accessible without any installation."
date: 2026-11-22T22:08:30+05:30
tags: [LiveCoding, WebAudio, OpenSource, BrowserMusic]
categories: ["AI", "Audio Programming", "Creative Coding", "Web Development", "Open Source"]
image: "https://avatars.githubusercontent.com/u/5903857?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Limut – Browser‑Based Live‑Coding for Music and Visuals

Limut is a new browser‑based live‑coding environment for music and visuals, built to be instantly accessible without any installation.

## 🔍 Overview
- Live coding of music and visuals runs directly in any modern browser.
- Inspired by FoxDot’s approach to live‑coding music, with the goal of requiring no install.
- Visual rendering draws inspiration from Crash Server’s `video` player and the Shadertoy community.

## 🧩 How it works
- The interface uses the CodeMirror editor, which provides syntax coloring for Limut code.
- Documentation lives on the same page, positioned beneath the console.
- Example code snippets are embedded on the page; additional examples and technical tests are available in the repository at `examples.limut`.
- Unit tests execute automatically when the page is loaded with the `?test` URL parameter; results appear in the browser console.
- The Shadertoy synth loads shader code directly from the Shadertoy.com API, reusing many community shaders.

## ⚙️ Key details
- **Audio sources**: piano samples from the Salamander Grand Piano V3 (CC BY 3.0), guitar samples from FreePats FSBS Electric Guitar Direct (CC0 1.0), guitar release/muted noises from Karoryfer Shinyguitar (CC0 1.0). Additional waveform tables come from GoogleChromeLabs’ Web Audio Samples (Apache) and include Adventure Kid WaveForms and WaveEdit Online tables.
- **Compatibility**: Normal development maintains backward compatibility; occasional breaking changes trigger a new GitHub release that documents the upgrade path.
- **Testing**: Adding `?test` to the URL runs the built‑in unit tests; output is shown in the console.
- **Packaging**: Limut can be served as a static website or wrapped as a desktop app using Electron (`npm install` then `npm start`). No pre‑packaged binaries are provided yet; contributions are welcome via pull requests.

## 🚀 Availability
- Live demo: https://sdclibbery.github.io/limut/
- Source code and examples: https://github.com/sdclibbery/limut/blob/master/examples.limut
- Issue tracker: https://github.com/sdclibbery/limut/issues
- Release notes: https://github.com/sdclibbery/limut/releases
- Local development: run `./server.sh` and open http://localhost:8000/?test in a browser.

## 💡 Why it matters
- Removes the installation barrier for live‑coding music and visual performances.
- Leverages existing open‑source audio and shader assets, keeping the project lightweight and extensible.
- Provides a single, browser‑native environment that combines code editing, documentation, and testing in one page.

#LiveCoding #WebAudio #OpenSource #BrowserMusic

---

*Source: [sdclibbery/limut](https://github.com/sdclibbery/limut)*
