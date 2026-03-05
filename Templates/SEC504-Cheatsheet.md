<%*
const book_number = await tp.system.prompt("Book number(s)");
const page = await tp.system.prompt("Page(s)");
const platform = await tp.system.suggester(
  ["Windows", "Linux", "Cross-platform", "Network Device"],
  ["windows", "linux", "cross-platform", "network-device"]
);
_%>
---
tags:
  - sec504
  - cheatsheet
  - <% tp.file.title %>
aliases: []
book: "<% book_number %>"
page: "<% page %>"
platform: "<% platform %>"
date_created: <% tp.date.now("YYYY-MM-DD") %>
---

# 🛠️ <% tp.file.title %> — Cheatsheet

> **Book(s):** <% book_number %> | **Page(s):** <% page %> | **Platform:** <% platform %>

---

## What is it?

> One-liner description.

## When to Use

> Scenario or context in which this tool is relevant during the exam.

## Installation / Availability

```bash
# How to install or where it's available by default

```

## Essential Commands

### Basic Usage

```bash
# Description
command
```

### Common Scenarios

```bash
# Scenario 1 —

# Scenario 2 —

# Scenario 3 —
```

## Flags Quick Reference

| Flag | Description | Example |
|------|-------------|---------|
| | | |

## Exam-Relevant Combos

```bash
# The combo SANS is most likely to test

```

## Common Output & What to Look For

```
# Example of important output

```

## Related Tools

- [[]]
- [[]]

## Defensive Perspective

> How to detect or counter this tool (SEC504 tests both sides).
