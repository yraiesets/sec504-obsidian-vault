---
status: 🔴 Not Started
---
<%*
const book_number = await tp.system.prompt("Book number (1-6)");
_%>
---
tags:
  - sec504
  - book/<% book_number %>
  - notes
date_created: <% tp.date.now("YYYY-MM-DD") %>
status: "🔴 Not Started"
---

# 📘 SEC504 — Book <% book_number %> Notes

```dataviewjs
const file = app.vault.getAbstractFileByPath(dv.current().file.path);
const content = await app.vault.read(file);

const eobrPart = content.split('## End-of-Book Review')[1] || '';
const sectionPart = (content.split('## Section Notes')[1] || '').split('## End-of-Book Review')[0];

const eobrDone = /^- .+\S/m.test(eobrPart);
const hasNotes = sectionPart.split('**Key Takeaways:**').slice(1)
  .some(p => /\S/.test(p.split('**Key Vocabulary')[0].trim()));
const hasLabNotes = sectionPart.split('**Lab Notes:**').slice(1)
  .some(p => /\S/.test(p.split('---')[0].trim()));

const newStatus = eobrDone ? '🟢 Complete' : (hasNotes || hasLabNotes) ? '🟡 In Progress' : '🔴 Not Started';
if (dv.current().status !== newStatus) {
  await app.fileManager.processFrontMatter(file, fm => { fm.status = newStatus; });
}
```

## Book Overview

|              |                          |
| ------------ | ------------------------ |
| **Title**    |                          |
| **Sections** |                          |
| **Pages**    |                          |
| **Status**   | `$= dv.current().status` |

---

## Section Notes

### Section X.X — Title

**Pages:** X–X

**Key Takeaways:**


**Key Vocabulary:**

| Term | Definition |
|------|-----------|
| | |

**New Concepts Added to Index:**
- [[]]

**Lab Notes:**


---

## End-of-Book Review

### Concepts Understood
-

### Concepts to Revisit
-

### Questions from Practice Tests Related to This Book
-
