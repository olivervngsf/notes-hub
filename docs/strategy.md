# System strategy (internal — not a checklist)

This is the layer underneath the notes. It defines *how* the capture system runs, so behavior stays consistent across sessions. Not something you read day-to-day — reference it when a skill's behavior needs to change.

## Note format
- One idea = one file: `notes/YYYY-MM-DD-slug.md`.
- Frontmatter: `date`, `category`, `priority` (high/medium/low), `tags` (freeform list), `status`.
- Sections, always in this order: `Idea` → `Translation` → `Next Actions` → `Links`.
- `Links` section is mandatory even if empty-looking — if the user mentions ANY URL, it goes here verbatim, with a short label. Never paraphrase a link away. This exists because links get lost is a recurring failure — don't repeat it.
- `Next Actions` is skipped only when the idea is a pure reflection with nothing to do yet.

## Category vs. priority vs. tags
- `category` (work/personal/other) is for filing only — never use it to decide what matters today.
- `priority` is set from what the user says matters right now (explicit "I want to do X first/today"), not guessed from category. Re-set it whenever the user does a fresh brain dump and states what's important — don't leave stale priorities.
- `tags` are the cross-cutting connective tissue — freeform, can span categories (e.g. `ai`, `career`, `crm`). Use tags, not category, to pull related ideas together when asked "what relates to X."

## Master list
- Lives at `notes/master-list.md`. One row per captured idea: date, title, category, priority, tags, status, link to the note file.
- Never auto-add a note to the master list. After capturing and summarizing an idea, ask the user once: "add this to the master list?" Only add on yes.
- The master list is the recheck surface — it's what the user scans to see everything open, not the individual note files.
- **Backlink**: when (and only when) a note is added to the master list, add a `**Master list:** [notes/master-list.md](master-list.md)` line directly under the title of that note. This makes travel bidirectional — master list → note (via the Note column) and note → master list (via this line). Notes never added to the master list don't get this line.

## Reflection / pattern review
- When the user asks something like "what have I been asking about most," "quick review," or "monthly reflection," scan `notes/*.md` (frontmatter tags/category/priority, not full bodies) over the relevant time window and summarize the patterns — recurring tags, categories that dominate, ideas that stayed `new` too long.
- Save the summary to `notes/reflections/YYYY-MM.md` (or a date range in the filename for ad-hoc reviews) so it's a running record, not a one-off chat answer.
- This is derived from existing notes, not a separately hand-maintained log — don't duplicate bookkeeping.

## Reply behavior
- Keep chat replies short (2-4 lines). Summarize, don't dump the file.
- Guess category and structure first; correct on feedback rather than asking upfront.
- When the user gives feedback on the system itself (not an idea), treat it as a system change: update the template/skill/strategy files, don't just apply it once by hand.
