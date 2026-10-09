---
title: "Integrated Short‑Video Generation Workstation with AI Copy, TTS, and Image Synthesis"
slug: "integrated-shortvideo-generation-workstation-with-ai-copy-tts-and-image-synthesis"
description: "A new open‑source short‑video generation workstation bundles content planning, AI copywriting, batch TTS dubbing, AI image synthesis, ASR subtitle extraction, and free‑form AI creation into a single..."
date: 2026-10-09T22:05:01+05:30
tags: [AI, VideoAutomation, OpenSource]
categories: ["AI", "Artificial Intelligence", "Video Production", "Open Source Software"]
image: "https://avatars.githubusercontent.com/u/138738955?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Integrated Short‑Video Generation Workstation with AI Copy, TTS, and Image Synthesis

A new open‑source short‑video generation workstation bundles content planning, AI copywriting, batch TTS dubbing, AI image synthesis, ASR subtitle extraction, and free‑form AI creation into a single platform.

## 📦 Overview
- All‑in‑one (短视频) generation workbench that combines:
  - Content策划
  - AI文案自动生成
  - TTS 批量自动配音
  - (AI)图片素材合成
  - ASR 自动提取语言字幕脚本
  - AI 自由创作
- Designed for convenient management of each video project.

## ⚙️ Core Features
| Feature | Description |
|---|---|
| Template batch generation | One‑click creation of script, AI‑generated images, subtitles, and audio from a template. |
| Gemini + TTS synthesis | Rewrite scripts and directly output emotional voice‑over. |
| Image‑text track management | Front‑end can replace image, subtitle, or audio and preview results instantly. |
| Card‑style project overview | Shows output directory, creation time, and delete action for quick locating. |
| Copywriting generation | Structured scene script view; copy single line or full text; left‑side checkboxes link to right‑side prompt hints. |
| TTS synthesis | Single and batch modes; input text + emotion prompt to generate voice. |
| Image generation | Central management of character and scene prompts; batch copy to drawing tasks. |
| Character / background generation | Prompt input, reference image upload, aspect‑ratio setting, history for reuse. |
| ASR subtitle extraction | Reverse‑engineered interface; “字幕生成” button in TTS UI opens subtitle tool. |
| Prompt library & free creation | Collect high‑frequency prompts for one‑click copy; free‑creation panel for custom drawing. |

## 🚀 Getting Started
1. **Clone the repository** (assumed). 
2. **Copy configuration**: `cp env.example.yaml env.yaml` and fill in Gemini Key, Base URL, model, TTS Key, and prompt strings.  
3. (Optional) Set `Default-Project-Root` in `env.yaml` to `/data/projects` so that generated scripts, audio, and images are persisted under the host `./data` directory.
4. **Install Node dependencies**: `npm install`.
5. **Start the services**:
   - Preferred: `docker compose up -d --build` (one‑click start; first run will auto‑build).
   - If the Node image fails to pull, run `docker pull node:20-alpine` first, then repeat the compose command.
6. **Access the UI** at `http://localhost:8765`.
7. **View logs** with `docker compose logs -f video-workstation`.
8. **Run locally without Docker** (if desired): `npm start` or double‑click `start.bat`; the UI also listens on `http://localhost:8765`.

## 🖥️ Usage Notes
- The container has no desktop environment; buttons like “打开项目目录/打开TTS文件夹” return the path only. Navigate to the corresponding host directory (`./data` by default) manually.
- Projects are stored under the container path `/data/projects` (mapped to the host `./data`).
- Image generation relies on the NanoBanana model accessed via a locally deployed AIStudio reverse‑proxy interface; it has been tested as stable for feeding images to Sora.
- The ASR subtitle extraction component is open‑source code contributed by another author.

## ⚠️ Disclaimer
- The project is intended for reference, learning, and exchange only. It does **not** guarantee practical utility for creating viral video content; defining video concepts and achieving high engagement still requires human creativity.
- The author disclaims any responsibility for issues arising from use of the software.


#AI #VideoAutomation #OpenSource

---

*Source: [Norsico/Video-Materials-AutoGEN-Workstation](https://github.com/Norsico/Video-Materials-AutoGEN-Workstation)*
