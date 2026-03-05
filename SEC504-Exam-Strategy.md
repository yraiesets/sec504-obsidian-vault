---
tags:
  - sec504
  - exam
  - strategy
---

# 🎯 SEC504 — GCIH Exam Strategy

> GIAC Certified Incident Handler (GCIH)
> Open-book, proctored online exam.

---

## Exam Format

| | |
|---|---|
| **Questions** | 106 |
| **Duration** | 4 hours |
| **Passing score** | 71% (75 / 106) |
| **Format** | Multiple choice |
| **Resources allowed** | Physical books and printed notes only — no electronics |

---

## Before the Exam

### Index
- Print `SEC504-Master-Index.md` — this is the primary lookup tool during the exam
- Sort the alphabetical index A–Z
- Verify that all `confidence: low` concepts have been reviewed

### Books
- Tab each physical book with labeled Post-its at key sections
- Write the section name on each tab for fast navigation
- Mark high-frequency pages (common commands, attack steps, detection signatures)

### Mindset
- The exam tests understanding, not memorization — questions are scenario-based
- Both offensive and defensive perspectives are tested
- Incident handling process (Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned) appears throughout

---

## Time Management

| Phase | Time | Target |
|-------|------|--------|
| First pass (all questions) | ~2h 30m | Answer or flag every question |
| Review flagged questions | ~1h | Revisit uncertain answers |
| Final check | ~30m | Verify answers, don't second-guess |

**Rule of thumb:** ~2 minutes per question on the first pass. If a question requires more than 2 minutes of book lookup, flag it and move on.

---

## During the Exam

### Workflow per question
1. Read the question fully before looking anything up
2. Eliminate obviously wrong answers first
3. If unsure → Ctrl+F on the printed index → Book + Page → look it up
4. If still unsure → flag and move on, do not stall

### Common question patterns
- **Tool identification** — "Which tool is used to..." → Cheatsheets
- **Attack steps** — "What is the next step after..." → Concepts notes
- **Detection** — "Which log entry indicates..." → Defensive perspective sections
- **Incident response** — "What phase of IR addresses..." → Know the IR lifecycle cold
- **Output interpretation** — "What does this output mean..." → Common Output sections in cheatsheets

---

## High-Priority Topics

These areas have historically high question density in the GCIH:

| Topic | Why It Matters |
|-------|---------------|
| Incident Response lifecycle | Foundational — appears in many question contexts |
| Nmap scan types | Frequently tested with output interpretation |
| Metasploit workflow | Exploitation + post-exploitation steps |
| Password attack techniques | Hashcat, John, pass-the-hash, Mimikatz |
| Netcat usage | Bind shell vs reverse shell, pivoting |
| Web application attacks | SQLi, XSS, command injection |
| Windows persistence mechanisms | Registry, scheduled tasks, services |
| Network traffic analysis | Wireshark / tcpdump output reading |
| Buffer overflow concepts | Stack layout, NOP sled, shellcode |

---

## IR Lifecycle — Quick Reference

| Phase | Key Actions |
|-------|------------|
| **Preparation** | Policies, tools, training in place |
| **Identification** | Detect and confirm incident |
| **Containment** | Limit damage — short-term and long-term |
| **Eradication** | Remove root cause (malware, backdoors) |
| **Recovery** | Restore systems, monitor for recurrence |
| **Lessons Learned** | Post-incident review, improve defenses |

---

## Notes
