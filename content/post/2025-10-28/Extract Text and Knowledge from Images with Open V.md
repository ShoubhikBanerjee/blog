---
title: "Extract Text and Knowledge from Images with Open Vision Language Model"
description: "Learn how to leverage vision language models and AI Sheets for efficient OCR and text extraction from handwritten documents, receipts, and visual content."
date: 2025-10-28T01:31:53.153797+05:30
tags: ["Vision Language Models", "OCR", "AI", "Hugging Face", "Text Extraction", "Computer Vision", "AI Sheets", "Document Digitization", "Machine Learning", "Image Processing"]
categories: ["AI/ML", "Computer Vision", "Document Processing"]
image: "https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/OZSQLc_GeINsLWnL-3t49.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🖼️ Extract Text and Knowledge from Images with Open Vision Language Model

![Folder with images](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/OZSQLc_GeINsLWnL-3t49.png)

*A collection of images ready for text extraction using AI*

Vision language models have revolutionized how we extract and process text from images, making
them invaluable tools for digitizing handwritten documents, receipts, and other visual content.
This comprehensive tutorial demonstrates how to leverage these powerful models using AI Sheets
for efficient OCR and text processing workflows.

## 📂 Upload Your Images

Start your text extraction journey with a folder containing images with text content. These could include:

- Handwritten recipes
- Business documents
- Receipts and invoices
- Historical manuscripts
- Any visual content containing text

![Upload interface](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/s8FkH6gw2LG9F7rM2mJ0D.png)

*Simple drag-and-drop interface for uploading images to AI Sheets*

Once uploaded, your images appear in an intuitive spreadsheet format, making batch processing
straightforward and organized.

![Table view](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/4lW1LWM31dB_stOP0QvL1.png)

*Images displayed in organized spreadsheet format for easy management*

## ⚙️ Apply AI Actions to Your Columns

Each column in your dataset can be enhanced with specialized AI operations. Simply click the
overlay on any column to access available processing options:

![AI action menu](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/O1XHmf70blGY6kRMOcvMi.png)

*Comprehensive AI action menu for different column types*

### Available AI Operations:

**Image Columns:**
- Text extraction (OCR)
- Visual question answering
- Object detection
- Custom AI actions

**Text Columns:**
- Content summarization
- Keyword extraction
- Multi-language translation

## 🔍 Extract Text Using OCR

AI Sheets provides pre-built templates for efficient text extraction:

![Extract text interface](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/gTXMKRJ8J0Oil7YUZUnOr.png)

*Built-in OCR template for immediate text extraction*

### Example: Handwritten Recipe Processing

Consider this handwritten recipe example:

![Handwritten recipe](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/7IuC9cTT5v-fXHvI9NB9D.webp)

*Sample handwritten recipe demonstrating OCR capabilities*

**Default extraction captures all visible text:**

```
MEMORANDUM: From To 1 Box Duncan Hines Yellow Cake Mix 1 Box instant lemon pudding 2/3 cups
water 1/2 cup Mozola oil 4 eggs Lemon flavoring to taste. Put in mixing bowl and beat for 10
min. and REMEMBER... for Quality PRINTING CALL OR WRITE Gatling & Pierce PRINTERS TELEPHONE
332-2579 22 YEARS OF SERVICE IN NORTHEASTERN CAROLINA
```

### Custom Prompt Optimization

For cleaner, more focused results, implement custom prompts:

![Custom prompt interface](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/oYanFJWYR6zejEgq2TFYc.png)

*Custom prompt configuration for targeted text extraction*

**Refined output focusing on recipe content:**

```
- 1 box Duncan Hines Yellow Cake Mix
- 1 box instant lemon pudding
- 2/3 cups water
- 1/2 cup Mazola oil
- 4 eggs
- Lemon flavoring to taste
- Put in mixing bowl and beat for 10 minutes
```

## 🤖 Compare Vision Language Models for OCR Accuracy

The default `Qwen/Qwen2.5-VL-7B-Instruct` model handles most OCR tasks effectively. For
challenging handwriting or complex documents, consider upgrading to more powerful models like
`Qwen/Qwen3-VL-235B-A22B-Reasoning`:

![Qwen3 model selection](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/pA3vr1tw8VtmgS9Q6pskF.png)

*Advanced model selection for improved accuracy*

### Model Performance Comparison

| Qwen/Qwen2.5-VL-7B-Instruct | Qwen/Qwen3-VL-235B-A22B-Reasoning |
|------------------------------|-----------------------------------|
| in large bowl combine meat, onion, bread crumbs 1/2 nutmeg & cheese - as you add sprinkle
around. Then blend - Last sprinkle blend again Bake in large pan for 10-15 min. at 350. Let
stand 5 min before serving. | in lg bowl combine meat, onion, bread crumbs 1/4 nutmeg & cheese -
 as you add sprinkle around. then blend - last **spinach** blend again. Bake in lg pan for
**50-60 min. @ 350** - let stand 5 min before serving |

💡 **Key Insight:** The larger model successfully identifies critical details like "spinach" and
 corrects the cooking time from "10-15 min" to the accurate "50-60 min."

## 📝 Process Extracted Text

Transform raw extracted text into structured, usable formats:

![Text formatting options](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/lB4Z_iEKIUnuaSTPqc_xZ.png)

*Text processing options for structured output*

This generates clean, formatted HTML for each processed recipe:

![HTML output](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/zSCnY3D6uobqSCHj7tBqR.png)

*Well-structured HTML output ready for web publishing*

## 🎨 Transform Images

Apply sophisticated image-to-image models for visual enhancements. Convert images to black and
white for improved OCR accuracy:

![Transform to black and white](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/Blf4wtKrX6UYkQ06HUV-8.png)

*Image transformation interface for visual preprocessing*

**Transformation result:**

![Black and white result](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/cMzCQUMMRKch__C3W_-Ve.png)

*Enhanced black and white image optimized for text extraction*

## 📤 Export Your Dataset

Seamlessly export your processed dataset to Hugging Face Hub for sharing and collaboration:

![Export interface](https://cdn-uploads.huggingface.co/production/uploads/60420dccc15e823a685f2b03/2fSKxUzwZtPkPJ-ZWEYYl.png)

*Direct export to Hugging Face Hub for dataset sharing*

The complete processed dataset is publicly available at
[aisheets/unlocked-recipes](https://huggingface.co/datasets/aisheets/unlocked-recipes).

## 📚 Resources

**Get Started:**
- Try [AI Sheets](https://aisheets.com) directly in your browser
- Deploy locally from the [GitHub repository](https://github.com/aisheets/aisheets)
- Ask questions in the Community tab
- [Open GitHub issues](https://github.com/aisheets/aisheets/issues) for technical support

## 🙌 Credits

*Originally posted at: https://huggingface.co/blog/dvilasuero/how-to-analyze-images-with-ai*

## 🏁 Conclusion

Vision language models represent a significant leap forward in automated text extraction and
document digitization. Through AI Sheets, these powerful capabilities become accessible without
requiring deep technical expertise. The ability to compare different models, apply custom
prompts, and export results directly to collaborative platforms like Hugging Face Hub creates a
comprehensive workflow for transforming visual content into structured, actionable data.

Whether you're digitizing historical documents, processing business receipts, or extracting
knowledge from handwritten notes, this approach offers scalable solutions that adapt to varying
complexity levels and accuracy requirements.

--- 
_#VISIONLANGUAGEMODELS #OCR #AIML #HUGGINGFACE #TEXTEXTRACTION #COMPUTERVISION #AISHEETS
#DOCUMENTDIGITIZATION_

