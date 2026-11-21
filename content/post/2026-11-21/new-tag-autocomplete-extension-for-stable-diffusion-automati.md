---
title: "New Tag Autocomplete Extension for Stable Diffusion AUTOMATIC1111 Web UI"
slug: "new-tag-autocomplete-extension-for-stable-diffusion-automatic1111-web-ui"
description: "Tag Autocomplete is an extension for the popular AUTOMATIC1111 web UI for Stable Diffusion that provides suggested tags from image booru boards. It displays autocompletion hints for recognized tags..."
date: 2026-11-21T22:09:40+05:30
tags: [StableDiffusion, Danbooru, AUTOMATIC1111, AItools, ImageGeneration]
categories: ["AI", "Generative AI", "Software Tools", "Image Synthesis"]
image: "https://avatars.githubusercontent.com/u/34448969?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# New Tag Autocomplete Extension for Stable Diffusion AUTOMATIC1111 Web UI

Tag Autocomplete is an extension for the popular AUTOMATIC1111 web UI for Stable Diffusion that provides suggested tags from image booru boards. It displays autocompletion hints for recognized tags to improve prompt accuracy.

## 🔍 Overview
The extension displays autocompletion hints for recognized tags from image booru boards such as Danbooru and e621. These tags are primarily used for browsing Anime-style illustrations, but they are relevant to a wide range of Stable Diffusion models.

| Feature | Description |
| :--- | :--- |
| Danbooru & e621 Tags | Top 100k tags by post count as of November 2022 |
| Wildcard Support | Works with wildcard files from extensions or scripts |
| Extra Networks | Support for Extra Network previews |
| UI Modes | Dark and Light mode support with specific tag colors |

## 🧩 How it works
Completion is triggered by typing a double underscore (`__`). The extension searches for wildcard files in every extension folder and the `scripts/wildcards` folder to support legacy versions. It also supports nested folders for grouped wildcards. Because this was one of the first extensions available, it appears high in the inbuilt extensions list when sorting by "oldest first."

## ⚙️ Key details
Users can locate the extension by using CTRL + F to search for text on the extensions page. It is compatible with wildcard files used by the AUTOMATIC1111 wildcards extension and other similar scripts. Completion provides exact tags that match training data for many popular models.

## 🚀 Availability
Installation is available through three primary methods:
* Using the inbuilt available extensions list within the web UI.
* Manual cloning of the extension files from the repository.
* Downloading pre-packaged versions from the project's Releases page.

## 💡 Why it matters
Most custom Stable Diffusion models were trained using booru tag information or merged with models that were. Using exact tags in prompts can improve composition and consistency, even if the model itself is designed for a photorealistic style.

#StableDiffusion #Danbooru #AUTOMATIC1111 #AItools #ImageGeneration

---

*Source: [DominikDoom/a1111-sd-webui-tagcomplete](https://github.com/DominikDoom/a1111-sd-webui-tagcomplete)*
