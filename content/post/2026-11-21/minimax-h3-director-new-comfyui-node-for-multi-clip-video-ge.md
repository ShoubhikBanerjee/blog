---
title: "MiniMax H3 Director: New ComfyUI Node for Multi-Clip Video Generation"
slug: "minimax-h3-director-new-comfyui-node-for-multi-clip-video-generation"
description: "MiniMax H3 Director is a new ComfyUI node designed for long video and multi-segment generation. It integrates segment planning, conditional encoding, sampling, decoding, and export into a single..."
date: 2026-11-21T22:09:40+05:30
tags: [MiniMaxH3, ComfyUI, VideoGeneration, AIVideo, ComfyNodes]
categories: ["AI", "Generative AI", "Video Generation", "Machine Learning", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/149470765?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# MiniMax H3 Director: New ComfyUI Node for Multi-Clip Video Generation

MiniMax H3 Director is a new ComfyUI node designed for long video and multi-segment generation. It integrates segment planning, conditional encoding, sampling, decoding, and export into a single interface, utilizing the official MiniMax H3 Image-to-Video and Reference-to-Video models alongside KSampler and AV separation decoding pipelines. The node natively outputs stereo audio.

## 🧩 How it works

The node manages a visual timeline for video generation, supporting several task types and advanced control over segmentation and transitions.

*   **Segmentation and Editing**: Users can upload video within the node to split, equally divide, or intelligently segment scenes using PySceneDetect. Split points are selectable and deletable, with a visual timeline previewing each segment's range and thumbnail.
*   **Grouped Keyframes**: An independent first-last frame timeline allows multiple keyframe groups. Users can either write prompts for text-to-video or upload first/last frames (officially supporting last-frame-only uploads).
*   **Inter-Segment Guidance**: When enabled, empty groups use the last N frames of the previous segment for motion and audio continuity. Users can adjust duration via dragging and select specific groups to run.
*   **Prompt Syntax**: Prompts utilize `<Picture N>`, `<Video K>`, or `<Audio J>` tags (or `@` references). The timeline preview and selection states remain synchronized with the prompts.
*   **Reference Binding**: For style-source video timelines, each segment’s source frame is automatically bound to `<Video 1>`. For reference-to-video tasks, additional reference images (up to 9) and audio (up to 3) can be attached per group.
*   **Selective Sampling**: When enabled, only checked segments or material groups are sampled. Unchecked segments can be filled with cache or source frames during export.
*   **Audio Integration**: Audio is generated in the same sampling pass as the visuals. For video-to-video and reference-video tasks, users can choose to generate sound, use original audio, or remain silent.
*   **Reference Audio Slots**: Users can select existing videos or local audio/video files. Selected videos immediately extract the first audio track as FLAC, saved directly to the `input/` directory.

## ⚙️ Key details

The node supports various task types and integrates external modules to refine the generation pipeline. A semantic bridge and self-lift module can be attached to specific ports; if unconnected, the system behaves as a standard single-stage one-sampling process. When connected, the self-lift module transforms the process into a low-resolution prefix, 3D lift, and high-resolution finish, using Euler sampling at the director canvas resolution.

### External Modules and Refinement

| Module/Feature | Functionality |
| :--- | :--- |
| **Semantic Bridge** | Uses a student MLP to rewrite official conditional tokens. Weights are not distributed with the plugin and must be placed in `models/semantic_bridge/`. |
| **Self-Lift** | Connects to the `selflift` port. Enables a multi-stage sampling process (low-res prefix + 3D lift + high-res finish). |
| **Refine** | Connects to the `refine` port. Offers three modes: `refine` (same-resolution refinement), `upscale` (upscale to target canvas then re-sample according to SIGMAS), and `latent_upscale` (upscale H3 latent only, no re-sampling). |
| **Report Output** | Outputs the segment plan and per-segment task summary via the `report` port. |

### Model and Configuration Requirements

*   **CLIP Loader**: The `type` must be set to `minimax` (Qwen3-VL).
*   **UNET Selection**: `t2v`, `i2v`, and `fl2v` tasks use the `fl2va` UNET. `r2v`, `v2v`, and `rv2v` tasks use the `ref2va` UNET.
*   **Distillation**: The model is distilled from FL2VA. Note that `r2v`, `v2v`, and `rv2v` are forced compatibility modes, and caution is advised when using them.
*   **ComfyUI Version**: Users must upgrade ComfyUI to version 0.30.0 or higher.
*   **Source Images**: Outputting the original film to `source_images` fills the independent `source_images` output without altering the main `images` output.

## 🚀 Availability

The complete resource package, including MiniMax H3 model weights and example JSON workflows, is available via Comfyit Stirring Station · Article 506: "MiniMax H3 Models and Workflows." After downloading, users must merge the `models/` directory into `ComfyUI/models/`. The JSON workflow can be dragged directly into ComfyUI to begin use. The toolbar also supports importing and exporting director packages, which save timeline JSON and reference materials in a zip file.

#MiniMaxH3 #ComfyUI #VideoGeneration #AIVideo #ComfyNodes

---

*Source: [AIMixer/ComfyUI_MiniMaxH3_Director](https://github.com/AIMixer/ComfyUI_MiniMaxH3_Director)*
