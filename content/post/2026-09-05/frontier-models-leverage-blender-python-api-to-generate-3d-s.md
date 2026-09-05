---
title: "Frontier Models Leverage Blender Python API to Generate 3D Scenes and Movies"
description: "Modern frontier models have become highly capable of using Blender to generate and render 3D scenes. By leveraging Blender's Python API, these models can produce editable files, render static images,..."
date: 2026-09-05T22:02:16+05:30
tags: [Blender, ChatGPTCodex, AIagents, 3Dmodeling]
categories: [AI]
image: "https://static.simonwillison.net/static/2026/astra-blender-pelican.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Frontier Models Leverage Blender Python API to Generate 3D Scenes and Movies

Modern frontier models have become highly capable of using Blender to generate and render 3D scenes. By leveraging Blender's Python API, these models can produce editable files, render static images, and even assemble movies.

## 🧩 How it works

Setting up coding agents to work with Blender is straightforward:
* Install the full Mac application from blender.org.
* Run a prompt instructing the agent to use the installed application path, such as `/Applications/Blender`.
* The model uses Blender's Python API to construct and render the scene.

## ⚙️ Key details

Testing with ChatGPT Codex on Mac has demonstrated several key capabilities:
* **Editable Outputs**: Models can produce `.blend` files that users can open and edit directly within Blender.
* **Multimedia Creation**: Beyond single images, models can generate movies by rendering a sequence of images and combining them using `ffmpeg`.
* **Iterative Refinement**: Scenes can be built and improved through sequential prompting. For example, a 3D scene was created and refined using the following prompts:
  1. "Use the already install /Applications/Blender to render a scene of a pelican riding a bicycle"
  2. "OK add a background and a lot of flair"
  3. "OK make it a whole lot better"

![Pelican riding a bicycle](https://s3.amazonaws.com/til.simonwillison.net/06a8afba27ca49ee8734d84e9fd951a2.jpg)

![figure](https://s3.amazonaws.com/til.simonwillison.net/06a8afba27ca49ee8734d84e9fd951a2.jpg)

#Blender #ChatGPTCodex #AIagents #3Dmodeling

---

*Source: [TIL: Using Blender with coding agents on macOS](https://simonwillison.net/2026/Sep/5/blender-coding-agents-macos/)*
