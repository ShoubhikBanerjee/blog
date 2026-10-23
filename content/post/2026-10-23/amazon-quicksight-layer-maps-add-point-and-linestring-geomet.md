---
title: "Amazon QuickSight Layer Maps Add Point and LineString Geometry Support"
slug: "amazon-quicksight-layer-maps-add-point-and-linestring-geometry-support"
description: "Amazon QuickSight now lets layer maps display individual locations and routes by supporting Point and LineString geometry types from GeoJSON files."
date: 2026-10-23T22:04:00+05:30
tags: [AmazonQuickSight, GeospatialBI, LayerMaps, GeoJSON, DataVisualization]
categories: ["AI", "Business Intelligence", "Geospatial Analytics", "Data Visualization"]
image: "https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-21612-featured-image.png"
author: "Shoubhik Banerjee"
draft: false
---

# Amazon QuickSight Layer Maps Add Point and LineString Geometry Support

Amazon QuickSight now lets layer maps display individual locations and routes by supporting Point and LineString geometry types from GeoJSON files.

## 🔍 Overview
- Layer maps can plot points and routes, such as store locations across a city or flights leaving an airport.
- Supports multiple map types: point maps, filled maps, and layer maps.
- Geospatial maps help businesses spot location‑tied patterns, like regional performance or customer concentration.

## 🧩 How it works
- A layer map gets its shapes from a **GeoJSON** file and its metrics from a QuickSight dataset; a shared key joins the two.
- **GeoJSON requirements**: saved with a `.geojson` extension, maximum file size 100 MB, geometry types include Point, LineString, and Polygon.
- Configuration settings:
  1. **Geometry type to visualize** – selects which geometry (Points, Lines, or Polygons) from the GeoJSON file is rendered. Only one type appears at a time.
  2. **Shape‑file key ↔ dataset key** – matches a key field in the GeoJSON properties to a key field in the dataset. Field names can differ, but values must match.
- Example workflow for routes:
  - GeoJSON holds one **LineString** feature per route, keyed by `route_id`.
  - QuickSight dataset has one row per route, also keyed by `route_id`.
  - Set Geometry type to **Lines**; the visual draws each path from the ordered coordinates in the GeoJSON file.
- Example workflow for points:
  - GeoJSON holds one **Point** feature per store or facility, keyed by a store ID.
  - Dataset has one row per store.
  - Set Geometry type to **Points**.

## ⚙️ Key details
- **New geometry support**: Point (marks specific locations) and LineString (traces routes such as deliveries, flights, shipping lanes, pipelines).
- **Layer map visual behavior**:
  - Draws paths from GeoJSON coordinates rather than generating them from data at load time.
  - Join key in GeoJSON ties each LineString to the dataset row that provides tooltip and color information.
- **File format**: GeoJSON is a JSON‑based format describing geographic features; each feature’s `geometry` has a `type` (Point, LineString, Polygon) and `coordinates`.

## 💡 Why it matters
- Enables businesses to visualize not just regions (handled by polygons) but also the exact locations of assets and the routes connecting them.
- Supports use cases such as:
  - Mapping flights leaving an airport.
  - Visualizing delivery paths for logistics.
  - Showing shipping lanes or pipeline segments.
- By joining geographic shapes to dataset metrics, teams can overlay performance data on routes or locations for deeper insight.


![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-21612-1.png)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-21612-2.jpg)

![figure](https://d2908q01vomqb2.cloudfront.net/f1f836cb4ea6efb2a0b1b99f41ad8b103eff4b59/2026/10/20/ML-21612-3.png)

#AmazonQuickSight #GeospatialBI #LayerMaps #GeoJSON #DataVisualization

---

*Source: [Visualize points and routes with GeoJSON in Amazon Quick Sight layer maps | Amazon Web Services](https://aws.amazon.com/blogs/machine-learning/visualize-points-and-routes-with-geojson-in-amazon-quick-sight-layer-maps/)*
