---
title: "DeepSeek-OCR: Revolutionizing Optical Character Recognition with Context Compression"
description: "Advanced OCR technology that pushes the boundaries of visual-text compression with innovative context optical compression techniques and vLLM integration."
date: 2025-10-28T01:00:03.545062+05:30
tags: ["DeepSeek-OCR", "Optical Character Recognition", "Computer Vision", "Machine Learning", "AI", "vLLM", "Document Processing", "Context Compression", "Transformers", "CUDA"]
categories: ["Artificial Intelligence", "Computer Vision", "Machine Learning"]
image: "https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/logo.svg?raw=true"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 DeepSeek-OCR: Revolutionizing Optical Character Recognition with Context Compression

![DeepSeek AI](https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/logo.svg?raw=true)

*Advanced OCR technology that pushes the boundaries of visual-text compression*

---

[![Homepage](https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/badge.svg?raw=true)](h
ttps://github.com/deepseek-ai/DeepSeek-V2)
[![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-DeepSeek%20AI-ffc107
?color=ffc107&logoColor=white)](https://huggingface.co/deepseek-ai)

[![Discord](https://img.shields.io/badge/Discord-DeepSeek%20AI-7289da?logo=discord&logoColor=whi
te&color=7289da)](https://discord.gg/deepseek-ai)
[![Twitter Follow](https://img.shields.io/badge/Twitter-deepseek_ai-white?logo=x&logoColor=white
)](https://twitter.com/deepseek_ai)

**Quick Links:** [🌟 Github](https://github.com/deepseek-ai) | [📥 Model
Download](https://huggingface.co/deepseek-ai/DeepSeek-OCR) | [📄 Paper
Link](https://arxiv.org/abs/2510.18234) | [📄 Arxiv Paper
Link](https://arxiv.org/abs/2510.18234)

## 🔍 Overview

DeepSeek-OCR represents a breakthrough in optical character recognition technology, introducing
innovative context optical compression techniques. This state-of-the-art model demonstrates
exceptional capabilities in processing visual content and converting it to structured text
formats.

![DeepSeek-OCR
Demonstration](https://huggingface.co/deepseek-ai/DeepSeek-OCR/resolve/main/assets/fig1.png)

*Explore the boundaries of visual-text compression with DeepSeek-OCR*

The model excels at understanding complex document layouts, extracting text from images, and
maintaining contextual relationships between visual and textual elements. With its advanced
compression algorithms, DeepSeek-OCR offers superior performance in document digitization tasks.

## ⚙️ Usage

### 🛠️ Installation Requirement

Before getting started, ensure your environment meets the following specifications. The
requirements have been tested on Python 3.12.9 with CUDA 11.8:

```bash
torch==2.6.0
transformers==4.46.3
tokenizers==0.20.3
einops
addict
easydict
pip install flash-attn==2.7.3 --no-build-isolation
```

### 💻 Basic Implementation

Here's how to implement DeepSeek-OCR using Hugging Face transformers on NVIDIA GPUs:

```python
from transformers import AutoModel, AutoTokenizer
import torch
import os

os.environ["CUDA_VISIBLE_DEVICES"] = '0'

model_name = 'deepseek-ai/DeepSeek-OCR'
tokenizer = AutoTokenizer.from_pretrained(model_name, trust_remote_code=True)
model = AutoModel.from_pretrained(
    model_name,
    _attn_implementation='flash_attention_2',
    trust_remote_code=True,
    use_safetensors=True
)
model = model.eval().cuda().to(torch.bfloat16)

# Basic OCR prompt
# prompt = "<image>\nFree OCR. "

# Advanced grounding prompt for markdown conversion
prompt = "<image>\n<|grounding|>Convert the document to markdown. "

image_file = 'your_image.jpg'
output_path = 'your/output/dir'

# Configuration options:
# Tiny: base_size = 512, image_size = 512, crop_mode = False
# Small: base_size = 640, image_size = 640, crop_mode = False
# Base: base_size = 1024, image_size = 1024, crop_mode = False
# Large: base_size = 1280, image_size = 1280, crop_mode = False
# Gundam: base_size = 1024, image_size = 640, crop_mode = True

res = model.infer(
    tokenizer,
    prompt=prompt,
    image_file=image_file,
    output_path=output_path,
    base_size=1024,
    image_size=640,
    crop_mode=True,
    save_results=True,
    test_compress=True
)
```

## 🚀 vLLM Integration

DeepSeek-OCR now enjoys official support in upstream vLLM, enabling accelerated inference and
enhanced PDF processing capabilities. For comprehensive guidance on model inference
acceleration, visit the [🌟 GitHub repository](https://github.com/deepseek-ai).

### 🔧 vLLM Setup

```bash
uv venv
source .venv/bin/activate

# Until v0.11.1 release, install vLLM from nightly build
uv pip install -U vllm --pre --extra-index-url https://wheels.vllm.ai/nightly
```

### 🏃‍♂️ vLLM Implementat

```python
from vllm import LLM, SamplingParams
from vllm.model_executor.models.deepseek_ocr import NGramPerReqLogitsProcessor
from PIL import Image

# Create model instance
llm = LLM(
    model="deepseek-ai/DeepSeek-OCR",
    enable_prefix_caching=False,
    mm_processor_cache_gb=0,
    logits_processors=[NGramPerReqLogitsProcessor]
)

# Prepare batched input with your image files
image_1 = Image.open("path/to/your/image_1.png").convert("RGB")
image_2 = Image.open("path/to/your/image_2.png").convert("RGB")

prompt = "<image>\nFree OCR."

model_input = [
    {
        "prompt": prompt,
        "multi_modal_data": {"image": image_1}
    },
    {
        "prompt": prompt,
        "multi_modal_data": {"image": image_2}
    }
]

sampling_param = SamplingParams(
    temperature=0.0,
    max_tokens=8192,
    # ngram logit processor args
    extra_args=dict(
        ngram_size=30,
        window_size=90,
        whitelist_token_ids={128821, 128822},  # whitelist: <td>, </td>
    ),
    skip_special_tokens=False,
)

# Generate output
model_outputs = llm.generate(model_input, sampling_param)

# Print output
for output in model_outputs:
    print(output.outputs[0].text)
```

## 📊 Visualizations

The following examples demonstrate DeepSeek-OCR's capabilities across various document types and
 layouts:

| Example 1 | Example 2 |
|-----------|-----------|
| ![OCR Example
1](https://huggingface.co/deepseek-ai/DeepSeek-OCR/resolve/main/assets/show1.jpg) | ![OCR
Example 2](https://huggingface.co/deepseek-ai/DeepSeek-OCR/resolve/main/assets/show2.jpg) |

| Example 3 | Example 4 |
|-----------|-----------|
| ![OCR Example
3](https://huggingface.co/deepseek-ai/DeepSeek-OCR/resolve/main/assets/show3.jpg) | ![OCR
Example 4](https://huggingface.co/deepseek-ai/DeepSeek-OCR/resolve/main/assets/show4.jpg) |

*These visualizations showcase DeepSeek-OCR's versatility in handling different document formats
 and layouts*

## 🙌 Acknowledgement

The development of DeepSeek-OCR builds upon valuable contributions from the open-source
community. We extend our gratitude to the following projects and their teams:

**Core Technologies:**
- [Vary](https://github.com/Vary-ai/Vary) - Visual understanding frameworks
- [GOT-OCR2.0](https://github.com/Ucas-HaoranWei/GOT-OCR2.0) - Advanced OCR methodologies
- [MinerU](https://github.com/opendatalab/MinerU) - Document processing utilities
- [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR) - OCR toolkit foundations
- [OneChart](https://github.com/UniModal4Reasoning/ChartVLM) - Chart understanding capabilities
- [Slow Perception](https://github.com/yfzhang114/SlowFast) - Visual perception models

**Evaluation Benchmarks:**
- [Fox](https://github.com/ucaslcl/FOX) - Comprehensive evaluation framework
- [OminiDocBench](https://github.com/opendatalab/OminiDocBench) - Document understanding
benchmarks

These collaborative efforts have been instrumental in advancing the field of optical character
recognition and visual understanding.

## 📚 Citation

If you use DeepSeek-OCR in your research or applications, please cite our work:

```bibtex
@article{wei2025deepseek,
  title={DeepSeek-OCR: Contexts Optical Compression},
  author={Wei, Haoran and Sun, Yaofeng and Li, Yukun},
  journal={arXiv preprint arXiv:2510.18234},
  year={2025}
}
```

## 🙌 Credits

*Originally posted at: https://huggingface.co/deepseek-ai/DeepSeek-OCR*

## ✅ Final Thoughts

DeepSeek-OCR represents a significant advancement in optical character recognition technology,
offering researchers and developers a powerful tool for visual-text compression and document
digitization. With its innovative context compression techniques and seamless integration with
popular frameworks like vLLM, this model opens new possibilities for automated document
processing workflows.

The model's impressive performance across various document types, combined with its efficient
inference capabilities, makes it an excellent choice for production environments requiring
reliable OCR functionality. Whether you're working on document digitization, data extraction, or
 visual understanding tasks, DeepSeek-OCR provides the advanced capabilities needed to achieve
exceptional results.

---

*#DEEPSEEK #OCR #AI #MACHINELEARNING #COMPUTERVISION #DOCUMENTPROCESSING #VLLM #TRANSFORMERS*

