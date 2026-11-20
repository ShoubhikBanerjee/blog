---
title: "esptool-js brings browser-based serial flashing to Espressif chips"
slug: "esptool-js-brings-browser-based-serial-flashing-to-espressif-chips"
description: "esptool-js is a new Javascript implementation of esptool, a serial flasher utility for Espressif chips, that runs directly in supported web browsers using the Web Serial API."
date: 2026-11-20T18:09:02+05:30
tags: [Espressif, WebAssembly, JavaScript, IoT, EmbeddedSystems]
categories: ["AI", "Embedded Systems", "Web Development", "Hardware", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/9460735?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# esptool-js brings browser-based serial flashing to Espressif chips

esptool-js is a new Javascript implementation of esptool, a serial flasher utility for Espressif chips, that runs directly in supported web browsers using the Web Serial API.

## 🔍 Overview
The repository provides a tool for flashing firmware to ESP devices without requiring a local Python environment. It is designed to work with Google Chrome and Microsoft Edge version 89 or later, as well as Google Chrome on Android version 61 or later via the web-serial-polyfill compatibility layer.

## 🧩 How it works
The library operates through the following workflow:
*   Request access to a serial port using the Web Serial API, optionally filtering by USB vendor or product IDs.
*   Configure loader options and create an `ESPLoader` instance.
*   Connect to the ESP device and detect the chip, a process that resets the device.
*   Flash firmware images to the device.

Users can read firmware files from a `File` input or `fetch` request. Key configuration parameters include the starting address in flash, flash mode (e.g., "dio"), flash frequency (e.g., "40m"), and flash size (e.g., "4MB"). Users can also set options to erase the entire flash before writing, compress data during transfer, or reset the device after flashing.

## ⚙️ Key details
Unlike the Python-based esptool, esptool-js does not implement generation of binary images out of ELF files and does not include companion tools similar to `espefuse.py` and `espsecure.py`.

**Handling Flash Images**
*   **Merged .bin files:** These are contiguous images where bytes between partitions are 0xFF. Using `writeFlash` erases every sector from the start of the image through its end, which also erases NVS and factory partitions within that span.
*   **Sparse Intel HEX files:** These leave gaps out. The `parseIntelHex` function splits the file into one `{ data, address }` entry per contiguous region. If two regions share a 4 KiB flash sector, `parseIntelHex` throws an error. To ensure only covered sectors are erased, users should keep `eraseAll: false` and `compress: true`.

## 🚀 Availability
Developers can integrate esptool-js into web applications using the following endpoints:
*   Use `https://unpkg.com/esptool-js/bundle.js` for a single-file browser load. Dependencies such as `pako` are inlined, so no import map is required.
*   Use `https://unpkg.com/esptool-js/lib/index.js` for Node and bundlers. An API documentation reference is available for detailed class and method information.

#Espressif #WebAssembly #JavaScript #IoT #EmbeddedSystems

---

*Source: [espressif/esptool-js](https://github.com/espressif/esptool-js)*
