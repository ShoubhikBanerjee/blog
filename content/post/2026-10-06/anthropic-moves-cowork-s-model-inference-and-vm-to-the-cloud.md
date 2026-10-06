---
title: "Anthropic Moves Cowork’s Model Inference and VM to the Cloud"
slug: "anthropic-moves-coworks-model-inference-and-vm-to-the-cloud"
description: "On 5 October 2026 Anthropic announced a new version of its Cowork product that moves both model inference and the supporting virtual machine (VM) from the local device to the cloud."
date: 2026-10-06T22:08:14+05:30
tags: [Anthropic, Cowork, AIInference, CloudVM, LLM]
categories: ["AI", "Artificial Intelligence", "Cloud Computing", "Software Engineering"]
author: "Shoubhik Banerjee"
draft: false
---

# Anthropic Moves Cowork’s Model Inference and VM to the Cloud

On 5 October 2026 Anthropic announced a new version of its Cowork product that moves both model inference and the supporting virtual machine (VM) from the local device to the cloud.

## 🔍 Overview
- The **old** version of Cowork runs model inference in the cloud but executes tool calls in an Anthropic‑provided VM shipped to the user’s computer.
- The VM was added for capability, safety, and security reasons – it only maps the data explicitly added to a session.
- Users liked Claude’s abilities but complained about the disk, battery, and performance cost of running the VM locally.
- Users also disliked that closing a laptop caused work to stop.
- The **new** version runs both model inference **and** the VM in the cloud.

## 🧩 How it Works
- Each session receives its own sandbox in the cloud; state is not shared with other sessions.
- When the cloud‑based VM needs a local resource (e.g., a file), the desktop app performs the required file‑access tool call.
- This architecture lets Cowork run on phones, keep work running when a laptop is closed, and deliver the same compute power without draining the device’s battery.

## ⚙️ Key Details
- **Inference location:** Cloud (both old and new versions).
- **VM location:** Local (old) → Cloud (new).
- **Session isolation:** Per‑session sandbox, no cross‑session state sharing.
- **Local file access:** Handled by the desktop application via tool calls.
- **User‑reported pain points addressed:** Disk usage, battery drain, performance overhead, and interruption when the laptop is closed.
- **Quote:** “We think this solves a lot of problems we’ve heard about (like using Cowork from a phone, keeping work running, or getting all the same power without losing battery to the VM)” — Felix Rieseberg, Anthropic, see also this help page.

## 🚀 Availability
- Announcement date: 5 October 2026.
- No further rollout timeline is provided in the evidence.

#Anthropic #Cowork #AIInference #CloudVM #LLM

---

*Source: [A quote from Felix Rieseberg](https://simonwillison.net/2026/Oct/5/felix-rieseberg/)*
