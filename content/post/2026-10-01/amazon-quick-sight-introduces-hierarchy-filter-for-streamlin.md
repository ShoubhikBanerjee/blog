---
title: "Amazon Quick Sight Introduces Hierarchy Filter for Streamlined Dashboards"
slug: "amazon-quick-sight-introduces-hierarchy-filter-for-streamlined-dashboards"
description: "Amazon Quick Sight is a fully managed, cloud-native business intelligence (BI) capability for building and publishing interactive dashboards."
date: 2026-10-01T22:03:23+05:30
tags: [AmazonQuickSight, BI, DataVisualization, Filters]
categories: ["AI", "Business Intelligence", "Data Analytics", "Cloud Computing"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21595-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon Quick Sight Introduces Hierarchy Filter for Streamlined Dashboards

Amazon Quick Sight is a fully managed, cloud-native business intelligence (BI) capability for building and publishing interactive dashboards.

Today, we’re announcing the hierarchy filter in Quick Sight.

## 🔍 Overview
- "With it, authors can offer rich, multi-level filtering in a single compact control, reducing clutter and guiding readers to the data they need in fewer steps."
- "Reduces visual clutter: Instead of showing hundreds of cities upfront, readers see a short list of Regions first."
- "Fewer steps and more guided exploration: Readers drill down a logical path (Region → Sub-Region → Country → City) rather than scanning a flat list of dozens of filters."

## 🧩 How it works
- "In the Filters pane, choose Add and select the field to filter on (for example, Region)."
- "Choose the filter to open Edit filter, open the Filter type menu, and under ADVANCED FILTER choose Hierarchy filter."
- "Quick Sight describes it as “Organize and present filter values in a hierarchical tree control.”"
- "A hierarchy filter is a single filter that holds several related fields: up to five levels (for example, Region → Subregion → Country → City → Town)."
- "The fields don’t need to be geographic. Any parent‑child dimensions work, such as Product Category → Product."
- "Under FIELD HIERARCHY, choose Add field to add Region, Country, and City."
- "Arrange the fields from broadest to most detailed: Region, then Country, then City. Use each field’s move up and move down control to reorder them. The order sets the reader’s drill‑down path."

## ⚙️ Key details
- "Mix‑and‑match hierarchy selection: Readers can combine levels of the hierarchy in one filter control, selecting an entire country such as Japan alongside a single city such as New York."
- "Scales without overwhelming: You can support deep hierarchies (up to five levels) without adding five independent filter controls that crowd the toolbar. One compact control handles the full drill path."
- "Prevents reader confusion: Readers don’t need to know which country belongs to which Region. The hierarchy encodes that knowledge for them, making the dashboard self‑guiding."

### Existing filter landscape
| Filter Count | Types |
|--------------|-------|
| 6 | Four geographical filters (Region, Sub‑Region, Country, City) and two more that cover the Segment and Product dimensions |

## 🚀 Getting started
- "You need author access to create and manage analyses and dashboards."
- "For this walkthrough we use a retail sales dataset with a three‑level geographic hierarchy plus a couple of metrics."
- "The dataset covers three Regions (EMEA, AMER, APAC), eight countries, and fourteen cities, so the cascade has enough depth to be meaningful."
- "We will build a single‑sheet dashboard so the reader can see the whole cascade at a glance."

## 💡 Why it matters
- Reduces visual clutter.
- Shortens the number of steps to reach target data.
- Allows flexible, mixed‑level selections.
- Enables deep hierarchies without crowding the UI.
- Provides self‑guiding navigation for readers.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21595-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21595-2.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/09/29/ML-21595-3.png)

#AmazonQuickSight #BI #DataVisualization #Filters

---

*Source: [Simplify dashboard drill-down with the Amazon Quick Sight hierarchy filter | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/simplify-dashboard-drill-down-with-the-amazon-quick-sight-hierarchy-filter/)*
