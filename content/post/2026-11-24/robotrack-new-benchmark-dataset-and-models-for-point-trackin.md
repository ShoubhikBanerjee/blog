---
title: "RoboTrack: New Benchmark, Dataset, and Models for Point Tracking in Robotics"
slug: "robotrack-new-benchmark-dataset-and-models-for-point-tracking-in-robotics"
description: "Today we release RoboTrack, a new benchmark and training data suite for point tracking in robotic manipulation, along with two new models."
date: 2026-11-24T12:08:32+05:30
tags: [RoboTrack, PointTracking, Robotics, ComputerVision, Dataset]
categories: ["AI", "Machine Learning", "Computer Vision", "Robotics", "Datasets"]
image: "https://cdn-uploads.huggingface.co/production/uploads/638e39b249de7ae552d977b5/0KlbITzhyUGtGPyvi09um.png"
author: "Shoubhik Banerjee"
draft: false
---

# RoboTrack: New Benchmark, Dataset, and Models for Point Tracking in Robotics

Today we release RoboTrack, a new benchmark and training data suite for point tracking in robotic manipulation, along with two new models.

## 🔍 Overview
- RoboTrack‑Bench contains 307 human‑annotated videos from DROID, Ego‑Exo4D, MolmoAct 2, and EgoVerse. 2,522 point tracks are annotated and verified by humans.
- Videos capture robots and human hands manipulating objects across cluttered scenes and first‑ and third‑person viewpoints.
- Annotators prioritize points that move or become occluded, use TAP‑Vid motion estimates to trace each point, and label each track as belonging to a robot/human body, a manipulated object, or a static object.
- A second group of annotators checks every track frame by frame.
- RoboTrack‑Bench includes 33 video pairs recorded simultaneously from two cameras, with the same physical points annotated in both views.

## 🧩 How it works
- The pipeline extends MolmoSpaces, Ai2’s simulation ecosystem for robot learning, to generate dense point tracks from simulated robot manipulation trajectories.
- This produces RoboTrack‑15M, a new synthetic training dataset targeted toward robotic manipulation.
- Two new point tracking models are released:
  - **RoboTracker**: a fine‑tuned AllTracker model using RoboTrack data and techniques.
  - **RoboTracker‑Warp**: trained from CoWTracker.

## ⚙️ Key details
- Evaluations show that leading trackers score 3.0 to 6.6 AJ lower on RoboTrack‑Bench than on the only other real‑video robotics benchmark, RoboTAP.
- The strongest off‑the‑shelf tracker, CoWTracker, drops from 70.5 AJ on RoboTAP to 63.9 AJ on RoboTrack‑Bench.
- Adding RoboTrack‑15M to an existing tracker’s training improves performance on real manipulation video, with gains extending to other tracking benchmarks.
- RoboTracker improves average AJ across the three robotics benchmarks compared with their respective released baselines.
- RoboTracker‑Warp achieves state‑of‑the‑art performance on four of the five benchmarks evaluated.

## 🚀 Availability
- We bring these pieces together on a real robot, using the resulting tracker to help guide pipette handling in wet‑lab tasks.
- Both RoboTrack components and the two new models are publicly released.

## 💡 Why it matters
- RoboTrack‑Bench is harder than existing robot benchmarks, exposing weaknesses across multiple tracker architectures and training data.
- Synthetic data from RoboTrack‑15M can boost real‑world performance and cross‑benchmark generalization.



![figure](https://www.datocms-assets.com/64837/1795407244-robotrack-blog-draft-google-docs-image-1.png)

![figure](https://www.datocms-assets.com/64837/1795407981-robotrack-blog-draft-google-docs-image-3-1.png)

![figure](https://www.datocms-assets.com/64837/1795408512-robotrack-blog-draft-google-docs-image-5.png)

#RoboTrack #PointTracking #Robotics #ComputerVision #Dataset

---

*Source: [RoboTrack: Point tracking for real-world robotic manipulation](https://huggingface.co/blog/allenai/robotrack)*
