---
title: "FlashVSR: Towards Real-Time Diffusion-Based Streaming Video Super-Resolution"
description: "A breakthrough diffusion-based framework achieving real-time video
super-resolution at 17 FPS with state-of-the-art performance and up to 12× speedup over existing
 models."
date: 2025-10-28T00:46:31.535613+05:30
tags: ["Video Super-Resolution", "Diffusion Models", "Real-Time Processing", "Machine Learning", "Computer Vision", "Streaming Video", "GPU Acceleration", "Deep Learning", "Image Enhancement", "Neural Networks"]
categories: ["AI", "Computer Vision", "Video Processing"]
image: "https://raw.githubusercontent.com/OpenImagingLab/FlashVSR/main/examples/WanVSR/assets/teaser.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# ⚡ FlashVSR: Towards Real-Time Diffusion-Based Streaming Video Super-Resolution

![FlashVSR Teaser](https://raw.githubusercontent.com/OpenImagingLab/FlashVSR/main/examples/WanVSR/assets/teaser.png)
*FlashVSR demonstrates real-time video super-resolution capabilities with state-of-the-art
performance*

**Authors:** Junhao Zhuang, Shi Guo, Xin Cai, Xiaohui Li, Yihao Liu, Chun Yuan, Tianfan Xue

[![Project Page](https://img.shields.io/badge/Project-Page-Green)](https://openimaginglabs.github.io/FlashVSR/)
[![GitHub Repository](https://img.shields.io/badge/GitHub-Repository-black?logo=github)](https://github.com/OpenImagingLab/FlashVSR)
[![🤗 Hugging Face Model](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Model-blue)](https://huggingface.co/JunhaoZhuang/FlashVSR)
[![🤗 Hugging Face Dataset](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Dataset-orange)](https://huggingface.co/JunhaoZhuang/FlashVSR)
[![arXiv](https://img.shields.io/badge/arXiv-2510.12747-b31b1b.svg)](https://arxiv.org/abs/2510.12747)

---

## 🌟 Abstract

Diffusion models have recently advanced video restoration, but applying them to real-world video
 super-resolution (VSR) remains challenging due to high latency, prohibitive computation, and
poor generalization to ultra-high resolutions. Our goal in this work is to make diffusion-based
VSR practical by achieving **efficiency, scalability, and real-time performance**.

To this end, we propose **FlashVSR**, the first diffusion-based one-step streaming framework
towards real-time VSR. **FlashVSR runs at ∼17 FPS for 768 × 1408 videos on a single A100 GPU**
by combining three complementary innovations:

1. A train-friendly three-stage distillation pipeline that enables streaming super-resolution
2. Locality-constrained sparse attention that cuts redundant computation while bridging the
train–test resolution gap
3. A tiny conditional decoder that accelerates reconstruction without sacrificing quality

To support large-scale training, we also construct **VSR-120K**, a new dataset with 120k videos
and 180k images. Extensive experiments show that FlashVSR scales reliably to ultra-high
resolutions and achieves **state-of-the-art performance with up to ∼12× speedup** over prior
one-step diffusion VSR models.

---

## 📰 News

- **Release Date:** October 2025 — Inference code and model weights are available now! 🎉
- **Coming Soon:** Dataset release (**VSR-120K**) for large-scale training

--- 
## 📋 TODO

- ✅ Release inference code and model weights
- ⬜ Release dataset (VSR-120K)

--- 
## 🚀 Getting Started

Follow these steps to set up and run **FlashVSR** on your local machine:

### 1️⃣ Clone the Repositor

```bash
git clone https://github.com/OpenImagingLab/FlashVSRcd FlashVSR
```

### 2️⃣ Set Up the Python Environmen

Create and activate the environment (**Python 3.11.13**):

```bash
conda create -n flashvsr python=3.11.13 conda activate flashvsr
```

Install project dependencies:

```bash
pip install -e .
pip install -r requirements.txt
```

### 3️⃣ Install Block-Sparse Attention (Required

FlashVSR relies on the **Block-Sparse Attention** backend to enable flexible and dynamic
attention masking for efficient inference.

```bash
git clone https://github.com/mit-han-lab/Block-Sparse-Attentioncd Block-Sparse-Attention
pip install packaging pip install ninja
python setup.py install
```

**⚠️ Note:** The Block-Sparse Attention backend currently achieves ideal acceleration only on
NVIDIA A100 or A800 GPUs (Ampere architecture). On H100/H800 (Hopper) GPUs, due to differences
in hardware scheduling and sparse kernel behavior, the expected speedup may not be realized, and
 in some cases performance can even be slower than dense attention.

### 4️⃣ Download Model Weights from Hugging Fac

Weights are hosted on **Hugging Face** via **Git LFS**. Please install Git LFS first:

```bash
# From the repo root
cd examples/WanVSR

# Install Git LFS (once per machine)
git lfs install

# Clone the model repository into examples/WanVSR
git lfs clone https://huggingface.co/JunhaoZhuang/FlashVSR
```

After cloning, you should have:

```
./examples/WanVSR/FlashVSR/

 LQ_proj_in.ckpt TCDecoder.ckpt
 Wan2.1_VAE.pth diffusion_pytorch_model_streaming_dmd.safetensors
 README.md
```

> The inference scripts will load weights from `./examples/WanVSR/FlashVSR/` by default.

### 5️⃣ Run Inferenc

```bash
# From the repo root
cd examples/WanVSR python infer_flashvsr_full.py  # Full model
# or
python infer_flashvsr_tiny.py  # Tiny model
```

--- 
## 🛠️ Metho

The overview of **FlashVSR**. This framework features:

- **Three-Stage Distillation Pipeline** for streaming VSR training
- **Locality-Constrained Sparse Attention** to cut redundant computation and bridge the
train–test resolution gap
- **Tiny Conditional Decoder** for efficient, high-quality reconstruction
- **VSR-120K Dataset** consisting of **120k videos** and **180k images**, supports joint
training on both images and videos

![FlashVSR Architecture](https://raw.githubusercontent.com/OpenImagingLab/FlashVSR/main/examples/WanVSR/assets/flowchart.jpg)
*FlashVSR methodology overview showing the three-stage distillation pipeline and sparse
attention mechanisms*

--- 
## 🤗 Feedback & Support

We welcome feedback and issues. Thank you for trying **FlashVSR**!

Feel free to reach out through GitHub issues or contact the authors directly for support and
collaboration opportunities.

--- 
## 📄 Acknowledgments

We gratefully acknowledge the following open-source projects:

- **DiffSynth Studio** —
[https://github.com/modelscope/DiffSynth-Studio](https://github.com/modelscope/DiffSynth-Studio)
- **Block-Sparse-Attention** — [https://github.com/mit-han-lab/Block-Sparse-Attention](https://github.com/mit-han-lab/Block-Sparse-Attention)
- **taehv** — [https://github.com/madebyollin/taehv](https://github.com/madebyollin/taehv)

--- 
## 📞 Contact

- **Junhao Zhuang** Email:
[zhuangjh23@mails.tsinghua.edu.cn](mailto:zhuangjh23@mails.tsinghua.edu.cn)

--- 
## 📜 Citation

```bibtex
@misc{zhuang2025flashvsrrealtimediffusionbasedstreaming,
    title={FlashVSR: Towards Real-Time Diffusion-Based Streaming Video Super-Resolution},
    author={Junhao Zhuang and Shi Guo and Xin Cai and Xiaohui Li and Yihao Liu and Chun Yuan and Tianfan Xue},
    year={2025}, eprint={2510.12747},
    archivePrefix={arXiv}, primaryClass={cs.CV},
    url={https://arxiv.org/abs/2510.12747},}
```

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/JunhaoZhuang/FlashVSR*

--- 
## 🏁 Conclusion

FlashVSR represents a significant breakthrough in real-time video super-resolution technology by
 successfully bridging the gap between high-quality diffusion models and practical deployment
requirements. The framework's innovative three-stage distillation pipeline, combined with
locality-constrained sparse attention and a tiny conditional decoder, achieves an impressive
balance between speed and quality.

Key takeaways include:

- **Real-time Performance:** Achieving ∼17 FPS for high-resolution videos on single GPU hardware
- **Scalability:** Successfully handling ultra-high resolutions that were previously impractical
- **Efficiency Gains:** Up to 12× speedup over existing one-step diffusion VSR models
- **Practical Implementation:** Complete inference code and pre-trained models available for
immediate use

The upcoming release of the VSR-120K dataset will further accelerate research in this domain,
providing the community with valuable resources for large-scale video super-resolution training.
 FlashVSR sets a new standard for practical diffusion-based video enhancement applications.

--- 
*#VIDEOSUPERRESOLUTION #DIFFUSIONMODELS #REALTIME #MACHINELEARNING #COMPUTERVISION #AI
#STREAMING #HUGGINGFACE*

