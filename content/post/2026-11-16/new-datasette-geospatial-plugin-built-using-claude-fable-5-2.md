---
title: "New Datasette Geospatial Plugin Built Using Claude Fable 5.2"
slug: "new-datasette-geospatial-plugin-built-using-claude-fable-5-2"
description: "On 15th November 2026, a new Datasette geospatial plugin was created using Claude Fable 5.2. The plugin combines the MapLibre GL library with OpenFreeMap, a free vector map server operated by Zsolt..."
date: 2026-11-16T16:01:27+05:30
tags: [Datasette, Claude, OpenFreeMap, MapLibre, WebAssembly]
categories: ["AI", "Artificial Intelligence", "Data Visualization", "Geospatial Development", "Open Source"]
image: "https://static.simonwillison.net/static/cors-allow/2026/datasette-maplibre.webp"
author: "Shoubhik Banerjee"
draft: false
---

# New Datasette Geospatial Plugin Built Using Claude Fable 5.2

On 15th November 2026, a new Datasette geospatial plugin was created using Claude Fable 5.2. The plugin combines the MapLibre GL library with OpenFreeMap, a free vector map server operated by Zsolt Ero.

## 🧩 Development and Features

Most of the plugin was created with a single prompt instructing Claude Fable 5.2 to combine features from `datasette-cluster-map` and `datasette-leaflet-geojson` alongside a local demo file, while thinking outside the box for additional useful features.

Key features and capabilities include:
- Combines the MapLibre GL library with the OpenFreeMap vector map server.
- Displays SVG previews of GeoJSON shapes, loading a WebGL preview only when they scroll into view.
- Displays both GeoJSON shapes and latitude/longitude points on the same map.

## 🚀 Availability

A comprehensive demo was built to work in the latest Datasette Lite, allowing the plugin and a demo database to load directly in a browser via Pyodide and WebAssembly.

#Datasette #Claude #OpenFreeMap #MapLibre #WebAssembly

---

*Source: [Release: datasette-maplibre 0.1a0](https://simonwillison.net/2026/Nov/15/datasette-maplibre/)*
