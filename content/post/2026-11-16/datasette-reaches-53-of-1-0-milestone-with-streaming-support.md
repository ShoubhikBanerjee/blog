---
title: "Datasette Reaches 53% of 1.0 Milestone with Streaming Support and View Transitions"
slug: "datasette-reaches-53-of-1-0-milestone-with-streaming-support-and-view-transitions"
description: "Development on Datasette using Claude Fable 5.2 has brought the 1.0 milestone to 53% completion. The latest release introduces streaming support for output renderers, several interface updates,..."
date: 2026-11-16T16:01:27+05:30
tags: [Datasette, OpenSource, WebDevelopment, SoftwareUpdates]
categories: ["AI", "Software Development", "Web Development", "Data Tools"]
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Reaches 53% of 1.0 Milestone with Streaming Support and View Transitions

Development on Datasette using Claude Fable 5.2 has brought the 1.0 milestone to 53% completion. The latest release introduces streaming support for output renderers, several interface updates, security patches, and CSS multi-page view transitions.

## 🔍 Overview

The update includes dozens of smaller improvements alongside dozens of bug fixes. Contributions to the bug fixes were made by Zihan Dai, Peter Olkhovets, Ilya Khalafi, and Ankita Advitot.

## ⚙️ Key details

* **Streaming support:** Built-in TSV and CSV export mechanisms now utilize streaming support. Plugins can also register to stream every row in a table in one go via the new `Response.stream()` method.
* **CSS multi-page view transitions:** Navigations within Datasette—which remains a multi-page application—feel more like a single-page application (SPA).
* **Row page JSON:** The row page JSON representation has received a design suitable for 1.0.
* **Column JSON formatting:** JSON data in columns on the row page can now be pretty-printed.
* **Web Components & JS utilities:** A new `<datasette-copy-button>` Web Component provides copy-schema functionality in various places, and a new `DatasetteModal.confirm()` JavaScript utility method has been added.

## 🔒 Security fixes

A security fix was issued with a GitHub advisory regarding private stored queries. The vulnerability could expose the title and SQL of private stored queries, though it did not allow those queries to be executed.

## 🚀 Availability

CSS multi-page view transitions currently work on Chrome and Safari. Support for Firefox is expected to arrive in Firefox 162 on December 8th, 2026, as the feature is no longer feature-flagged in Firefox Nightly.

#Datasette #OpenSource #WebDevelopment #SoftwareUpdates

---

*Source: [Release: datasette 1.0a43](https://simonwillison.net/2026/Nov/15/datasette/)*
