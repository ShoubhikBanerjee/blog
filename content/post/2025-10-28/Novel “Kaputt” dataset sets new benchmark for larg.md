---
title: "Novel Kaputt Dataset Sets New Benchmark for Large-Scale Visual Defect Detection"
description: "Amazon releases groundbreaking Kaputt dataset with 238,421 images for visual
defect detection in retail logistics, revealing significant performance gaps between
manufacturing and retail environments."
date: 2025-10-28T01:30:31.924838+05:30
tags: ["Computer Vision", "Machine Learning", "AI", "Amazon", "Defect Detection", "Dataset", "Logistics", "Quality Control", "ICCV", "Visual Inspection"]
categories: ["AI", "Computer Vision", "Research"]
image: "https://assets.amazon.science/dims4/default/541b3b2/2147483647/strip/true/crop/1398x1080+255+0/resize/1200x927!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.com%2Fscience%2F32%2Fec%2F023c8352477ca878edd636144408%2Fkaputt-image01-16x9.png"
math: false
license: "NA"
hidden: false
comments: true
draft: false
author: "Shoubhik Banerjee"
---

# 🔍 Novel "Kaputt" Dataset Sets New Benchmark for Large-Scale Visual Defect Detection

![Kaputt Dataset Overview](https://assets.amazon.science/dims4/default/541b3b2/2147483647/strip/true/crop/1398x1080+255+0/resize/1200x927!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot
.s3.amazonaws.com%2Fscience%2F32%2Fec%2F023c8352477ca878edd636144408%2Fkaputt-image01-16x9.png)

*Overview of defect severities and types in the Kaputt dataset*

At Amazon, the relentless pursuit of operational excellence through cutting-edge AI and computer
 vision has led to a groundbreaking development in visual defect detection. The company has
announced the public release of **Kaputt**, a revolutionary large-scale dataset designed to
transform how we approach defect detection in retail logistics.

## 🚀 A Game-Changing Dataset

The Kaputt dataset represents a monumental leap forward in visual defect detection research.
With **238,421 high-resolution images** of **48,376 unique items**, including **29,316 defective
 instances**, this dataset is approximately **40 times larger** than current state-of-the-art
benchmark datasets. This massive scale captures the real-world complexities of detecting defects
 and damage across an extensive range of products — from minor creases to major spills and everything in between.

This groundbreaking work will be presented at the **International Conference on Computer Vision
(ICCV) 2025**, marking a significant milestone in Amazon's efforts to automate defect detection
across their logistics operations.

## ⚙️ The Challenge of Automated Defect Detection

Developing robust visual defect detection systems for retail logistics presents unprecedented
challenges that existing research hasn't fully addressed. Unlike manufacturing settings, which
typically focus on highly standardized item poses and restricted numbers of distinct items,
retail logistics must handle **millions of unique products**, most of which have been seen only a handful of times.

Current manufacturing-focused benchmarks have reached saturation, achieving near-perfect
performance with more than **99.9% AUROC** (area under the receiver-operating-characteristic
curve). However, these achievements don't translate effectively to the diverse, dynamic
environment of retail logistics where products vary dramatically in shape, size, material, and condition.

## 🧩 Dataset Structure and Real-World Applications

The Kaputt dataset's structure thoughtfully reflects real-world challenges and opportunities.
For each query image, the dataset provides **up to three reference images** showing the item in
"normal" condition (meaning more than 99% likely to be defect-free), mirroring how human
inspectors might compare items to determine defects.

![Reference Image Variability](https://assets.amazon.science/dims4/default/7c51f38/2147483647/strip/true/crop/893x
719+92+177/resize/1200x967!/quality/90/?url=http%3A%2F%2Famazon-topics-brightspot.s3.amazonaws.c
om%2Fscience%2Fd4%2F87%2Fcae2d1b346b18c45eb615888cb41%2Fkaputt-image02-1x1.png)

*Each query image is associated with reference images that may exhibit significant variability*

The dataset includes detailed annotations for **seven distinct types of defects** and their
severity levels, acknowledging the subjective nature of defect assessment. This comprehensive
categorization enables more nuanced understanding and analysis of different defect patterns.

## 📊 Understanding Model Performance

The comprehensive evaluation of multiple leading methodologies reveals both the complexity of
the task and current technological limitations. Amazon's research team tested four distinct approaches:

| Approach Type | Description | Performance |
| --- | --- | --- |
| **Zero-shot methods** | Using general-purpose vision models | ≤56.96% AUROC |
| **Few-shot approaches** | Leveraging reference images | Variable results |
| **Supervised learning** | Full dataset access | 94.27% AUROC |
| **Hybrid methods** | Combining multiple techniques | Mixed performance |

### Key Performance Insights

The results reveal striking performance gaps:

- **Supervised models** with full dataset access achieve **94.27% AUROC** on defect detection
- Performance drops dramatically to **74.4%** in realistic scenarios with limited defective
samples
- **State-of-the-art zero-shot methods** perform poorly, with none exceeding **56.96% AUROC** —
barely better than random guessing

Through qualitative analysis, researchers identified several key challenges:

- 🔍 **Subtle anomalies** are difficult for models to detect
- 🎯 **Rare defect types** present classification challenges
- 📦 **Reference-dependent defects** like missing units are poorly handled
- 🌟 **Deformable items** and items with damage-like designs cause misclassification
- 💭 **Vision-language models** can detect obvious defects but fail on subtle defects in
deformable items

These results stand in sharp contrast to the near-perfect performance achieved in manufacturing
settings, highlighting the unique challenges of retail logistics addressed by the Kaputt dataset.

## 🌍 Impact Beyond Retail Operations

The implications of improving visual defect detection extend far beyond operational efficiency.
Early detection of defective items creates a cascading positive impact:

### Environmental Benefits ♻️
- **Reduces waste** by preventing defective products from moving through the supply chain
- **Minimizes resource consumption** through early intervention
- **Supports sustainability goals** through efficient resource utilization
- **Reduces carbon emissions** by preventing unnecessary returns and reshipments

### Customer Experience Enhancement 🎯
- **Ensures customers receive orders in perfect condition**
- **Reduces returns and reshipments**
- **Improves overall customer satisfaction**
- **Builds trust through consistent quality**

### Broader Applications 🔬
The challenges addressed by this dataset extend beyond retail:

- **Vehicle damage assessment** in automotive industries
- **Infrastructure inspection** for maintenance and safety
- **Medical imaging** for diagnostic applications
- **Quality control** across various manufacturing sectors

The diversity of objects, limited data per instance, and significant pose variations make this
dataset valuable for numerous domains requiring robust visual inspection capabilities.

## 💡 Future Research Opportunities

The public availability of the Kaputt dataset opens numerous avenues for innovation:

- **Novel algorithm development** for few-shot learning scenarios
- **Advanced multi-modal approaches** combining visual and textual information
- **Improved reference-based comparison methods**
- **Domain adaptation techniques** for cross-industry applications
- **Explainable AI methods** for defect detection reasoning

---

## 🙌 Credits

*Originally posted at: https://www.amazon.science/blog/novel-kaputt-dataset-sets-new-benchmark-f
or-large-scale-visual-defect-detection*

## 🏁 Conclusion

The release of the Kaputt dataset marks a pivotal moment in visual defect detection research. By
 providing the research community with a dataset that captures real-world complexity at
unprecedented scale, Amazon is accelerating progress toward more robust, practical defect
detection systems.

The stark performance differences between manufacturing and retail environments revealed by this
 research underscore the need for specialized datasets and methodologies. As computer vision
researchers leverage this resource to develop novel approaches, we can expect significant
advances in automated quality control systems that will benefit industries far beyond retail
logistics.

The dataset is now available for download, inviting the global research community to contribute
to solving these challenging problems and developing innovative solutions that will shape the
future of automated visual inspection.

---

_#COMPUTERVISION #MACHINELEARNING #AI #AMAZON #LOGISTICS #DEFECTDETECTION #DATASET #RESEARCH
#ICCV2025 #QUALITYCONTROL_

