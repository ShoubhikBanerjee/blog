---
title: "Chroma v3 Released with Go iter.Seq Support"
slug: "chroma-v3-released-with-go-iter-seq-support"
description: "Chroma v3 has been released as a new alpha version, bringing significant changes to its Go implementation and module path."
date: 2026-11-17T18:10:30+05:30
tags: [Chroma, Go, Pygments, SyntaxHighlighting]
categories: ["AI", "Programming Languages", "Software Development", "Developer Tools"]
image: "https://avatars.githubusercontent.com/u/41767?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Chroma v3 Released with Go iter.Seq Support

Chroma v3 has been released as a new alpha version, bringing significant changes to its Go implementation and module path.

## 🔍 Overview

Chroma takes source code and other structured text and converts it into syntax highlighted HTML, ANSI-coloured text, and other formats. It is based heavily on Pygments and includes translators for Pygments lexers and styles.

## ⚙️ Key details

- Replaces the custom `Iterator` type with Go's built-in `iter.Seq[Token]`
- Removes the `EOF` sentinel
- Bumps the module path to `github.com/alecthomas/chroma/v3`

## 🧩 How it works

- Lexers convert source text into a stream of tokens
- Styles specify how token types are mapped to colours
- Formatters convert tokens and styles into formatted output

## 🚀 Availability

- See the v3.0.0-alpha.1 release for migration details
- Try out various languages and styles on the Chroma Playground
- An authoritative list of languages and styles can be displayed with `chroma --list`

#Chroma #Go #Pygments #SyntaxHighlighting

---

*Source: [alecthomas/chroma](https://github.com/alecthomas/chroma)*
