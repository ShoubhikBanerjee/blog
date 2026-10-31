---
title: "MonsterHouse interactive Halloween projection powered by NVIDIA Nemotron Voice Agent"
slug: "monsterhouse-interactive-halloween-projection-powered-by-nvidia-nemotron-voice-agent"
description: "MonsterHouse is an interactive Halloween projection designed to listen and respond to trick-or-treaters. The system uses the personality of a grumpy old pirate ship, which softens when visitors..."
date: 2026-10-31T22:01:44+05:30
tags: [NVIDIA, Nemotron, GenerativeAI, UnrealEngine5, Halloween]
categories: ["AI", "Conversational AI", "Computer Vision", "Interactive Media"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6ab2a746c7d0655b3d8dfbb9/fownH6rn05tSp1jDBTz8m.png"
author: "Shoubhik Banerjee"
draft: false
---

# MonsterHouse interactive Halloween projection powered by NVIDIA Nemotron Voice Agent

MonsterHouse is an interactive Halloween projection designed to listen and respond to trick-or-treaters. The system uses the personality of a grumpy old pirate ship, which softens when visitors remember their manners.

## 🔍 Overview
MonsterHouse is built on the NVIDIA Nemotron Voice Agent and runs on a single workstation. The character is a cantankerous building with a backstory that it was constructed from the timbers of a sunken pirate ship. The house uses a variety of interactive responses, ranging from brushing visitors off with nautical complaints to offering warm farewells if thanked.

## 🧩 How it works

| Component | Technology | Function |
| :--- | :--- | :--- |
| Listening | NVIDIA Nemotron 3 ASR | Turns visitor speech into text |
| Thinking | NVIDIA Nemotron 3.5 Bolt E4B 4GB | Writes replies using an open small language model |
| Speaking | NVIDIA Magpie TTS Zeroshot | Voices replies from a short reference sample |
| Animating | NVIDIA Audio2Face-3D | Turns clean speech into mouth animation in Unreal Engine 5 |
| Seeing | NVIDIA Nemotron 3 Nano Omni | Describes visitor costumes |
| Tracking | YOLO and ByteTrack | Counts and tracks visitors |

## ⚙️ Key details
*   **Model Selection:** The dialogue is powered by Nemotron 3.5 Bolt E4B 4GB, a 4-bit quantized small language model purpose-built for local conversational agents.
*   **Personality:** A LoRA adapter supplies the specific grumpy pirate personality to the language model.
*   **Visual Design:** The character SkelMesh was created in Autodesk Maya and exported to Unreal Engine 5. It features a mouth designed from jagged wooden boards and virtual fire effects.
*   **Hardware:** The entire system runs on one workstation equipped with an NVIDIA RTX PRO 6000 Blackwell Max-Q and an NVIDIA RTX PRO 4000 Blackwell.
*   **Animation:** Audio2Face-3D animates the facial expression shapes, which were manually exported after creating a custom animation rig.

## 💡 Why it matters
The use of the NVIDIA Nemotron Voice Agent provided a foundation for listening, conversation, and speech right out of the box. This allowed for an iterative development process where what was traditionally the difficult part of the build—coordinating complex AI models—became easy. The project demonstrates a complete local pipeline for an interactive, vision-aware conversational character.

![figure](https://cdn-uploads.huggingface.co/production/uploads/6ab2a746c7d0655b3d8dfbb9/5bIvVxc791He8vRKSaBH4.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6ab2a746c7d0655b3d8dfbb9/CzzK5VpTMFR9Azps_6Qbv.png)

![figure](https://cdn-uploads.huggingface.co/production/uploads/6ab2a746c7d0655b3d8dfbb9/iVLQ71tHCdvLRIuaJ6oLk.png)

#NVIDIA #Nemotron #GenerativeAI #UnrealEngine5 #Halloween

---

*Source: [nemotron-halloween](https://huggingface.co/blog/nvidia/nemotron-halloween)*
