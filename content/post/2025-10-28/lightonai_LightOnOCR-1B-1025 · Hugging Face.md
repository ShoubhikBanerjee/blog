---
title: "LightOnOCR-1B-1025: Revolutionary End-to-End OCR Model for Document Understanding"
description: "A comprehensive guide to LightOnOCR-1B, a state-of-the-art compact vision-language
 model that achieves exceptional OCR accuracy while being 5× faster and more cost-effective than
 traditional solutions."
date: 2025-10-28T00:52:37.466590+05:30
tags: ["OCR", "Vision-Language Model", "Document Understanding", "AI", "Machine Learning", "PDF Processing", "Text Extraction", "Computer Vision", "Deep Learning", "HuggingFace"]
categories: ["Artificial Intelligence", "Computer Vision", "Machine Learning"]
image: "https://huggingface.co/lightonai/LightOnOCR-1B-1025/resolve/main/lightonocr-banner.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# Response

![LightOn OCR-1B Banner](https://huggingface.co/lightonai/LightOnOCR-1B-1025/resolve/main/lightonocr-banner.png)
*LightOnOCR-1B: State-of-the-art OCR model for document understanding*

# 🔍 LightOnOCR-1B-1025: Revolutionary End-to-End OCR Model

**LightOnOCR-1B** is a compact, end-to-end vision–language model for Optical Character
Recognition (OCR) and document understanding. It achieves state-of-the-art accuracy in its
weight class while being several times faster and cheaper than larger general-purpose VLMs.

This full BF16 version of the model is recommended for further fine-tuning or research use,
offering unparalleled efficiency in document processing tasks.

📝 **[Read the full blog post](https://huggingface.co/blog/lightonai/lightonocr)** | 🚀 **[Try
the demo](https://huggingface.co/spaces/lightonai/LightOnOCR-1B-Demo)**

---

## ✨ Key Highlights

- ⚡ **Speed:** 5× faster than dots.ocr, 2× faster than PaddleOCR-VL-0.9B, 1.73× faster than
DeepSeekOCR
- 💸 **Efficiency:** Processes 5.71 pages/s on a single H100 (~493k pages/day) for **<$0.01 per
1,000 pages**
- 🧠 **End-to-End:** Fully differentiable, no external OCR pipeline
- 🧾 **Versatile:** Handles tables, receipts, forms, multi-column layouts, and math notation
- 🌍 **Compact variants:** 32k and 16k vocab options for European languages

---

## 🔧 Model Overview

**LightOnOCR** combines a Vision Transformer encoder (Pixtral-based) with a lightweight text
decoder (Qwen3-based) distilled from high-quality open VLMs. The model is specifically optimized
 for document parsing tasks, producing accurate, layout-aware text extraction from high-resolution pages.

This innovative architecture enables the model to understand complex document structures while
maintaining exceptional processing speed and cost efficiency.

--- 
## 📊 Benchmarks

| Model | ArXiv | Old Scans | Math | Tables | Multi-Column | Tiny Text | Base | Overall |
|-------|-------|-----------|------|--------|--------------|-----------|------|---------|
| **[LightOnOCR-1B-1025](https://huggingface.co/lightonai/LightOnOCR-1B-1025)** (151k vocab) |
81.4 | 71.6 | 76.4 | 35.2 | 80.0 | 88.7 | 99.5 | **76.1** |
| **[LightOnOCR-1B-32k](https://huggingface.co/lightonai/LightOnOCR-1B-32k)** (32k vocab) | 80.6
 | 66.2 | 73.5 | 33.5 | 71.2 | 87.6 | 99.5 | **73.1** |
| **[LightOnOCR-1B-16k](https://huggingface.co/lightonai/LightOnOCR-1B-16k)** (16k vocab) | 82.3
 | 72.9 | 75.3 | 33.5 | 78.6 | 85.1 | 99.8 | **75.4** |

All benchmarks evaluated using **vLLM** on the Olmo-Bench.

--- 
## 🛠️ Installatio

```bash
uv venv --python 3.12 --seed source .venv/bin/activate
uv pip install -U vllm \ --torch-backend=auto \
  --extra-index-url https://wheels.vllm.ai/nightly \ --prerelease=allow

# if this fails try adding triton-kernels package
'triton-kernels @ git+https://github.com/triton-lang/triton.git@v3.5.0#subdirectory=python/triton_kernels'

uv pip install pypdfium2 pillow requests
```

--- 
## 🚀 Start Server

```bash
vllm serve lightonai/LightOnOCR-1B-1025 \ --limit-mm-per-prompt '{"image": 1}' \
  --async-scheduling
```

--- 
## 📄 PDF Inference

```python
import base64 import requests
import pypdfium2 as pdfium import io

ENDPOINT = "http://localhost:8000/v1/chat/completions"MODEL = "lightonai/LightOnOCR-1B-1025"

# Download PDF from arXiv
pdf_url = "https://arxiv.org/pdf/2412.13663"pdf_data = requests.get(pdf_url).content

# Open PDF and convert first page to image
pdf = pdfium.PdfDocument(pdf_data) page = pdf[0]

# Render at 200 DPI (scale factor = 200/72 ≈ 2.77)
pil_image = page.render(scale=2.77).to_pil()

# Convert to base64
buffer = io.BytesIO() pil_image.save(buffer, format="PNG")
image_base64 = base64.b64encode(buffer.getvalue()).decode('utf-8')

# Make request
payload = { "model": MODEL,
    "messages": [{ "role": "user",
        "content": [{ "type": "image_url",
            "image_url": {"url": f"data:image/png;base64,{image_base64}"} }]
    }], "max_tokens": 4096,
    "temperature": 0.2, "top_p": 0.9,
}

response = requests.post(ENDPOINT, json=payload) text = response.json()['choices'][0]['message']['content']
print(text)
```

--- 
## 🎨 Rendering and Preprocessing Tips

- Render PDFs to **PNG** or **JPEG** at a target longest dimension of **1540px**
- Maintain aspect ratio to preserve text geometry
- Use one image per page; batching supported by vLLM

These preprocessing guidelines ensure optimal performance and accuracy when processing documents with LightOnOCR.

--- 
## 🔄 Variants

| Variant | Description |
|---------|-------------|
| **[LightOnOCR-1B-1025](https://huggingface.co/lightonai/LightOnOCR-1B-1025)** | Full
multilingual model (default) |
| **[LightOnOCR-1B-32k](https://huggingface.co/lightonai/LightOnOCR-1B-32k)** | Fastest
pruned-vocabulary version (32k tokens) optimized for European languages |
| **[LightOnOCR-1B-16k](https://huggingface.co/lightonai/LightOnOCR-1B-16k)** | Most compact
variant with smallest vocabulary |

--- 
## 🎯 Fine-tuning

**Transformers integration is coming soon for training and inference.**

LightOnOCR is fully differentiable and supports:

- LoRA fine-tuning
- Domain adaptation (receipts, scientific articles, forms, etc.)
- Multilingual fine-tuning with task-specific corpora

Example fine-tuning configurations will be released alongside the dataset, making it easier for
researchers and developers to adapt the model to their specific use cases.

--- 
## 📚 Data

Trained on a diverse large-scale PDF corpus covering:

- Scientific papers, books, receipts, invoices, tables, forms, and handwritten text
- Multiple languages (Latin alphabet dominant)
- Real and synthetic document scans

The dataset will be released under an open license, promoting further research and development in the OCR domain.

--- 
## 📜 License

Apache License 2.0

--- 
## 📖 Citation

```bibtex
@misc{lightonocr2025, title = {LightOnOCR-1B: End-to-End and Efficient Domain-Specific Vision-Language Models for
OCR}, author = {Said Taghadouini and Baptiste Aubertin and Adrien Cavaillès},
  year = {2025}, howpublished = {\url{https://huggingface.co/blog/lightonai/lightonocr}}
}
```

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/lightonai/LightOnOCR-1B-1025*

--- 
## 🏁 Conclusion

LightOnOCR-1B-1025 represents a significant breakthrough in OCR technology, offering an optimal
balance between performance, speed, and cost-effectiveness. With its end-to-end architecture,
versatile document handling capabilities, and exceptional efficiency metrics, this model is
poised to revolutionize document processing workflows across various industries.

The availability of multiple variants ensures that users can choose the most appropriate model
for their specific requirements, whether prioritizing maximum accuracy or optimal processing
speed. The upcoming fine-tuning support and open dataset release will further enhance the
model's utility for specialized applications.

_#OCR #VISIONLANGUAGE #DOCUMENTUNDERSTANDING #AI #MACHINELEARNING #HUGGINGFACE #VLLM #PDF
#TEXTEXTRACTION #DEEPLEARNING_

