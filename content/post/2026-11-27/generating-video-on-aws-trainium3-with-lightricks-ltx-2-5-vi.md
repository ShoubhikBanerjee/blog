---
title: "Generating Video on AWS Trainium3 with Lightricks LTX-2.5 via Diffusers"
slug: "generating-video-on-aws-trainium3-with-lightricks-ltx-2-5-via-diffusers"
description: "A developer partnered with AWS to access a Trainium3 machine (trn3.48xlarge, 64 NeuronCores) for a month, using it to generate video and sound with Lightricks' LTX-2.5 model through the diffusers..."
date: 2026-11-27T18:08:33+05:30
tags: [AWS, Trainium, Lightricks, Diffusers, VideoGeneration]
categories: ["AI", "Cloud Computing", "Video Generation", "Deep Learning", "Hardware Optimization"]
image: "https://huggingface.co/blog/assets/video-trainium3/thumbnail.jpg"
author: "Shoubhik Banerjee"
draft: false
---

# Generating Video on AWS Trainium3 with Lightricks LTX-2.5 via Diffusers

A developer partnered with AWS to access a Trainium3 machine (trn3.48xlarge, 64 NeuronCores) for a month, using it to generate video and sound with Lightricks' LTX-2.5 model through the diffusers library.

## 🔍 Overview
The project aimed to determine how easy it is to generate videos with diffusers on Trainium3 and to match performance levels found in CUDA or Lightricks' own API. The setup achieved generation times for a 10-second clip with sound in 22 to 23 seconds on half of the machine, matching Lightricks' online API claim of 23.7 seconds for a 10-second 1080p clip and beating it by about a second at 2048×1024 resolution.

## 🧩 How it works
The model required three types of work to run on the NeuronCores: tensor parallelism to make the model run, sequence parallelism to split it over more cores, and host optimizations to keep up with the NeuronCores. Out of the box, the transformer did not fit on one core, and diffusers had no plan to split it. The first attempt took about 5 minutes 20 seconds for a 10-second clip, with NeuronCores computing for only about 45 seconds of that time.

## ⚙️ Key details
The workflow uses a JSON file acting as a storyboard, where each shot has a name and a long prompt describing style, subject, motion, camera, light, and sound. Shots can link to earlier or later shots using `from` and `to` keys to maintain continuity of look or motion, and can be trimmed or captioned. Three diffusers pipelines are used:

| Pipeline | Function |
| :--- | :--- |
| LTX2Pipeline | Generates shots from prompts alone using an 8-step distilled recipe |
| LTX2ConditionPipeline | Generates shots that start or end on frames of another shot |
| LTX2LatentUpsamplePipeline | Upscales latents ×2 before 3 final steps |

The film assembly logic is approximately 160 lines of Python that reads the JSON, orders shots so keyframes exist before they are needed, cuts frames, trims, captions, evens out sound, and assembles the final video.

## 🚀 Availability
The code is available in the `dacorvo/video-generation` repository. Sample films, including a seal, a fox, and a goat, are stored in the `dacorvo/video-generation` bucket alongside their JSON files.

#AWS #Trainium #Lightricks #Diffusers #VideoGeneration

---

*Source: [Taking Trainium3 to the Track: Generating Videos with LTX-2.5](https://huggingface.co/blog/video-trainium3)*
