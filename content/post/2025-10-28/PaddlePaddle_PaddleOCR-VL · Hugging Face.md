---
title: "PaddleOCR-VL: Ultra-Compact Vision-Language Model for Multilingual Document Parsing"
description: "A breakthrough 0.9B parameter vision-language model delivering state-of-the-art
document parsing performance across 109 languages with exceptional efficiency and comprehensive
element recognition capabilities."
date: 2025-10-28T00:43:50.598602+05:30
tags: ["PaddleOCR", "Vision-Language Model", "Document Parsing", "OCR", "Multilingual", "ERNIE", "Computer Vision", "NLP", "Table Recognition", "Formula Recognition"]
categories: ["Artificial Intelligence", "Computer Vision", "Natural Language Processing"]
image: "https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/allmetric.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🚀 PaddleOCR-VL: Ultra-Compact Vision-Language Model for Multilingual Document Parsing

![PaddleOCR-VL Performance](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/allmetric.png)

*Comprehensive performance metrics showcasing PaddleOCR-VL's state-of-the-art capabilities
across various document parsing tasks*

## 📖 Introduction

**PaddleOCR-VL** represents a breakthrough in document parsing technology, delivering
state-of-the-art performance through an ultra-compact 0.9B parameter vision-language model
(VLM). This innovative solution integrates a NaViT-style dynamic resolution visual encoder with
the ERNIE-4.5-0.3B language model, enabling accurate recognition of complex document elements
while maintaining minimal resource consumption.

The model demonstrates exceptional capabilities in handling diverse document types across **109
languages**, making it ideal for real-world deployment scenarios where efficiency and accuracy are paramount.

## ⭐ Core Features

### 🏗️ **Compact yet Powerful VLM Architecture*

The model features a novel vision-language architecture specifically designed for
resource-efficient inference. By combining:
- **NaViT-style dynamic high-resolution visual encoder** for superior image processing
- **Lightweight ERNIE-4.5-0.3B language model** for efficient text generation
- **Optimized inference pipeline** that reduces computational demands while maintaining high
accuracy

![Model Architecture](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/paddleocrvl.png)

*PaddleOCR-VL's innovative architecture combining visual and language components*

### 📊 **SOTA Performance on Document Parsing**

PaddleOCR-VL achieves state-of-the-art results across multiple benchmarks:
- **Page-level document parsing** with comprehensive layout understanding
- **Element-level recognition** for text, tables, formulas, and charts
- **Superior performance** compared to existing pipeline-based solutions
- **Strong competitiveness** against leading vision-language models

### 🌍 **Comprehensive Multilingual Support**

Supporting **109 languages** including:
- **Major global languages**: Chinese, English, Japanese, Korean, Latin
- **Diverse script systems**: Russian (Cyrillic), Arabic, Hindi (Devanagari), Thai
- **Specialized content**: Handwritten text and historical documents

## 📰 News

- `2025.10.16` 🚀 **Official Release** of PaddleOCR-VL — multilingual document parsing with SOTA
 performance in an ultra-compact 0.9B model

## 🛠️ Usag

### 📦 Install Dependencies

First, install the required PaddlePaddle and PaddleOCR components:

```bash
python -m pip install paddlepaddle-gpu==3.2.0 -i https://www.paddlepaddle.org.cn/packages/stable/cu126/
python -m pip install -U "paddleocr[doc-parser]"
python -m pip install https://paddle-whl.bj.bcebos.com/nightly/cu126/safetensors/safetensors-0.6.2.dev0-cp38-abi3-linux_x86_64.whl
```

> **Note**: Windows users should use WSL or Docker container for optimal compatibility.

### 💻 Basic Usage

**CLI Interface:**
```bash
paddleocr doc_parser -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/paddleocr_vl_demo.png
```

**Python API:**
```python
from paddleocr import PaddleOCRVL

pipeline = PaddleOCRVL()
output = pipeline.predict("https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/paddleocr_vl_demo.png")

for res in output:
    res.print() res.save_to_json(save_path="output")
    res.save_to_markdown(save_path="output")
```

### ⚡ Accelerated Inference with Optimized Servers

**1. Start VLM Inference Server:**
```bash
docker run \ --rm \
  --gpus all \ --network host \
  ccr-2vdh3abv-pub.cnc.bj.baidubce.com/paddlepaddle/paddlex-genai-vllm-server
```

**2. Use Accelerated Backend:**
```bash
paddleocr doc_parser \ -i https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/paddleocr_vl_demo.png \
  --vl_rec_backend vllm-server \ --vl_rec_server_url http://127.0.0.1:8080/v1
```

```python
from paddleocr import PaddleOCRVL

pipeline = PaddleOCRVL( vl_rec_backend="vllm-server",
    vl_rec_server_url="http://127.0.0.1:8080/v1")
output = pipeline.predict("https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/paddleocr_vl_demo.png")

for res in output:
    res.print() res.save_to_json(save_path="output")
    res.save_to_markdown(save_path="output")
```

## 📈 Performance Benchmarks

### 📄 Page-Level Document Parsing

#### **OmniDocBench v1.5 Results**

PaddleOCR-VL achieves state-of-the-art performance across all key metrics:

![OmniDocBench v1.5](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/omni15.png)

*SOTA performance on text, formula, tables, and reading order recognition*

#### **OmniDocBench v1.0 Results**

![OmniDocBench v1.0](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/omni10.png)

*Comprehensive benchmark results showing superior performance across multiple document types*

### 🔤 Element-Level Recognition Performance

#### **Text Recognition**

**OmniDocBench-OCR-block Performance:**
![OCR Block Performance](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/omnibenchocr.png)

**Multilingual OCR Performance:**
![In-house OCR](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/inhouseocr.png)

*Outstanding accuracy with lowest edit distances across multiple languages and scripts*

#### **Table Recognition**
![Table Performance](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/inhousetable.png)

*Exceptional performance across diverse table formats including bordered, borderless, and
complex layouts*

#### **Formula Recognition**
![Formula Performance](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/inhouse-formula.png)

*Superior performance on printed, scanned, and handwritten mathematical formulas*

#### **Chart Recognition**
![Chart Performance](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/inhousechart.png)

*Leading performance across 11 chart categories, outperforming even 72B-level models*

## 🎨 Visualization Examples

### 📋 Comprehensive Document Parsing

![Document Parsing Example 1](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/overview1.jpg)
![Document Parsing Example 2](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/overview2.jpg)

*Examples showcasing comprehensive document understanding and parsing capabilities*

### 📝 Text Recognition Examples

![English and Arabic Text](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/text_english_arabic.jpg) ![Handwritten Text](https://huggingface.co/datasets/PaddleP
addle/PaddleOCR-VL_demo/resolve/main/imgs/text_handwriting_02.jpg)

*Multilingual text recognition including handwritten content*

### 📊 Table Processing Examples

![Table Example 1](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/table_01.jpg) ![Table Example 2](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_d
emo/resolve/main/imgs/table_02.jpg)

*Complex table structures with various formatting styles*

### 📐 Formula Recognition Examples

![English Formula](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/formula_EN.jpg) ![Chinese Formula](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL
_demo/resolve/main/imgs/formula_ZH.jpg)

*Mathematical formulas in different languages and complexity levels*

### 📈 Chart Analysis Examples

![Chart Example 1](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_demo/resolve/main/imgs/chart_01.jpg) ![Chart Example 2](https://huggingface.co/datasets/PaddlePaddle/PaddleOCR-VL_d
emo/resolve/main/imgs/chart_02.jpg)

*Various chart types including bar charts, pie charts, and complex visualizations*

## 🙏 Acknowledgments

Special thanks to the following projects and teams for their valuable contributions:
- **[ERNIE](https://github.com/PaddlePaddle/ERNIE)** - Foundation language model
- **[Keye](https://github.com/PaddlePaddle/PaddleOCR)** - OCR framework
- **[MinerU](https://github.com/opendatalab/MinerU)** - Document processing tools
- **[OmniDocBench](https://github.com/opendatalab/OmniDocBench)** - Comprehensive benchmarking

We appreciate everyone's contribution to this open-source project! 🎉

## 📚 Citation

If you find PaddleOCR-VL helpful in your research or projects, please consider citing:

```bibtex
@misc{cui2025paddleocrvlboostingmultilingualdocument,
    title={PaddleOCR-VL: Boosting Multilingual Document Parsing via a 0.9B Ultra-Compact Vision-Language Model},
    author={Cheng Cui and Ting Sun and Suyin Liang and Tingquan Gao and Zelun Zhang and Jiaxuan
Liu and Xueqing Wang and Changda Zhou and Hongen Liu and Manhui Lin and Yue Zhang and Yubo Zhang
 and Handong Zheng and Jing Zhang and Jun Zhang and Yi Liu and Dianhai Yu and Yanjun Ma}, year={2025},
    eprint={2510.14528}, archivePrefix={arXiv},
    primaryClass={cs.CV}, url={https://arxiv.org/abs/2510.14528},
}
```

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/PaddlePaddle/PaddleOCR-VL*

## 🏁 Conclusion

PaddleOCR-VL represents a significant advancement in document parsing technology, combining
exceptional performance with remarkable efficiency. Its ultra-compact 0.9B parameter
architecture delivers state-of-the-art results across 109 languages while maintaining fast
inference speeds suitable for real-world deployment.

Key takeaways include:
- **Revolutionary efficiency** with SOTA performance in a compact model
- **Comprehensive multilingual support** covering diverse scripts and languages
- **Versatile element recognition** for text, tables, formulas, and charts
- **Production-ready deployment** with optimized inference servers
- **Open-source accessibility** enabling widespread adoption and innovation

This breakthrough makes advanced document parsing capabilities accessible to a broader range of
applications and organizations, democratizing AI-powered document understanding technology.

*#PADDLEOCR #VLM #DOCUMENTPARSING #OCR #AI #MULTILINGUAL #ERNIE #COMPUTERVISION #NLP*

