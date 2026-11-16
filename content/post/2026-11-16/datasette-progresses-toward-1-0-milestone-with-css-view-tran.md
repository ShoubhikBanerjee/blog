---
title: "Datasette Progresses Toward 1.0 Milestone with CSS View Transitions and Streaming Support"
slug: "datasette-progresses-toward-1-0-milestone-with-css-view-transitions-and-streaming-support"
description: "On November 15, 2026, developers shared updates on the progress of the Datasette 1.0 milestone, which is now 53% complete. The latest release includes significant architectural changes, security..."
date: 2026-11-16T12:08:13+05:30
tags: [Datasette, OpenSource, WebDevelopment]
categories: ["AI", "Software Development", "Data Management", "Web Standards"]
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Progresses Toward 1.0 Milestone with CSS View Transitions and Streaming Support

On November 15, 2026, developers shared updates on the progress of the Datasette 1.0 milestone, which is now 53% complete. The latest release includes significant architectural changes, security patches, and user interface enhancements developed with assistance from Claude Fable 5.2.

## ⚙️ Key details

The release introduces several functional improvements to the platform's core data handling and display capabilities:

*   **Streaming Support:** Output renderers, including built-in TSV and CSV export mechanisms, now utilize streaming. 
*   **Plugin API:** A new `Response.stream()` method allows plugins to register as capable of streaming every row in a table in a single operation.
*   **JSON Redesign:** The row page JSON representation has been redesigned for the 1.0 standard, and JSON data within columns can now be pretty-printed.
*   **UI Components:** A new `<datasette-copy-button>` Web Component has been added to provide copy-schema functionality in various locations.

## 🧩 How it works

A major feature in this release is the implementation of CSS multi-page view transitions, which allow the multi-page application to behave more like a single-page application (SPA). 

| Component | Mechanism |
| :--- | :--- |
| `.facet-results` | Morphs from old position to new position during transition. |
| `.table-wrapper` | Morphs position if it contains `.rows-and-columns`. |
| `DatasetteModal.confirm()` | A new JavaScript utility method for handling confirmations. |

These transitions are enabled for users who do not have "prefers-reduced-motion" active. This functionality currently works in Safari and Chrome.

## 🛡️ Security and Improvements

This update addresses dozens of bugs and includes a specific security fix regarding private stored queries. A GitHub advisory was issued because private stored queries could previously be exposed, revealing the title and SQL of the query, though they could not be executed by unauthorized parties.

General bug fixes were supported by several contributors, including:
*   Zihan Dai
*   Peter Olkhovets
*   Ilya Khalafi
*   Ankita Advitot

## 🚀 Availability

While currently available for Safari and Chrome users, Firefox support for the new CSS view transitions is expected to arrive on December 8th, 2026, with the release of Firefox 162. These features are no longer feature-flagged in Firefox Nightly.

#Datasette #OpenSource #WebDevelopment

---

*Source: [Release: datasette 1.0a43](https://simonwillison.net/2026/Nov/15/datasette/)*
