---
title: "Ditto: Scaling Instruction-Based Video Editing with a High-Quality Synthetic Dataset"
description: "A groundbreaking framework for instruction-based video editing that addresses
training data scarcity through innovative synthetic data generation and efficient model
architecture."
date: 2025-10-28T00:48:50.380222+05:30
tags: ["video-editing", "machine-learning", "artificial-intelligence", "computer-vision", "deep-learning", "diffusion-models", "synthetic-data", "instruction-following", "ditto", "editto"]
categories: ["Machine Learning", "Computer Vision", "AI Research"]
image: "https://github.com/EzioBy/Ditto/raw/main/assets/ditto.gif"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🎬 Ditto: Scaling Instruction-Based Video Editing with a High-Quality Synthetic Dataset

![Ditto Video Editing Demo](https://github.com/EzioBy/Ditto/raw/main/assets/ditto.gif)

*Instruction-based video editing results produced by the Ditto framework, enabling high-quality
video editing through natural language instructions.*

This repository introduces the groundbreaking **Ditto** framework and the **Editto** model,
addressing one of the most significant challenges in instruction-based video editing: the
scarcity of high-quality training data. The framework represents a comprehensive solution that
combines innovative data generation, efficient model architecture, and intelligent quality control.

## 📋 Abstract

Instruction-based video editing promises to democratize content creation, yet its progress has
been severely hampered by the scarcity of large-scale, high-quality training data. **Ditto**
introduces a holistic framework designed to tackle this fundamental challenge through several key innovations:

- **🎨 Novel Data Generation Pipeline**: Fuses the creative diversity of a leading image editor
with an in-context video generator, overcoming the limited scope of existing models
- **⚡ Efficient Architecture**: Employs a distilled model architecture augmented by a temporal
enhancer, reducing computational overhead while improving temporal coherence
- **🤖 Intelligent Agent**: Crafts diverse instructions and rigorously filters output, ensuring
quality control at scale

Using this framework, the team invested over **12,000 GPU-days** to build **Ditto-1M**, a new
dataset of one million high-fidelity video editing examples. The resulting **Editto** model
demonstrates superior instruction-following ability and establishes a new state-of-the-art in
instruction-based video editing.

## 🔗 Resources

- 📄 [Research Paper](https://arxiv.org/abs/2510.15742)
- 🌐 [Project Page](https://ditto-video-editing.github.io/)
- 💻 [GitHub Repository](https://github.com/EzioBy/Ditto)
- 📦 [Model Weights (Hugging Face)](https://huggingface.co/QingyanBai/Ditto_models)
- 📊 [Dataset (Hugging Face)](https://huggingface.co/datasets/QingyanBai/Ditto-1M)

---

## 🚀 Model Usage

### 1. Using with DiffSynth

#### ⚙️ Environment Setup

```bash
# Create conda environment (if you already have a DiffSynth conda environment, you can reuse it)
conda create -n ditto python=3.10
conda activate ditto
pip install -e .
```

#### 📥 Download Models

Download the base model and Ditto models from Google Drive or Hugging Face:

```bash
# Download Wan-AI/Wan2.1-VACE-14B from Hugging Face to models/Wan-AI/
huggingface-cli download Wan-AI/Wan2.1-VACE-14B --local-dir models/Wan-AI/

# Download Ditto models
huggingface-cli download QingyanBai/Ditto_models --include="models/*" --local-dir ./
```

#### 🎯 Usage

You can either use the provided script or run Python directly:

```bash
# Option 1: Use the provided script
bash infer.sh

# Option 2: Run Python directly
python inference/infer_ditto.py \
  --input_video /path/to/input_video.mp4 \
  --output_video /path/to/output_video.mp4 \
  --prompt "Editing instruction." \
  --lora_path /path/to/model.safetensors \
  --num_frames 73 \
  --device_id 0
```

Test cases can be found at the [HF
Dataset](https://huggingface.co/datasets/QingyanBai/Ditto-1M). Reference editing prompts are
available in `inference/example_prompts.txt`.

### 2. Using with ComfyUI

*Note: ComfyUI runs faster with lower computational requirements (832×480x73 videos need 11G GPU
 memory and ~4min on A6000). However, due to quantized and distilled models, there may be some
quality degradation.*

#### ⚙️ Environment Setup

First, follow the [ComfyUI installation guide](https://github.com/comfyanonymous/ComfyUI) to set
 up the base environment. We strongly recommend installing
[ComfyUI-Manager](https://github.com/Comfy-Org/ComfyUI-Manager) for easy custom node management:

```bash
# Install ComfyUI-Manager
cd ComfyUI/custom_nodes
git clone https://github.com/Comfy-Org/ComfyUI-Manager.git
```

After installing ComfyUI, you can either:

**Option 1** (Recommended): Use ComfyUI-Manager to automatically install all required custom
nodes with the "Install Missing Custom Nodes" function.

**Option 2**: Manually install the required custom nodes:
- [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper)
- [KJNodes for ComfyUI](https://github.com/kijai/ComfyUI-KJNodes)
- [comfyui-mixlab-nodes](https://github.com/shadowcz007/comfyui-mixlab-nodes)
- [ComfyUI-VideoHelperSuite](https://github.com/Kosinkadink/ComfyUI-VideoHelperSuite)

#### 📥 Download Models

Download the required model weights from
[Kijai/WanVideo_comfy](https://huggingface.co/Kijai/WanVideo_comfy) to subfolders of `models/`:

| File | Destination |
| --- | --- |
| `Wan2_1-T2V-14B_fp8_e4m3fn.safetensors` | `diffusion_models/` |
| `Wan21_CausVid_14B_T2V_lora_rank32_v2.safetensors` | `loras/` |
| `Wan2_1_VAE_bf16.safetensors` | `vae/wan/` |
| `umt5-xxl-enc-bf16.safetensors` | `text_encoders/` |

Download Ditto models from Google Drive or Hugging Face to `diffusion_models/` (use VACE Module
Select node for loading).

#### 🎯 Usage

Use the workflow `ditto_comfyui_workflow.json` in this repository to get started. Reference
prompts are provided in the notes. Test cases can be found at the [HF
Dataset](https://huggingface.co/datasets/QingyanBai/Ditto-1M).

💡 *Tip: For sim2real cases, try prompts like "Turn it into the real domain".*

---

## 📝 Citation

If you find this work useful, please consider citing the paper:

```bibtex
@article{bai2025ditto, title={Scaling Instruction-Based Video Editing with a High-Quality Synthetic Dataset},
  author={Bai, Qingyan and Wang, Qiuyu and Ouyang, Hao and Yu, Yue and Wang, Hanlin and Wang,
Wen and Cheng, Ka Leong and Ma, Shuailei and Zeng, Yanhong and Liu, Zichen and Xu, Yinghao and
Shen, Yujun and Chen, Qifeng}, journal={arXiv preprint arXiv:2510.15742},
  year={2025} }
```

## 🙏 Acknowledgments

The authors thank [Wan](https://github.com/wanghanlin/Wan) &
[VACE](https://github.com/wanghanlin/VACE) & [Qwen-Image](https://github.com/QwenLM/Qwen2-VL)for providing powerful foundation models, and [QwenVL](https://github.com/QwenLM/Qwen2-VL) for
advanced visual understanding capabilities. Special thanks to
[DiffSynth-Studio](https://github.com/modelscope/DiffSynth-Studio) serving as the codebase for this repository.

## 📜 License

This project is licensed under the [CC BY-NC-SA 4.0 (Creative Commons
Attribution-NonCommercial-ShareAlike 4.0 International License)](https://creativecommons.org/licenses/by-nc-sa/4.0/).

The code is provided for academic research purposes only.

For any questions, please contact [qingyanbai@hotmail.com](mailto:qingyanbai@hotmail.com).

## 🙌 Credits

*Originally posted at: https://huggingface.co/QingyanBai/Ditto_models*

## 🏁 Conclusion

The Ditto framework represents a significant advancement in instruction-based video editing,
successfully addressing the critical challenge of training data scarcity through innovative
synthetic data generation. With its comprehensive pipeline that combines intelligent data
creation, efficient model architecture, and rigorous quality control, Ditto-1M provides the
foundation for training state-of-the-art video editing models like Editto.

The framework's practical implementations through both DiffSynth and ComfyUI make it accessible
to researchers and practitioners, while maintaining high-quality results. This work opens new
possibilities for democratizing video content creation through natural language instructions,
setting a new benchmark for future developments in the field.

*#VIDEOEDITING #MACHINELEARNING #ARTIFICIALINTELLIGENCE #COMPUTERVISION #DEEPLEARNING #DIFFUSION
 #SYNTHETICDATA #DITTO*

