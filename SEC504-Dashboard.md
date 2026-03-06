---
tags:
  - sec504
  - MOC
  - dashboard
---

# 🎯 SEC504 — GCIH Study Dashboard

> SANS Hacker Tools, Techniques, and Incident Handling
> GIAC Certified Incident Handler (GCIH)

---

## 📚 Course Books

| Book          | Topic | Status                                    | Notes |
| ------------- | ----- | ----------------------------------------- | ----- |
| [[Section-1]] |       | `$= dv.page("Section-1")?.status ?? "🔴"` |       |
| [[Section-2]] |       | `$= dv.page("Section-2")?.status ?? "🔴"` |       |
| [[Section-3]] |       | `$= dv.page("Section-3")?.status ?? "🔴"` |       |
| [[Section-4]] |       | `$= dv.page("Section-4")?.status ?? "🔴"` |       |
| [[Section-5]] |       | `$= dv.page("Section-5")?.status ?? "🔴"` |       |
| [[Section-6]] |       | `$= dv.page("Section-6")?.status ?? "🔴"` |       |

---

## 🗂️ Quick Links

- [[SEC504-Master-Index]] — Complete index (print for exam)
- [[SEC504-Exam-Strategy]] — Exam strategy & time management

---

## 🛠️ Cheatsheets

| Tool | Category | Confidence |
|------|----------|------------|
| [[Nmap-Cheatsheet]] | Scanning | |
| [[Metasploit-Cheatsheet]] | Exploitation | |
| [[Netcat-Cheatsheet]] | Networking | |
| [[Wireshark-Cheatsheet]] | Analysis | |
| [[PowerShell-Attack-Cheatsheet]] | Post-Exploitation | |
| [[Tcpdump-Cheatsheet]] | Analysis | |

> Add more cheatsheets as you progress through the material.

---

## 📊 Study Tracker

### Weekly Goals

| Week | Focus | Done |
|------|-------|------|
| 1 | | [ ] |
| 2 | | [ ] |
| 3 | | [ ] |
| 4 | | [ ] |
| 5 | | [ ] |
| 6 | | [ ] |

### Practice Exams

| Attempt | Date | Score | Weak Areas |
|---------|------|-------|------------|
| 1 | | /100 | |
| 2 | | /100 | |

---

## 🔥 Weak Spots to Review

> Notes with `confidence: low` — review these first.

```dataview
TABLE book AS "Book", page AS "Page", category AS "Category"
FROM #sec504
WHERE confidence = "low"
SORT book ASC
```

---

## 📈 Progress Overview

```dataview
TABLE length(rows) AS "Count"
FROM #sec504
WHERE confidence
GROUP BY confidence
```

