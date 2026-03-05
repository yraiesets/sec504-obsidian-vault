<%*
const book_number = await tp.system.prompt("Book number (1-6)");
const page = await tp.system.prompt("Page(s)");
const category = await tp.system.suggester(
  ["Reconnaissance", "Scanning & Enumeration", "Exploitation", "Password Attacks", "Post-Exploitation", "Network Defense", "Incident Response", "Forensics", "Web Application", "Malware"],
  ["reconnaissance", "scanning", "exploitation", "password-attacks", "post-exploitation", "network-defense", "incident-response", "forensics", "web-application", "malware"]
);
const confidence = await tp.system.suggester(["🔴 low", "🟡 medium", "🟢 high"], ["low", "medium", "high"]);
const mitre_raw = await tp.system.prompt("MITRE ATT&CK Technique (e.g. T1059.001) — leave blank to skip", "");
const mitre = mitre_raw ? mitre_raw.trim() : "";
_%>
---
tags:
  - sec504
  - book/<% book_number %>
  - <% category %>
aliases: []
book: "<% book_number %>"
page: "<% page %>"
category: "<% category %>"
confidence: <% confidence %>
mitre: "<% mitre %>"
date_created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>

## Quick Reference

| | |
|---|---|
| **Book** | <% book_number %> |
| **Page(s)** | <% page %> |
| **Category** | <% category %> |
| **MITRE ATT&CK** | <% mitre ? mitre : "—" %> |
| **Key Command** | `` |

## Summary

> One-sentence explanation in plain language.

## How It Works


### Key Commands

```bash
# Primary command

```

### Important Flags / Options

| Flag | Description |
|------|-------------|
| `-` | |
| `-` | |

## Attack vs. Defense

| Perspective | Notes |
|-------------|-------|
| **Offensive use** | |
| **Detection / Mitigation** | |

## Exam Tips

- ⚠️ Common pitfall:
- 💡 Key insight:

## Related Concepts

- [[]]
- [[]]

## Lab Reference

- **Lab:** Book <% book_number %>, Lab X.X
- **Page:**
- **Notes:**
