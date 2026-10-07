---
title: "Nouveau/NVK Driver Runs on NVIDIA Spark Box After Extensive Patching"
slug: "nouveau-nvk-driver-runs-on-nvidia-spark-box-after-extensive-patching"
description: "After much back and forth and hoops jumping, I can finally reveal nouveau/nvk running on a NVIDIA Spark box."
date: 2026-10-07T22:09:50+05:30
tags: [Nouveau, NVK, NVIDIA, Linux, ACPI]
categories: ["AI", "Operating Systems", "Hardware", "Drivers"]
author: "Shoubhik Banerjee"
draft: false
---

# Nouveau/NVK Driver Runs on NVIDIA Spark Box After Extensive Patching

After much back and forth and hoops jumping, I can finally reveal nouveau/nvk running on a NVIDIA Spark box.

## 🔍 Overview
- The open‑source **nouveau/nvk** driver has been demonstrated on a **NVIDIA Spark** platform.
- The effort involved a large patch series and new firmware.

## 🛠️ What was required
- **100 patches** were prepared for the driver.
- A **new firmware** was required for the hardware.
- The author notes it "might mean it's a wait for nova type situation" when considering upstream integration.

## 🚀 Availability
- Upstreaming is still uncertain; the author is "not sure how best to upstream it all."
- No official release or integration status is provided beyond the demonstration.

## 📺 Watching the demo
- To view the live stream of the demonstration, go to the YouTube schedule overview and hover over the paperclip to see the **‘Live Stream’ link**.
- Live streams are only available for **A/V assisted tracks**.
- For a two‑way conversation during the stream, you need a **Matrix account**, join the **Linux Plumbers Space**, and find the room corresponding to the track you’re watching.

## ⚠️ ACPI Operation Region Conflicts (Related Kernel Insight)
- Many people mistakenly think warnings like `ACPI Warning: SystemIO range … conflicts with OpRegion …` indicate a firmware bug; **this is generally untrue**.
- The **Advanced Configuration and Power Interface (ACPI)** specification abstracts hardware details.
- ACPI provides information as **code** via the **ACPI Source Language (ASL)**, which is compiled into bytecode interpreted by the OS at runtime.
- ASL can define **Operation Regions** that map to hardware registers.
- Example: an operation region **OPR1** at I/O port `0x400`, 2 bytes long, with 8‑bit fields `INDX` and `DATA`.
- ACPI methods lock access to these registers; however, a Linux driver that accesses the hardware directly **has no knowledge of ACPI** and can race with ACPI methods.
- The kernel detects such conflicts and emits warnings such as:
  `ACPI Warning: SystemIO range 0x0000000000000400-0x000000000000401 conflicts with OpRegion 0x0000000000000400-0x0000000000000401 (OPR1)`.
- This warning indicates a driver is attempting to allocate I/O ports that an ACPI operation region already claims.

*All statements are drawn directly from the provided evidence.*

#Nouveau #NVK #NVIDIA #Linux #ACPI

---

*Source: [Kernel Planet](https://planet.kernel.org)*
