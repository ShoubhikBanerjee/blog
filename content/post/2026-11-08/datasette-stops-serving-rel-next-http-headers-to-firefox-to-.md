---
title: "Datasette Stops Serving Rel Next HTTP Headers to Firefox to Prevent Unnecessary Prefetching"
slug: "datasette-stops-serving-rel-next-http-headers-to-firefox-to-prevent-unnecessary-prefetching"
description: "Datasette issue #3046 proposes no longer serving `link: rel=next` HTTP headers to Firefox for HTML pages after discovery that Firefox automatically prefetches the next page of table rows."
date: 2026-11-08T22:01:08+05:30
tags: [Datasette, Firefox, HTTPHeaders, WebDevelopment, OpenSource]
categories: ["AI", "Web Development", "Software Engineering", "Open Source"]
author: "Shoubhik Banerjee"
draft: false
---

# Datasette Stops Serving Rel Next HTTP Headers to Firefox to Prevent Unnecessary Prefetching

Datasette issue #3046 proposes no longer serving `link: rel=next` HTTP headers to Firefox for HTML pages after discovery that Firefox automatically prefetches the next page of table rows.

## 🔍 Overview

When reviewing the Firefox network panel, requests to a Datasette table page were found to trigger an HTTP prefetch for the next page of rows in that table. This behavior was caused by Datasette pages serving an HTTP link header formatted as:
`link: <https://latest.datasette.io/fixtures/compound_three_primary_keys?_next=a%2Cd%2Cv>; rel="next"`

## ⚙️ Key Details

- Firefox has had an open issue regarding this HTTP prefetching behavior for 24 years.
- An early comment on that 24-year-old issue links to a 2002 blog post written by the Datasette creator complaining about the feature.
- The author had forgotten about both writing the blog post and the feature itself.

## 💡 Why It Matters

Automatic prefetching for next-page table rows creates unnecessary overhead:

- Only a tiny fraction of visitors click the 'next' link on a page.
- The browser ends up fetching unnecessary data.
- The Datasette server is forced to render an entire page that gets thrown away.

#Datasette #Firefox #HTTPHeaders #WebDevelopment #OpenSource

---

*Source: [datasette #3046: Don’t serve link: rel=next HTTP headers to Firefox for HTML pages](https://simonwillison.net/2026/Nov/7/link-rel-next/)*
