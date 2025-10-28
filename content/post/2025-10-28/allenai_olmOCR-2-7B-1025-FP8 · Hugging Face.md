---
title: "olmOCR-2-7B-1025-FP8: Advanced OCR with Vision Language Models"
description: "A quantized FP8 version of the powerful olmOCR model optimized for enhanced OCR
performance with exceptional handling of mathematical equations, tables, and complex document
recognition scenarios."
date: 2025-10-28T01:48:03.164402+05:30
tags: ["OCR", "Computer Vision", "Vision Language Models", "Document Processing", "AI", "Machine Learning", "Qwen2.5-VL", "FP8 Quantization", "VLLM", "PDF Processing"]
categories: ["Artificial Intelligence", "Computer Vision", "Document Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/6734d6722769638944a5aa2e/DPsr3ZvRF9v-gdMa4EaHW.png"
math: false
license: "Apache 2.0"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🧠 olmOCR-2-7B-1025-FP8: Advanced OCR with Vision Language Models

![olmOCR Logo](https://cdn-uploads.huggingface.co/production/uploads/6734d6722769638944a5aa2e/DPsr3ZvRF9v-gdMa4EaHW.png)

*The next generation of document recognition powered by AI*

## 🚀 Introduction

Meet **olmOCR-2-7B-1025-FP8**, a quantized FP8 version of the powerful olmOCR-2-7B-1025 model,
optimized using llmcompressor for enhanced performance and efficiency. This cutting-edge model
represents a significant leap forward in optical character recognition (OCR) technology,
fine-tuned from Qwen2.5-VL-7B-Instruct using the comprehensive olmOCR-mix-1025 dataset.

What sets this model apart is its additional fine-tuning using GRPO RL training, which
dramatically boosts its performance when handling complex mathematical equations, intricate
tables, and other challenging OCR scenarios that typically stump traditional recognition systems.

## 📊 olmOCR-Bench Scores

The model demonstrates exceptional performance across various document types when evaluated on
olmOCR-bench using the olmOCR toolkit, which intelligently renders, rotates, and retries pages as needed:

| **Model** | ArXiv | Old Scans Math | Tables | Old Scans | Headers and Footers | Multi column |
 Long tiny text | Base | Overall |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| olmOCR pipeline v0.4.0 with olmOCR-2-7B-1025 | 82.9 | 82.1 | 84.3 | 48.3 | 95.7 | 84.3 | 81.4
| 99.7 | 82.3 ± 1.1 |
| olmOCR pipeline v0.4.0 with olmOCR-2-7B-1025-FP8 | 83.0 | 82.3 | 84.9 | 47.7 | 96.1 | 83.7 |
81.9 | 99.7 | 82.4 ± 1.1 |

The FP8 quantized version maintains virtually identical performance while offering significant
efficiency improvements, making it ideal for production deployments.

## ⚙️ Usage

### 🎯 Optimal Implementation

The most effective way to leverage this model is through the **olmOCR toolkit**, which provides:

- ⚡ Efficient inference setup via VLLM
- 📈 Scalability to handle millions of documents
- 🔄 Automatic rendering, rotation, and retry mechanisms

### 📐 Input Requirements

The model expects input in a specific format:
- **Single document image** rendered with the longest dimension at **1288 pixels**
- **Structured prompts** containing document metadata (easily generated via olmOCR toolkit)

## 🛠️ Manual Promptin

For developers who prefer direct model interaction without the toolkit, here's a comprehensive implementation example:

### Prerequisites

```bash
pip install olmocr>=0.4.0
```

### Complete Code Implementation

```python
import torch import base64
import urllib.request from io import BytesIO
from PIL import Image from transformers import AutoProcessor, Qwen2_5_VLForConditionalGeneration
from olmocr.data.renderpdf import render_pdf_to_base64png from olmocr.prompts import build_no_anchoring_v4_yaml_prompt

# Initialize the model
model = Qwen2_5_VLForConditionalGeneration.from_pretrained("allenai/olmOCR-2-7B-1025",
torch_dtype=torch.bfloat16).eval() processor = AutoProcessor.from_pretrained("Qwen/Qwen2.5-VL-7B-Instruct")
device = torch.device("cuda" if torch.cuda.is_available() else "cpu") model.to(device)

# Grab a sample PDF
urllib.request.urlretrieve("https://olmocr.allenai.org/papers/olmocr.pdf", "./paper.pdf")

# Render page 1 to an image
image_base64 = render_pdf_to_base64png("./paper.pdf", 1, target_longest_image_dim=1288)

# Build the full prompt
messages = [ {
        "role": "user", "content": [
            {"type": "text", "text": build_no_anchoring_v4_yaml_prompt()}, {"type": "image_url", "image_url": {"url":
f"data:image/png;base64,{image_base64}"}}, ],
    } ]

# Apply the chat template and processor
text = processor.apply_chat_template(messages, tokenize=False, add_generation_prompt=True)
main_image = Image.open(BytesIO(base64.b64decode(image_base64))) inputs = processor(
    text=[text], images=[main_image],
    padding=True, return_tensors="pt",
) inputs = {key: value.to(device) for (key, value) in inputs.items()}

# Generate the output
output = model.generate( **inputs,
    temperature=0.1, max_new_tokens=50,
    num_return_sequences=1, do_sample=True,
)

# Decode the output
prompt_length = inputs["input_ids"].shape[1] new_tokens = output[:, prompt_length:]
text_output = processor.tokenizer.batch_decode( new_tokens, skip_special_tokens=True
)

print(text_output)
# Output example:
# ['---\nprimary_language: en\nis_rotation_valid: True\nrotation_correction: 0\nis_table:
False\nis_diagram: False\n---\nolmOCR: Unlocking Trillions of Tokens in PDFs with Vision Language Models\n\nJake Poz']
```

## 📋 Model Specifications

### Technical Details
- **Model Size**: 8B parameters
- **Tensor Types**: BF16, F8_E4M3
- **Base Model**: Qwen/Qwen2.5-VL-7B-Instruct
- **License**: Apache 2.0
- **Downloads**: 6,155+ last month

### Quick Links
- 📃 [Research Paper](https://olmocr.allenai.org/papers/olmocr.pdf)
- 🤗 [SFT Dataset](https://huggingface.co/datasets/allenai/olmOCR-mix-1025)
- 🤗 [RL Dataset](https://huggingface.co/datasets/allenai/olmOCR-rl-1025)
- 🛠️ [Source Code](https://github.com/allenai/olmOCR- 🎮 [Interactive Demo](https://olmocr.allenai.org)

## 📄 License and Usage

This model operates under the **Apache 2.0 license** and is designed for research and
educational applications in accordance with Ai2's Responsible Use Guidelines. The model ensures
ethical AI deployment while maintaining high performance standards.

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/allenai/olmOCR-2-7B-1025-FP8*

## 🏁 Conclusion

The olmOCR-2-7B-1025-FP8 model represents a significant advancement in document recognition
technology, offering enterprise-grade OCR capabilities with exceptional performance across
diverse document types. Its quantized FP8 format delivers the perfect balance of accuracy and
efficiency, making it ideal for large-scale production deployments.

Key takeaways include its superior handling of mathematical equations and complex tables,
seamless integration through the olmOCR toolkit, and maintained performance despite
quantization. Whether you're processing academic papers, financial documents, or technical
manuals, this model provides the reliability and accuracy needed for professional OCR applications.

For organizations looking to modernize their document processing workflows, olmOCR-2-7B-1025-FP8
 offers a compelling solution that combines cutting-edge AI with practical deployment considerations.

*#OCR #COMPUTERVISION #DOCUMENTPROCESSING #ARTIFICIALINTELLIGENCE #MACHINELEARNING #HUGGINGFACE
#QWEN #VISIONLANGUAGEMODELS*

