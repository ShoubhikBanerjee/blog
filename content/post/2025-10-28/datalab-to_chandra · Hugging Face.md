---
title: "Chandra: Advanced OCR Model for Markdown, HTML & JSON Output"
description: "Comprehensive guide to Chandra OCR model by Datalab, featuring high-accuracy text extraction with layout preservation and multi-format output capabilities."
date: 2025-10-28T00:45:22.399531+05:30
tags: ["OCR", "Machine Learning", "Document Processing", "AI", "Text Extraction", "Layout Preservation", "Hugging Face", "VLLM", "Computer Vision", "Natural Language Processing"]
categories: ["Artificial Intelligence", "Machine Learning", "Document Processing"]
image: "https://cdn-avatars.huggingface.co/v1/production/uploads/67ab6afe315e622f597bf9e8/YOgg0gVYVXZC1PDIHFTWK.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🔍 Chandra: Advanced OCR Model for Markdown, HTML & JSON Output

![Chandra OCR Model](https://cdn-avatars.huggingface.co/v1/production/uploads/67ab6afe315e622f597bf9e8/YOgg0gVYVXZC1PDIHFTWK.png)
*Chandra OCR model by Datalab - High-accuracy text extraction with layout preservation*

## 🚀 Introduction

Chandra is a cutting-edge OCR (Optical Character Recognition) model developed by Datalab that
revolutionizes document processing by outputting content in markdown, HTML, and JSON formats.
What sets Chandra apart is its exceptional accuracy in extracting text from images and PDFs
while maintaining the original layout information intact.

You can experience Chandra through their free playground or via hosted API services, making it
accessible for both testing and production environments.

## ⚙️ Key Features

Chandra offers a comprehensive suite of capabilities that make it stand out in the OCR landscape:

- **Multi-format Output**: Convert documents to markdown, HTML, or JSON with detailed layout
preservation
- **Handwriting Recognition**: Robust support for handwritten text extraction
- **Form Reconstruction**: Accurately reconstructs forms, including checkboxes and interactive
elements
- **Complex Layout Support**: Excellent handling of tables, mathematical expressions, and
intricate document structures
- **Visual Content Extraction**: Extracts images and diagrams with captions and structured
metadata
- **Multilingual Support**: Compatible with 40+ languages for global document processing

## 🏃‍♂️ Quickstart Gu

Getting started with Chandra is straightforward using the CLI tools:

```bash
pip install chandra-ocr

# With VLLM
chandra_vllm chandra input.pdf ./output

# With HuggingFace
chandra input.pdf ./output --method hf

# Interactive streamlit app
chandra_app
```

## 📊 Performance Benchmarks

Chandra demonstrates superior performance across various document types using the olmocr
benchmark, currently the most reliable OCR evaluation standard.

![Benchmark Results](datalab-to/chandra/resolve/main/bench.png)
*Comprehensive benchmark comparison showing Chandra's leading performance*

### Detailed Performance Metrics

| **Model** | ArXiv | Old Scans Math | Tables | Old Scans | Headers/Footers | Multi Column |
Long Tiny Text | Base | **Overall** | Source |
|-----------|-------|----------------|--------|-----------|-----------------|--------------|---- ------------|------|-------------|--------|
| **Datalab Chandra v0.1.0** | 82.2 | **80.3** | **88.0** | **50.4** | 90.8 | 81.2 | **92.3** |
**99.9** | **83.1 ± 0.9** | Own benchmarks |
| Datalab Marker v1.10.0 | **83.8** | 69.7 | 74.8 | 32.3 | 86.6 | 79.4 | 85.7 | 99.6 | 76.5 ±
1.0 | Own benchmarks |
| Mistral OCR API | 77.2 | 67.5 | 60.6 | 29.3 | 93.6 | 71.3 | 77.1 | 99.4 | 72.0 ± 1.1 | olmocr
repo |
| Deepseek OCR | 75.2 | 72.3 | 79.7 | 33.3 | 96.1 | 66.7 | 80.1 | 99.7 | 75.4 ± 1.0 | Own
benchmarks |
| GPT-4o (Anchored) | 53.5 | 74.5 | 70.0 | 40.7 | 93.8 | 69.3 | 60.6 | 96.8 | 69.9 ± 1.1 |
olmocr repo |
| olmOCR v0.3.0 | 78.6 | 79.9 | 72.9 | 43.9 | **95.1** | 77.3 | 81.2 | 98.9 | 78.5 ± 1.1 |
olmocr repo |
| dots.ocr | 82.1 | 64.2 | 88.3 | 40.9 | 94.1 | **82.4** | 81.2 | 99.5 | 79.1 ± 1.0 | dots.ocr
repo |

## 📁 Practical Examples

![Handwritten Form Example](datalab-to/chandra/resolve/main/handwritten_form.png)
*Chandra successfully processing a complex handwritten form with multiple fields*

### Document Type Coverage

| Type | Name | Example |
|------|------|---------|
| **Tables** | Water Damage Form | Complex insurance forms with structured data |
| **Tables** | 10K Filing | Financial documents with detailed tabular information |
| **Forms** | Handwritten Form | Personal forms with handwritten entries |
| **Forms** | Lease Agreement | Legal documents with multiple sections |
| **Handwriting** | Doctor Note | Medical prescriptions and notes |
| **Handwriting** | Math Homework | Educational content with equations |
| **Books** | Geography Textbook | Academic publications with diagrams |
| **Books** | Exercise Problems | Educational materials with solutions |
| **Math** | Attention Diagram | Technical diagrams with mathematical notation |
| **Math** | Worksheet | Mathematical problem sets |
| **Newspapers** | New York Times | Multi-column news layouts |
| **Other** | Flowchart | Technical diagrams and process flows |

## 💻 Implementation Guide

### Installation

```bash
pip install chandra-ocr
```

### Direct Code Integration

```python
from chandra.model import InferenceManager from chandra.model.schema import BatchInputItem

# Run chandra_vllm to start a vLLM server first if you pass vllm, else pass hf
# you can also start your own vllm server with the datalab-to/chandra model
manager = InferenceManager(method="vllm")

batch = [ BatchInputItem(
        image=PIL_IMAGE, prompt_type="ocr_layout"
    ) ]

result = manager.generate(batch)[0] print(result.markdown)
```

### Using Transformers Library

```python
from transformers import AutoModel, AutoProcessor from chandra.model.hf import generate_hf
from chandra.model.schema import BatchInputItem from chandra.output import parse_markdown

model = AutoModel.from_pretrained("datalab-to/chandra").cuda()
model.processor = AutoProcessor.from_pretrained("datalab-to/chandra")

batch = [ BatchInputItem(
        image=PIL_IMAGE, prompt_type="ocr_layout"
    ) ]

result = generate_hf(batch, model)[0] markdown = parse_markdown(result.raw)
```

## 🙌 Credits

*Originally posted at: https://huggingface.co/datalab-to/chandra*

Special thanks to the following open source projects that made Chandra possible:

- **Huggingface Transformers** - Core model infrastructure
- **VLLM** - High-performance inference engine
- **olmocr** - Benchmark evaluation framework
- **Qwen 3 VL** - Foundation model architecture

## ✅ Final Thoughts

Chandra represents a significant advancement in OCR technology, delivering exceptional accuracy
across diverse document types while preserving critical layout information. With its **83.1%
overall performance** leading the benchmark charts, support for 40+ languages, and flexible
output formats, Chandra is positioned as the go-to solution for modern document processing needs.

The model's strength in handling complex layouts, mathematical expressions, and handwritten
content makes it particularly valuable for enterprise applications, academic research, and
document digitization projects. The availability of both free playground access and hosted API
services ensures accessibility for projects of all scales.

--- 
*#OCR #MACHINELEARNING #DOCUMENTPROCESSING #AI #HUGGINGFACE #VLLM #TEXTEXTRACTION
#LAYOUTPRESERVATION*

