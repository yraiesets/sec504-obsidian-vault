---

tags:
  - sec504
  - book/4
  - notes
date_created: 2026-03-06
status: "🔴 Not Started"

---

# 📘 SEC504 — Book 4 Notes

```dataviewjs
const filePath = dv.current()?.file?.path ?? app.workspace.getActiveFile()?.path;
if (!filePath || filePath.startsWith("Templates/")) return;
const file = app.vault.getAbstractFileByPath(filePath);
if (!file) return;

const updateStatus = async () => {
  const content = await app.vault.read(file);
  const EOBR = '## End-of' + '-Book Review';
  const SEC = '## Section' + ' Notes';
  const eobrPart = content.split(EOBR)[1] || '';
  const sectionPart = (content.split(SEC)[1] || '').split(EOBR)[0];
  const eobrDone = /^- .+\S/m.test(eobrPart);
  const hasNotes = sectionPart.split('**Key Takeaways:**').slice(1)
    .some(p => /\S/.test(p.split('**Key Vocabulary')[0].trim()));
  const hasLabNotes = sectionPart.split('**Lab Notes:**').slice(1)
    .some(p => /\S/.test(p.split('---')[0].trim()));
  const newStatus = eobrDone ? '🟢 Complete' : (hasNotes || hasLabNotes) ? '🟡 In Progress' : '🔴 Not Started';
  const currentStatus = app.metadataCache.getFileCache(file)?.frontmatter?.status;
  if (currentStatus !== newStatus) {
    await app.fileManager.processFrontMatter(file, fm => { fm.status = newStatus; });
  }
};

await updateStatus();
const evtRef = app.vault.on('modify', async (modified) => {
  if (modified.path === file.path) await updateStatus();
});
const observer = new MutationObserver(() => {
  if (!dv.container.isConnected) {
    app.vault.offref(evtRef);
    observer.disconnect();
  }
});
observer.observe(dv.container.parentElement ?? document.body, { childList: true });
```

## Book Overview

|              |                          |
| ------------ | ------------------------ |
| **Title**    |                          |
| **Sections** |                          |
| **Pages**    |                          |
| **Status**   | `$= dv.current()?.status` |

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
