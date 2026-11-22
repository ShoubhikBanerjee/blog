---
title: "New Open Source ChatGPT Web Fork Integrates Video Image and Audio APIs"
slug: "new-open-source-chatgpt-web-fork-integrates-video-image-and-audio-apis"
description: "An open-source, MIT-licensed secondary development of the chatgpt-web project has been released on GitHub. Based on the work of ChenZhaoYu and integrated with multiple backend APIs including..."
date: 2026-11-22T18:07:49+05:30
tags: [OpenSource, ChatGPT, Midjourney, MultiModal, AIVideo]
categories: ["AI", "Generative AI", "Software Development", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/3765401?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Open Source ChatGPT Web Fork Integrates Video Image and Audio APIs

An open-source, MIT-licensed secondary development of the chatgpt-web project has been released on GitHub. Based on the work of ChenZhaoYu and integrated with multiple backend APIs including midjourney-proxy, Suno-API, and Luma-API, this free project combines multi-modal capabilities across text, image, music, and video generation.

## ⚙️ Key details
This project is built as a secondary development and utilizes several underlying technologies:
* **Base Project**: [ChenZhaoYu's chatgpt-web](https://github.com/Chanzhaoyu/chatgpt-web)
* **Backend APIs**: [midjourney-proxy](https://github.com/novicezk/midjourney-proxy), Suno-API, and [Luma-API](https://github.com/LumaAI-API/Luma-API)
* **Storage**: Local storage is implemented via localforage for images.

## 🧩 Supported Models and Features
The project integrates a wide array of generation and editing features across different medium types:

| Capability Type | Supported Tools / Models | Key Features |
| :--- | :--- | :--- |
| **Video Generation** | pika, runway, luma, kling, viggle | Text-to-video, image-to-video, and dance (viggle) |
| **Music Generation** | udio, suno | Text-to-music, audio-to-audio (suno), lyrics and style adjustment |
| **Image Generation** | flux, dall.e, ideogram, kling | Text-to-image generation |
| **Midjourney Controls** | Midjourney, Niji robots | Partial repainting, zoom (1.5x, 2x), HD (2x, 4x), pan (left, right, up, down), and image-to-text |
| **Chat & Voice** | chatgpt web | Custom API keys and base_url, custom models, context/response counts, GPTs multi-modal, tts, whisper, dall-e-3, and native browser speech recognition (ASR in v2.15.7+) |

## 🚀 Availability
* **Distribution**: Released on GitHub under the MIT license.
* **Cost**: Fully free and intended for open-source learning.
* **Policy**: There are no paid services, account sales, or discussion groups associated with the project.

#OpenSource #ChatGPT #Midjourney #MultiModal #AIVideo

---

*Source: [Dooy/chatgpt-web-midjourney-proxy](https://github.com/Dooy/chatgpt-web-midjourney-proxy)*
