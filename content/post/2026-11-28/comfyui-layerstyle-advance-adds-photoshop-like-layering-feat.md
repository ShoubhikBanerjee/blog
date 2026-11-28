---
title: "ComfyUI LayerStyle Advance Adds Photoshop‑Like Layering Features"
slug: "comfyui-layerstyle-advance-adds-photoshoplike-layering-features"
description: "A new set of ComfyUI nodes called ComfyUI_LayerStyle_Advance now provides Photoshop‑like layering and masking functionality, bringing advanced image editing directly into the ComfyUI workflow."
date: 2026-11-28T18:07:42+05:30
tags: [ComfyUI, LayerStyle, ImageEditing, OpenSource, Python]
categories: ["AI", "Computer Vision", "Machine Learning", "Software Development", "Artificial Intelligence"]
image: "https://avatars.githubusercontent.com/u/130118553?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# ComfyUI LayerStyle Advance Adds Photoshop‑Like Layering Features

A new set of ComfyUI nodes called ComfyUI_LayerStyle_Advance now provides Photoshop‑like layering and masking functionality, bringing advanced image editing directly into the ComfyUI workflow.

## 🔍 Overview
- Provides Photoshop‑like compositing of layers and masks.
- Migrates basic Photoshop functions to ComfyUI.
- Nodes are split into repositories to reduce dependency problems.

## 🧩 How it Works
- The plugin includes many LayerMask and LayerUtility nodes (examples listed below).
- Each node handles specific tasks such as mask generation, image auto‑crop, color tone extraction, etc.

## ⚙️ Key Details
### Node Table
| Node | Type |
|------|------|
| BiRefNetUltra | LayerMask |
| BiRefNetUltraV2 | LayerMask |
| LoadBiRefNetModel | LayerMask |
| LoadBiRefNetModelV2 | LayerMask |
| EVFSAMUltra | LayerMask |
| Florence2Ultra | LayerMask |
| LoadFlorence2Model | LayerMask |
| Florence2Image2Prompt | LayerUtility |
| GetColorTone | LayerUtility |
| GetColorToneV2 | LayerUtility |
| HumanPartsUltra | LayerMask |
| BenUltra | LayerMask |
| LoadBenModel | LayerMask |
| ImageAutoCrop | LayerUtility |
| ImageAutoCropV2 | LayerUtility |
| ImageAutoCropV3 | LayerUtility |
| ImageRewardFilter | LayerUtility |
| LoadJoyCaption2Model | LayerUtility |
| JoyCaption2Split | LayerUtility |
| JoyCaption2 | LayerUtility |
| JoyCaption2ExtraOptions | LayerUtility |
| LaMa | LayerUtility |
| LlamaVision | LayerUtility |
| LoadPSD | LayerUtility |
| MaskByDifferent | LayerMask |
| MediapipeFacialSegment | LayerMask |
| BBoxJoin | LayerMask |
| DrawBBoxMask | LayerMask |
| ObjectDetectorFL2 | LayerMask |
| ObjectDetectorMask | LayerMask |
| ObjectDetectorYOLO8 | LayerMask |
| ObjectDetectorYOLOWorld | LayerMask |
| PersonMaskUltra | LayerMask |
| PersonMaskUltra V2 | LayerMask |
| PhiPrompt | LayerUtility |
| PromptEmbellish | LayerUtility |
| PromptTagger | LayerUtility |
| CreateQRCode | LayerUtility |
| DecodeQRCode | LayerUtility |
| QWenImage2Prompt | LayerUtility |
| SAM2Ultra | LayerMask |
| SAM2VideoUltra | LayerMask |
| SaveImagePlus | LayerUtility |
| SD3NegativeConditioning | LayerUtility |
| SegmentAnythingUltra | LayerMask |
| SegmentAnythingUltra V2 | LayerMask |
| TransparentBackgroundUltra | LayerMask |
| UserPromptGeneratorTxt2ImgPrompt | LayerUtility |
| UserPromptGeneratorTxt2ImgPromptWithReference | LayerUtility |
| UserPromptGeneratorReplaceWord | LayerUtility |
| AddBlindWaterMark | LayerUtility |
| ShowBlindWaterMark | LayerUtility |
| YoloV8Detect | LayerMask |

### Installation
- Recommended: Use ComfyUI Manager to install the plugin.
- Manual install:
  1. Open a command prompt in the plugin directory (`ComfyUI\\custom_nodes`).
  2. Run `git clone https://github.com/chflame163/ComfyUI_LayerStyle.git`.
  3. Or download the zip, extract, and copy the folder to `ComfyUI\\custom_nodes`.

- For ComfyUI official portable package:
  - Double‑click `install_requirements.bat` in the plugin directory.
  - Or install dependencies manually:
    ```
    ..\\..\\..\\python_embeded\\python.exe -s -m pip install -r requirements.txt
    .\\repair_dependency.bat
    ```

- For Aki ComfyUI package:
  - Double‑click `install_requirements_aki.bat` in the plugin directory.
  - Or install dependencies manually:
    ```
    ..\\..\\python\\python.exe -s -m pip install -r requirements.txt
    .\\repair_dependency_aki.bat
    ```

- Restart ComfyUI after installation.

### Model Files
- Model files are available from BaiduNetdisk or QuarkNetdisk for domestic users, or from HuggingFace.
- Download all files and copy them to `ComfyUI\\models`.
- Some nodes marked “Ultra” use the vitmatte model. Download it from https://huggingface.co/hustvl/vitmatte-small-composition-1k/tree/main and copy to `ComfyUI\\models\\vitmatte`.

### Troubleshooting
- If nodes cannot load, check the ComfyUI terminal for error messages.
- A warning about missing `*.ini` files can be ignored; it does not affect usage.
- To hide these warnings, rename all `*.ini.example` files in the plugin directory to `*.ini`.

### Version Rollback
- If a problem is caused by splitting the warehouse, roll back the plugin to commit `3d4a3526a9d1a19671a133e9215077bda520ee5d`.
- Open a terminal in the plugin directory and run:
  ```
  git reset --hard 3d4a3526a9d1a19671a133e9215077bda520ee5d
  ```

## 🚀 Availability
- GitHub repository: https://github.com/chflame163/ComfyUI_LayerStyle_Advance
- Download links for the plugin and model files are provided in the README.

## 💡 Why it Matters
- Centralizes Photoshop‑like functions within ComfyUI, reducing the need to switch between software.
- Enables a streamlined, single‑environment workflow for image editing and generation.

## 📬 Contact
- Business cooperation: [chflame@163.com](mailto:chflame@163.com)

#ComfyUI #LayerStyle #ImageEditing #OpenSource #Python

---

*Source: [chflame163/ComfyUI_LayerStyle](https://github.com/chflame163/ComfyUI_LayerStyle)*
