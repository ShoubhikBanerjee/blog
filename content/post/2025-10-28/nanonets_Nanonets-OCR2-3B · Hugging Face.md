---
title: "Nanonets-OCR2-3B: Advanced Document Intelligence & Structured Markdown Conversion"
description: "Advanced OCR model for intelligent document processing and markdown conversion with LaTeX equation recognition, image description, and multilingual support."
date: 2025-10-28T02:06:52.427737+05:30
tags: ["OCR", "Document Intelligence", "AI", "Machine Learning", "NLP", "Computer Vision", "Transformers", "Nanonets", "Markdown", "VQA"]
categories: ["AI", "Document Processing", "Computer Vision"]
image: "https://cdn-uploads.huggingface.co/production/uploads/626d198986671a29c70e688e/Vn6092flX4bQgzal2X04f.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🔍 Nanonets-OCR2-3B: Advanced Document Intelligence & Structured Markdown Conversion

![Nanonets Logo](https://cdn-uploads.huggingface.co/production/uploads/626d198986671a29c70e688e/Vn6092flX4bQgzal2X04f.png)

*Advanced OCR model for intelligent document processing and markdown conversion*

---

## 🚀 Introduction

**Nanonets-OCR2** by [Nanonets](https://nanonets.com) represents a breakthrough in document
intelligence technology. This cutting-edge family of image-to-markdown OCR models transcends
traditional text extraction, delivering structured markdown output with intelligent content
recognition and semantic tagging that's optimized for Large Language Model (LLM) processing.

**Quick Access Links:**
- [🖥️ Live Demo](https://nanonets.com/ocr-api) | [📢 Blog](https://nanonets.com/blog/) | [⌨️
GitHub](https://github.com/nanonets) | [📖 Cookbooks](https://nanonets.com/cookbooks)

---

## ⚙️ Key Features & Capabilities

Nanonets-OCR2 is engineered with advanced features designed to handle complex documents with unprecedented accuracy:

- **🧮 LaTeX Equation Recognition:** Automatically converts mathematical equations and formulas
into properly formatted LaTeX syntax, distinguishing between inline (`$...$`) and display (`$$...$$`) equations.

- **🖼️ Intelligent Image Description:** Describes images within documents using structured
`<img>` tags, making them digestible for LLM processing. Handles logos, charts, graphs, and
various image types with detailed content, style, and context analysis.

- **✍️ Signature Detection & Isolation:** Identifies and isolates signatures from other text,
outputting them within `<signature>` tags - crucial for legal and business document processing.

- **🏷️ Watermark Extraction:** Detects and extracts watermark text from documents, placing it
within `<watermark>` tags for clean document processing.

- **☑️ Smart Checkbox Handling:** Converts form checkboxes and radio buttons into standardized
Unicode symbols (☐, ☑, ☒) for consistent and reliable processing.

- **📊 Complex Table Extraction:** Accurately extracts complex tables from documents and
converts them into both markdown and HTML table formats.

- **📈 Flow Charts & Organizational Charts:** Extracts flow charts and organizational structures
 as [mermaid](https://mermaid.js.org/) code.

- **✏️ Handwritten Documents:** Trained on handwritten documents across multiple languages for
comprehensive text recognition.

- **🌍 Multilingual Support:** Supports English, Chinese, French, Spanish, Portuguese, German,
Italian, Russian, Japanese, Korean, Arabic, and many more languages.

- **❓ Visual Question Answering (VQA):** Provides direct answers if present in the document;
otherwise responds with "Not mentioned."

--- 
## 🏗️ Nanonets-OCR2 Famil

| Model | Access Link |
| --- | --- |
| Nanonets-OCR2-Plus | [Docstrange link](https://docstrange.com) |
| Nanonets-OCR2-3B | [🤗 link](https://huggingface.co/nanonets/Nanonets-OCR2-3B) |
| Nanonets-OCR2-1.5B-exp | [🤗 link](https://huggingface.co/nanonets/Nanonets-OCR2-1.5B-exp) |

--- 
## 💻 Usage Examples

### Using Transformers

```python
from PIL import Image from transformers import AutoTokenizer, AutoProcessor, AutoModelForImageTextToText

model_path = "nanonets/Nanonets-OCR2-3B" model = AutoModelForImageTextToText.from_pretrained(
    model_path, torch_dtype="auto",
    device_map="auto", attn_implementation="flash_attention_2"
) model.eval()

tokenizer = AutoTokenizer.from_pretrained(model_path) processor = AutoProcessor.from_pretrained(model_path)

def ocr_page_with_nanonets_s(image_path, model, processor, max_new_tokens=4096):
    prompt = """Extract the text from the above document as if you were reading it naturally.
Return the tables in html format. Return the equations in LaTeX representation. If there is an
image in the document and image caption is not present, add a small description of the image
inside the <img></img> tag; otherwise, add the image caption inside <img></img>. Watermarks
should be wrapped in brackets. Ex: <watermark>OFFICIAL COPY</watermark>. Page numbers should be
wrapped in brackets. Ex: <page_number>14</page_number> or <page_number>9/22</page_number>.
Prefer using ☐ and ☑ for check boxes."""

    image = Image.open(image_path) messages = [
        {"role": "system", "content": "You are a helpful assistant."}, {"role": "user", "content": [
            {"type": "image", "image": f"file://{image_path}"}, {"type": "text", "text": prompt},
        ]}, ]

    text = processor.apply_chat_template(messages, tokenize=False, add_generation_prompt=True)
    inputs = processor(text=[text], images=[image], padding=True, return_tensors="pt") inputs = inputs.to(model.device)

    output_ids = model.generate(**inputs, max_new_tokens=max_new_tokens, do_sample=False)
    generated_ids = [output_ids[len(input_ids):] for input_ids, output_ids in zip(inputs.input_ids, output_ids)]
    output_text = processor.batch_decode(generated_ids, skip_special_tokens=True, clean_up_tokenization_spaces=True)

    return output_text[0]

# Usage
image_path = "/path/to/your/document.jpg"
result = ocr_page_with_nanonets_s(image_path, model, processor, max_new_tokens=15000) print(result)
```

### Using vLLM

1. **Start the vLLM server:**

```bash
vllm serve nanonets/Nanonets-OCR2-3B
```

2. **Predict with the model:**

```python
from openai import OpenAI import base64

client = OpenAI(api_key="123", base_url="http://localhost:8000/v1")model = "nanonets/Nanonets-OCR2-3B"

def encode_image(image_path):
    with open(image_path, "rb") as image_file:
        return base64.b64encode(image_file.read()).decode("utf-8")

def ocr_page_with_nanonets_s(img_base64):
    response = client.chat.completions.create( model=model,
        messages=[ {
                "role": "user", "content": [
                    { "type": "image_url",
                        "image_url": {"url": f"data:image/png;base64,{img_base64}"}, },
                    { "type": "text",
                        "text": "Extract the text from the above document as if you were reading
 it naturally. Return the tables in html format. Return the equations in LaTeX representation.
If there is an image in the document and image caption is not present, add a small description
of the image inside the <img></img> tag; otherwise, add the image caption inside <img></img>.
Watermarks should be wrapped in brackets. Ex: <watermark>OFFICIAL COPY</watermark>. Page numbers
 should be wrapped in brackets. Ex: <page_number>14</page_number> or
<page_number>9/22</page_number>. Prefer using ☐ and ☑ for check boxes.", },
                ], }
        ], temperature=0.0,
        max_tokens=15000 )
    return response.choices[0].message.content

test_img_path = "/path/to/your/document.jpg" img_base64 = encode_image(test_img_path)
print(ocr_page_with_nanonets_s(img_base64))
```

### Using Docstrange

```python
import requests

url = "https://extraction-api.nanonets.com/extract"headers = {"Authorization": <API KEY>}
files = {"file": open("/path/to/your/file", "rb")} data = {"output_type": "markdown"}
data["model"] = "nanonets"

response = requests.post(url, headers=headers, files=files, data=data) print(response.json())
```

Check out [Docstrange](https://docstrange.com) for more details.

--- 
## 📊 Performance Evaluation

### Markdown Evaluations

#### Nanonets OCR2 Plus Performance

| Model | Win Rate vs Nanonets OCR2 Plus (%) | Lose Rate vs Nanonets OCR2 Plus (%) | Both
Correct (%) |
| --- | --- | --- | --- |
| **Gemini 2.5 flash (No Thinking)** | 34.35 | 57.60 | 8.06 |
| **Nanonets OCR2 3B** | 29.37 | 54.58 | 16.04 |
| **Nanonets-OCR-s** | 24.86 | 66.12 | 9.02 |
| **Nanonets OCR2 1.5B exp** | 13.00 | 81.20 | 5.79 |
| **GPT-5 (Thinking: low)** | 23.53 | 74.86 | 1.60 |

#### Nanonets OCR2 3B Performance

| Model | Win Rate vs Nanonets OCR2 3B (%) | Lose Rate vs Nanonets OCR2 3B (%) | Both Correct
(%) |
| --- | --- | --- | --- |
| **Gemini 2.5 flash (No Thinking)** | 39.98 | 52.43 | 7.58 |
| **Nanonets-OCR-s** | 30.61 | 58.28 | 11.12 |
| **Nanonets OCR2 1.5B exp** | 14.78 | 79.18 | 6.04 |
| **GPT-5** | 25.00 | 72.87 | 2.13 |

### Visual Question Answering (VQA) Evaluations

| Dataset | Nanonets OCR2 Plus | Nanonets OCR2 3B | Qwen2.5-VL-72B-Instruct | Gemini 2.5 Flash |
| --- | --- | --- | --- | --- |
| ChartQA (IDP-Leaderboard) | 79.20 | 78.56 | 76.20 | 84.82 |
| DocVQA (IDP-Leaderboard) | 85.15 | 89.43 | 84.00 | 85.51 |

--- 
## 🎯 Tips to Improve Accuracy

1. **Higher Resolution Images:** Increasing image resolution significantly improves model performance.

2. **Complex Tables (Financial Documents):** Use `repetition_penalty=1` for better results with financial documents:

```python
user_prompt = """Extract the text from the above document as if you were reading it naturally.
Return the tables in HTML format. Return the equations in LaTeX representation. If there is an
image in the document and image caption is not present, add a small description of the image
inside the <img></img> tag; otherwise, add the image caption inside <img></img>. Watermarks
should be wrapped in brackets. Ex: <watermark>OFFICIAL COPY</watermark>. Page numbers should be
wrapped in brackets. Ex: <page_number>14</page_number> or <page_number>9/22</page_number>.
Prefer using ☐ and ☑ for check boxes. Only return HTML table within <table></table>."""
```

3. **Docstrange Financial Option:** Use the `Markdown (Financial Docs)` option for table-heavy financial documents:

```python
import requests

url = "https://extraction-api.nanonets.com/extract"headers = {"Authorization": <API KEY>}
files = {"file": open("/path/to/your/file", "rb")} data = {"output_type": "markdown-financial-docs"}

response = requests.post(url, headers=headers, files=files, data=data) print(response.json())
```

4. **Document-Specific Optimization:** Check the [cookbooks](https://nanonets.com/cookbooks) for
 resolution recommendations specific to different document types.

--- 
## 📚 BibTeX Citation

```bibtex
@misc{Nanonets-OCR2, title={Nanonets-OCR2: A model for transforming documents into structured markdown with
intelligent content recognition and semantic tagging},
    author={Souvik Mandal and Ashish Talewar and Siddhant Thakuria and Paras Ahuja and Prathamesh Juvatkar},
    year={2025}, }
```

--- 
## 🙌 Credits

*Originally posted at: https://huggingface.co/nanonets/Nanonets-OCR2-3B*

--- 
## 🏁 Conclusion

Nanonets-OCR2-3B represents a significant advancement in document intelligence technology,
offering unprecedented capabilities in converting complex documents into structured, LLM-ready
markdown format. With its comprehensive feature set including LaTeX equation recognition,
intelligent image description, signature detection, and multilingual support, it stands as a
powerful solution for modern document processing workflows.

The model's strong performance across various benchmarks, particularly in DocVQA tasks where it
achieves 89.43% accuracy, demonstrates its practical value for real-world applications. Whether
processing financial documents, academic papers, or multilingual content, Nanonets-OCR2-3B
provides the accuracy and intelligence needed for advanced document understanding.

For organizations looking to enhance their document processing capabilities with
state-of-the-art AI technology, Nanonets-OCR2-3B offers a compelling solution that bridges the
gap between raw document content and structured, actionable data.

--- 
*#OCR #DOCUMENTINTELLIGENCE #AI #MACHINELEARNING #NLP #COMPUTERVISION #TRANSFORMERS #NANONETS
#MARKDOWN #VQA*

