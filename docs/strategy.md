# System strategy (internal — not a checklist)

This is the layer underneath the notes. It defines *how* the capture system runs, so behavior stays consistent across sessions. Not something you read day-to-day — reference it when a skill's behavior needs to change.

## Note format
- One idea = one file: `notes/YYYY-MM-DD-slug.md`.
- Sections, always in this order: `Idea` → `Translation` → `Next Actions` → `Links`.
- `Links` section is mandatory even if empty-looking — if the user mentions ANY URL, it goes here verbatim, with a short label. Never paraphrase a link away. This exists because links get lost is a recurring failure — don't repeat it.
- `Next Actions` is skipped only when the idea is a pure reflection with nothing to do yet.

## Master list
- Lives at `notes/master-list.md`. One row per captured idea: date, title, category, status, link to the note file.
- Never auto-add a note to the master list. After capturing and summarizing an idea, ask the user once: "add this to the master list?" Only add on yes.
- The master list is the recheck surface — it's what the user scans to see everything open, not the individual note files.

## Reply behavior
- Keep chat replies short (2-4 lines). Summarize, don't dump the file.
- Guess category and structure first; correct on feedback rather than asking upfront.
- When the user gives feedback on the system itself (not an idea), treat it as a system change: update the template/skill/strategy files, don't just apply it once by hand.
