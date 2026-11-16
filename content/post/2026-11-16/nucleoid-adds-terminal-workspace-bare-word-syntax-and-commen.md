---
title: "Nucleoid adds terminal workspace, bare-word syntax, and comment updates"
slug: "nucleoid-adds-terminal-workspace-bare-word-syntax-and-comment-updates"
description: "Nucleoid has updated its developer experience and language syntax with a new full-screen terminal workspace, support for bare-word assignments, and changes to how comments and conditional logic are..."
date: 2026-11-16T22:14:27+05:30
tags: [Nucleoid, LogicProgramming, CLI, KnowledgeGraph, Rust]
categories: ["AI", "Programming Languages", "Developer Tools", "Knowledge Graphs", "Command Line Interface"]
image: "https://avatars.githubusercontent.com/u/87045767?v=4"
author: "Shoubhik Banerjee"
draft: false
---

# Nucleoid adds terminal workspace, bare-word syntax, and comment updates

Nucleoid has updated its developer experience and language syntax with a new full-screen terminal workspace, support for bare-word assignments, and changes to how comments and conditional logic are handled.

## 🔍 Overview
Nucleoid is a next-generation logic programming language built on structured objects and their relationships, extending the traditional Knowledge Graph. It uses a minimum-token syntax for logic representation and a declarative execution model, eliminating the need for LLMs to manually manage control flow, state propagation, and other imperative constructs.

## 🧩 How it works
The new interactive interface offers a top-level tab layout, with two tabs reserved for future views. A multiline editor sits at the bottom, featuring autocomplete for keywords, built-ins, and model properties, plus in-session input and result history. Results can be inspected in Text, JSON, or Table formats without re-running the program; arrays of objects render as table rows, while other JSON values display in property/value or index/value views.

Key input behaviors include:
- **Enter** inserts a newline.
- **F5** runs the entire editor content.
- **Ctrl-J** inserts an automatically indented newline.
- **Tab** accepts autocomplete or indents.
- **Ctrl-Space** opens suggestions.
- **Ctrl-P / Ctrl-N** recalls input while preserving an unfinished draft.
- **F1-F3** switch tabs, **F6** changes the result view, and **Ctrl-Up / Ctrl-Down** select earlier results.
- **Mouse** clicks select tabs, views, and results; click/drag edits the cursor/selection, and the wheel scrolls individual panes.
- **Ctrl-C** cancels input, **Ctrl-Q** exits, and **.help** lists all controls.

## ⚙️ Key details
- **Assignment Syntax**: Assignments can be written as `target is value`. Quotes are optional around a single word. For example, `a is 5` and `o.x is "good"` are valid. If the value is a bare word that does not match a defined variable, class, function, or built-in, it stores its own text.
- **Conditional Branches**: In conditionals like `a is A if c else B`, a bare word in a branch is read as a variable, class, function, or built-in if it exists; otherwise, it reads as its own text. Parenthesized operands are not treated as words, so `a is (A if c else B)` requires `A` and `B` to be defined.
- **List and Dictionary Items**: Inside `is` values, list items, dictionary values, or named arguments can also be bare words.
- **Comments**: Hash (`#`), double-slash (`//`), and non-nesting block comments (`/* ... */`) all work in files and interactive interfaces. Comments take delimiter priority outside literals, meaning `//` is a comment, not an empty regex (use `/(?:)/` for an empty-matching regex). Comments retain newlines and source positions and cannot join tokens or supply indentation. Unclosed block comments report `SyntaxError: Unterminated block comment at its opening slash`.
- **Plain Mode**: Running `nucleoid --plain` provides a line-oriented interface. Piped stdin or redirected stdout automatically selects this mode. Body lines are prefilled with indentation after the `..` prompt, and blank lines submit the block.

## 🚀 Availability
Install the CLI from crates.io using the command: `cargo install nucleoid`. The standard `nucleoid` command opens the full-screen terminal workspace from any directory. File execution and the `--json` and `--graph` flags retain their existing behavior. References NUC 76, NUC 93, and NUC 94 document the removal of the `--c-style-comments`, `--is-assignment`, and `--conditional-words` flags, respectively.

#Nucleoid #LogicProgramming #CLI #KnowledgeGraph #Rust

---

*Source: [NucleoidAI/Nucleoid](https://github.com/NucleoidAI/Nucleoid)*
