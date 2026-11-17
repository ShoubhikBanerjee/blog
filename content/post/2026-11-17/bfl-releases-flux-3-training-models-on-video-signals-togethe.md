---
title: "BFL Releases FLUX 3, Training Models on Video Signals Together"
slug: "bfl-releases-flux-3-training-models-on-video-signals-together"
description: "BFL released FLUX 3, training a new image generation model on video signals together to improve temporal consistency and understanding of motion."
date: 2026-11-17T18:10:30+05:30
tags: [StableDiffusion, AI, FLUX3, VideoGeneration, ImageGeneration]
categories: ["AI", "Artificial Intelligence", "Machine Learning", "Computer Vision", "Digital Media"]
image: "https://i.ytimg.com/vi/8cGfJOU3AlQ/maxresdefault.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# BFL Releases FLUX 3, Training Models on Video Signals Together

## Intro
BFL released FLUX 3, training a new image generation model on video signals together to improve temporal consistency and understanding of motion.

## 🧩 Origins
Stable Diffusion’s release prompted Dustin Podell and others to go fulltime into AI. Podell stuck to human content creation while immersing in AI content creation with Andreas Blattmann and Stability AI’s image generation team. After Stability AI fell apart, Anj Midha helped the core group spin out to BFL, which built the FLUX series.

## 🔍 FLUX 3’s Approach
BFL’s argument for training FLUX 3 was to combine three signals: a still shows where the ball is, a video shows how it got there, and the sound of impact can tell when it hit something even if the camera missed contact. A key example in the FLUX 3 release is the horse in motion.

## ⚙️ Video Upscaling
FLUX 3 derives its video upscaler from the same FLUX 3 backbone. Sharpening each frame independently might look terrific, but playing it back can show shimmering as the upscaler makes slightly different decisions per frame. Temporal consistency matters even for higher-resolution files. Andreas Blattmann notes that ordinary 2D video contains evidence about what objects look like from other angles.

## 🚀 Technical Execution
An autoregressive model can learn from all tokens in a training example at once. On the diffusion side, the team distilled long sampling processes down to a handful of steps. Dustin Podell’s early Kontext experiment showed that a model able to draw a dog wearing a hat seemed to know where hats go. A few hours of training got the model to place a logo on a shirt, which was rough but sufficient for offsite discussion. The team then spent months refining the data and model.

## 💡 Unexpected Use Case
Users fed FLUX old, degraded family photos to restore them, then shared the pictures with families. Podell hadn’t predicted this use. After discussing identity preservation across edits and frames, he noted it’s a nice example of users noticing when something is done right.

![figure](https://latent.space/brand/wordmark.webp)

![figure](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,format=auto,onerror=redirect,quality=80/uploads/user/profile_picture/0ac84106-c2bb-4348-891f-fa5737b90805/thumb_swyxski.jpg)

![figure](https://media.beehiiv.com/cdn-cgi/image/fit=scale-down,format=auto,onerror=redirect,quality=80/uploads/asset/file/349354cd-819f-4893-a1cf-c7bae8662f05/flux3-strip.jpg?t=1794863695)

#StableDiffusion #AI #FLUX3 #VideoGeneration #ImageGeneration

---

*Source: [Building Visual Intelligence — Andreas Blattmann & Dustin Podell, Black Forest Labs — Latent Space](https://latent.space/p/bfl/)*
