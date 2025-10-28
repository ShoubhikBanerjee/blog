---
title: "LFM2-VL-3B: Liquid AI's Advanced Multimodal Vision-Language Model"
description: "Comprehensive overview of Liquid AI's flagship 3B parameter multimodal model that
efficiently processes text and images with enhanced visual understanding and reasoning
capabilities."
date: 2025-10-28T01:51:47.035270+05:30
tags: ["Liquid AI", "LFM2-VL", "Multimodal AI", "Vision-Language Model", "Computer Vision", "NLP", "Transformers", "Machine Learning", "Artificial Intelligence", "Edge Computing"]
categories: ["Artificial Intelligence", "Computer Vision", "Machine Learning"]
image: "https://cdn-uploads.huggingface.co/production/uploads/61b8e2ba285851687028d395/7_6D7rWrLxp2hb6OHSV1p.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🧠 LFM2-VL-3B: Liquid AI's Advanced Multimodal Vision-Language Model

![Liquid AI](https://cdn-uploads.huggingface.co/production/uploads/61b8e2ba285851687028d395/7_6D7rWrLxp2hb6OHSV1p.png)

*Liquid AI's flagship multimodal model for efficient image and text processing*

---

## 🚀 Introduction

**LFM2-VL-3B** represents the newest and most capable model in Liquid AI's multimodal
**LFM2-VL** series, engineered to process both text and images with variable resolutions
seamlessly. Built on the robust LFM2 backbone, this model extends its architecture for enhanced
reasoning capabilities and superior visual understanding while maintaining operational
efficiency.

The release of the 3B checkpoint offers significantly higher performance across industry
benchmarks while remaining optimized for scalable deployment scenarios. This makes it an ideal
solution for organizations seeking powerful multimodal AI capabilities without the overhead of
larger, resource-intensive models.

## ✨ Key Features

- **🏆 Competitive multimodal performance** among lightweight open models
- **👁️ Enhanced visual understanding and reasoning**, particularly excelling in fine-grained
perception tasks
- **⚡ Retains efficient inference** with the same flexible architecture and user-tunable
speed-quality tradeoffs
- **📐 Processes native resolutions up to 512×512** with intelligent patch-based handling for
larger inputs

## 📄 Model Details

Due to their compact size, **we recommend fine-tuning LFM2-VL models on narrow use cases** to
maximize performance. These models were specifically trained for instruction following and
lightweight agentic workflows, though they are not intended for safety-critical decisions.

### Model Specifications

| Property | **LFM2-VL-450M** | **LFM2-VL-1.6B** | **LFM2-VL-3B** |
|----------|------------------|-------------------|-----------------|
| **Parameters (LM only)** | 350M | 1.2B | 2.6B |
| **Vision encoder** | SigLIP2 NaFlex base (86M) | SigLIP2 NaFlex shape-optimized (400M) |
SigLIP2 NaFlex large (400M) |
| **Backbone layers** | hybrid conv+attention | hybrid conv+attention | hybrid conv+attention |
| **Context (text)** | 32,768 tokens | 32,768 tokens | 32,768 tokens |
| **Image tokens** | dynamic, user-tunable | dynamic, user-tunable | dynamic, user-tunable |
| **Vocab size** | 65,536 | 65,536 | 65,536 |
| **Precision** | bfloat16 | bfloat16 | bfloat16 |
| **License** | LFM Open License v1.0 | LFM Open License v1.0 | LFM Open License v1.0 |

### 🌐 Language Support
**Supported languages:** English

### ⚙️ Generation Parameters
We recommend the following optimized parameters:

- **Text:** `temperature=0.1`, `min_p=0.15`, `repetition_penalty=1.05`
- **Vision:** `min_image_tokens=64`, `max_image_tokens=256`, `do_image_splitting=True`

### 💬 Chat Template
LFM2-VL uses a ChatML-like chat template structure:

```
<|startoftext|><|im_start|>system
You are a helpful multimodal assistant by Liquid AI.<|im_end|>
<|im_start|>user
<image>Describe this image.<|im_end|>
<|im_start|>assistant
This image shows a Caenorhabditis elegans (C. elegans) nematode.<|im_end|>
```

Images are referenced with a sentinel (`<image>`), which is automatically replaced with the
image tokens by the processor. You can apply it using the dedicated `.apply_chat_template()`
function from Hugging Face transformers.

## 🏗️ Architectur

The LFM2-VL-3B model features a sophisticated hybrid architecture designed for optimal
performance:

- **🔗 Hybrid backbone:** Language model tower (LFM2-2.6B) paired with SigLIP2 NaFlex vision
encoders (400M shape-optimized)
- **📱 Native resolution processing:** Handles images up to 512×512 pixels without upscaling and
 preserves non-standard aspect ratios without distortion
- **🧩 Tiling strategy:** Splits large images into non-overlapping 512×512 patches and includes
thumbnail encoding for global context
- **⚡ Efficient token mapping:** 2-layer MLP connector with pixel unshuffle reduces image
tokens (e.g., 256×384 image → 96 tokens, 1000×3000 → 1,020 tokens)
- **🎛️ Inference-time flexibility:** User-tunable maximum image tokens and patch count for
speed/quality tradeoff without retraining

## 🎯 Training Approach

The model follows a comprehensive training methodology:

- Builds on the LFM2 base model with joint mid-training that fuses vision and language
capabilities using a gradually adjusted text-to-image ratio
- Applies joint SFT with emphasis on image understanding and vision tasks
- Leverages large-scale open-source datasets combined with in-house synthetic vision data,
selected for balanced task coverage
- Follows a progressive training strategy: base model → joint mid-training → supervised
fine-tuning

## 🏃 How to Run LFM2-VL

You can run LFM2-VL with Hugging Face `transformers` by installing Transformers from source:

```bash
pip install
git+https://github.com/huggingface/transformers.git@87be5595081364ef99393feeaa60d71db3652679
pillow
```

Here's a complete example of how to generate an answer with transformers in Python:

```python
from transformers import AutoProcessor, AutoModelForImageTextToText
from transformers.image_utils import load_image

# Load model and processor
model_id = "LiquidAI/LFM2-VL-3B"
model = AutoModelForImageTextToText.from_pretrained(
    model_id, device_map="auto", dtype="bfloat16"
)
processor = AutoProcessor.from_pretrained(model_id)

# Load image and create conversation
url = "https://www.ilankelman.org/stopsigns/australia.jpg"
image = load_image(url)
conversation = [
    {
        "role": "user",
        "content": [
            {"type": "image", "image": image},
            {"type": "text", "text": "What is in this image?"},
        ],
    },
]

# Generate Answer
inputs = processor.apply_chat_template(
    conversation,
    add_generation_prompt=True,
    return_tensors="pt",
    return_dict=True,
    tokenize=True,
).to(model.device)

outputs = model.generate(**inputs, max_new_tokens=64)
processor.batch_decode(outputs, skip_special_tokens=True)[0]

# Output: This image captures a vibrant street scene in a Chinatown area.
# The focal point is a large red Chinese archway with gold and black accents,
# adorned with Chinese characters. Flanking the archway are two white stone
# lion statues, which are traditional guardians in Chinese culture.
```

You can directly run and test the model with the provided Colab notebook for hands-on
experimentation.

## 🔧 How to Fine-tune

We recommend fine-tuning LFM2-VL models on your specific use cases to maximize performance:

| Notebook | Description | Link |
|----------|-------------|------|
| SFT (TRL) | Supervised Fine-Tuning (SFT) notebook with a LoRA adapter using TRL | ![Colab
link](https://cdn-uploads.huggingface.co/production/uploads/61b8e2ba285851687028d395/vlOyMEjwHa_
b_LXysEu2E.png) |

## 📈 Performance Benchmarks

LFM2-VL-3B demonstrates exceptional performance across industry-standard benchmarks,
outperforming comparable models in its size category:

| Model | Average | MMStar | RealWorldQA | MM-IFEval | BLINK | MMBench (dev en) | OCRBench |
POPE |
|-------|---------|--------|-------------|-----------|-------|------------------|----------|----
--|
| InternVL3_5-2B | 66.50 | 57.67 | 60.78 | 47.31 | 50.97 | 78.18 | 834.00 | 87.17 |
| Qwen2.5-VL-3B | 65.42 | 56.13 | 65.23 | 38.62 | 48.97 | 80.41 | 824.00 | 86.17 |
| InternVL3-2B | 67.44 | 61.10 | 65.10 | 38.49 | 53.10 | 81.10 | 831.00 | 90.10 |
| SmolVLM2-2.2B | 56.01 | 46.00 | 57.50 | 19.42 | 42.30 | 69.24 | 725.00 | 85.10 |
| **LFM2-VL-3B** | **69.00** | **57.73** | **71.37** | **51.83** | **51.03** | **79.81** |
**822.00** | **89.01** |

*More comprehensive benchmark scores are available in the official LFM2-VL-3B post. Scores for
competitive models were obtained using VLMEvalKit.*

---

## 🙌 Credits

*Originally posted at: https://huggingface.co/LiquidAI/LFM2-VL-3B*

## 🏁 Conclusion

LFM2-VL-3B represents a significant advancement in efficient multimodal AI, delivering
state-of-the-art performance in a compact, deployment-ready package. Its hybrid architecture,
intelligent image processing capabilities, and flexible inference options make it an ideal
choice for organizations seeking powerful vision-language capabilities without the computational
 overhead of larger models.

The model's emphasis on fine-tuning for specific use cases, combined with its robust performance
 across diverse benchmarks, positions it as a versatile solution for a wide range of multimodal
applications. Whether you're building conversational AI systems, image analysis tools, or
agentic workflows, LFM2-VL-3B offers the perfect balance of capability and efficiency.

For organizations interested in custom solutions with edge deployment capabilities, Liquid AI
provides enterprise support to maximize the model's potential in production environments.

*#LIQUIDAI #MULTIMODAL #VISIONLANGUAGE #LFM2VL #MACHINELEARNING #ARTIFICIALINTELLIGENCE
#COMPUTERVISION #NLP #TRANSFORMERS #EDGECOMPUTING*

