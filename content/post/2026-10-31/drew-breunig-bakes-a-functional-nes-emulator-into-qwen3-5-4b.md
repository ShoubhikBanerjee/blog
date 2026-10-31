---
title: "Drew Breunig bakes a functional NES emulator into Qwen3.5-4B model weights"
slug: "drew-breunig-bakes-a-functional-nes-emulator-into-qwen3-5-4b-model-weights"
description: "On October 30, 2026, developer Drew Breunig released 'nesformer,' a project that integrates a working Nintendo Entertainment System (NES) 6502 CPU emulator directly into the weights of the Qwen3.5-4B..."
date: 2026-10-31T06:04:25+05:30
tags: [Qwen, Emulation, RetroGaming, LLM]
categories: ["AI", "Large Language Models", "Software Engineering", "Artificial Intelligence"]
author: "Shoubhik Banerjee"
draft: false
---

# Drew Breunig bakes a functional NES emulator into Qwen3.5-4B model weights

On October 30, 2026, developer Drew Breunig released "nesformer," a project that integrates a working Nintendo Entertainment System (NES) 6502 CPU emulator directly into the weights of the Qwen3.5-4B model.

## 🔍 Overview
Inspired by Divyansh Agrawal’s "qwenputer," this project allows users to run NES ROMs inside the Qwen model. While the system is functional and capable of running games like Super Mario Bros, it currently operates very slowly. Breunig noted the project was built "just for fun."

## 🧩 How it works
To build the system, Breunig used Opus 5.5 with specific prompts to analyze the original "qwenputer" article and explore the feasibility of emulating NES chips and RAM using language model weights. 

*   **Emulation Target:** The system emulates the 6502 CPU and RAM of the Nintendo Entertainment System.
*   **Validation:** During development, Opus 5.5 utilized a collection of NES CPU conformance tests released 15 years ago by Christopher Pow to ensure accuracy.
*   **Methodology:** The system was designed to explore whether smaller, faster models could eventually reach standard clockspeeds for hardware emulation.

## ⚙️ Key details

| Attribute | Specification |
| :--- | :--- |
| Base Model | Qwen3.5-4B |
| Processor Emulated | NES 6502 CPU |
| Tested ROMs | Super Mario Bros |
| Logic Foundation | Weights-based emulation |

## 🚀 Availability
The project is available with the necessary model weights and a command-line interface (CLI). Users can run the system by pointing the CLI at a compatible NES ROM file.

#Qwen #Emulation #RetroGaming #LLM

---

*Source: [dbreunig/nesformer](https://simonwillison.net/2026/Oct/30/nesformer/)*
