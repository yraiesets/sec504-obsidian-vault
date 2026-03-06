# SEC504 — GCIH Study Vault

Obsidian vault structured for SANS SEC504 (*Hacker Tools, Techniques, and Incident Handling*) exam preparation. Built around the GCIH open-book exam format: every note is designed for fast, reliable lookup during the exam.

> [!WARNING]
> **This vault is a skeleton — not a complete study guide.**
>
> Its structure, templates, topic categories, and exam strategy notes are based on independent research about the SEC504 course and the GCIH exam. They have not been validated against the actual course material.
>
> Anyone using this vault should expect to adapt it significantly: sections may be missing, category names may not match the course's terminology, and the exam strategy notes may not reflect the current version of the exam.
>
> **Treat everything here as a starting point, not a source of truth.**

---

## Table of Contents

- [SEC504 — GCIH Study Vault](#sec504--gcih-study-vault)
  - [Table of Contents](#table-of-contents)
  - [Requirements](#requirements)
  - [Vault Structure](#vault-structure)
  - [Installation](#installation)
  - [Templates Overview](#templates-overview)
    - [SEC504-Concept](#sec504-concept)
    - [SEC504-Cheatsheet](#sec504-cheatsheet)
    - [SEC504-Book-Notes](#sec504-book-notes)
  - [Naming Conventions](#naming-conventions)
  - [Study Workflow](#study-workflow)
    - [During Reading](#during-reading)
    - [Before the Exam](#before-the-exam)
    - [During the Exam](#during-the-exam)
  - [Confidence System](#confidence-system)
  - [Best Practices](#best-practices)

---

## Requirements

| Plugin | Purpose | Status |
|--------|---------|--------|
| [Templater](https://github.com/SilentVoid13/Templater) | Dynamic templates with prompts and dropdowns | **Required** |
| [Dataview](https://github.com/blacksmithgu/obsidian-dataview) | Live queries in the Dashboard (weak spots, progress tracking) | Recommended |

---

## Vault Structure

```
sec504-obsidian-vault\
├── SEC504-Dashboard.md          ← Entry point & study tracker
├── SEC504-Master-Index.md       ← Master index (print for exam)
├── SEC504-Exam-Strategy.md      ← Exam format, time management & high-priority topics
├── Templates/                   ← Templater templates (do not edit note titles)
│   ├── SEC504-Concept.md        ← One note per concept or attack technique
│   ├── SEC504-Cheatsheet.md     ← One note per tool
│   └── SEC504-Book-Notes.md     ← Section-by-section notes per course book
├── Books/                       ← Book-level notes
├── Concepts/                    ← Individual concept notes
└── Cheatsheets/                 ← Tool cheatsheets
```

---

## Installation

1. Open the cloned `sec504-obsidian-vault` folder directly as your Obsidian vault *(recommended — preserves git tracking)*, or copy its contents into an existing vault
2. Install **Templater**: Settings → Community Plugins → Browse → search "Templater" → Install → Enable
3. Configure Templater: Settings → Templater → Template folder location → `Templates`
4. *(HIGHLY Recommended)* Install **Dataview** the same way for live queries in the Dashboard
5. Configure Dataview : Settings → Dataview → Toggle `Enable Javascript queries` & `Enable inline Javascript queries` (needed to execute DataviewJS queries)
6. Open `SEC504-Dashboard.md` as the study entry point

> **Important:** Always use *Templater: Open Insert Template Modal* when creating notes from templates — not the built-in Core Templates plugin. The `<% %>` syntax will not execute with the Core plugin.

---

## Templates Overview

### SEC504-Concept
For individual attack techniques, defensive concepts, or tools encountered during reading.

On insertion, Templater prompts for:
- **Book number** — which SEC504 book (1–6)
- **Page(s)** — page reference used during the exam
- **Category** — dropdown (Reconnaissance, Exploitation, Password Attacks, etc.)
- **Confidence** — dropdown (🔴 low / 🟡 medium / 🟢 high)
- **MITRE ATT&CK Technique** — optional (e.g. `T1059.001`), leave blank to skip

The note title is used automatically as the concept name via `tp.file.title`.

### SEC504-Cheatsheet
For full tool references (Nmap, Metasploit, Wireshark, Netcat, etc.).

Prompts for book number, pages, and target platform. The tool name is derived from the filename.

### SEC504-Book-Notes
For section-by-section notes on each course book.

Prompts for book number only.

---

## Naming Conventions

| Note Type | Convention | Example |
|-----------|-----------|---------|
| Concept | `Train-Case-Name.md` | `ARP-Poisoning.md` |
| Cheatsheet | `Tool-Cheatsheet.md` | `Nmap-Cheatsheet.md` |
| Book notes | `SEC504-Book-N.md` | `SEC504-Book-3.md` |

---

## Study Workflow

### During Reading

1. Open or create the Book Notes file for the current book using the `SEC504-Book-Notes` template
2. For each important concept:
   - Create a new note using the `SEC504-Concept` template
   - Fill in the summary and key commands in plain language
   - Add an entry to `SEC504-Master-Index.md`
3. For each tool encountered:
   - Create a note using the `SEC504-Cheatsheet` template

### Before the Exam

1. Open `SEC504-Master-Index.md`
2. Sort the alphabetical index A–Z
3. Review all entries with `confidence: low`
4. Print the Master Index
5. Tab physical books with Post-its at key pages

### During the Exam

- Use the printed Master Index for quick lookup
- Ctrl+F on a concept → find Book + Page → open the physical book at that page

---

## Confidence System

The `confidence` frontmatter field powers Dataview filtering in the Dashboard:

| Value | Meaning |
|-------|---------|
| `low` | Not yet understood — high priority for review |
| `medium` | Understood but not fully internalized |
| `high` | Confident — can explain and apply without reference |

The *Weak Spots* section in the Dashboard automatically surfaces all `confidence: low` notes.

---

## Best Practices

- **Fill the index progressively** — adding entries during reading reinforces retention better than reviewing completed notes afterward
- **Write summaries in plain language** — rewriting concepts forces comprehension; avoid copy-pasting from slides
- **Use the Graph View** — tags like `#book/3` and `#exploitation` reveal connections across concepts
- **MITRE ATT&CK references** — linking techniques to ATT&CK IDs helps contextualize attacks within the broader threat landscape and is useful for the incident handling portion of the exam
- **Dataview queries** in the Dashboard automatically surface weak spots and provide a progress overview across all notes
