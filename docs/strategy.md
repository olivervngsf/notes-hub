# System strategy (internal — not a checklist)

This is the layer underneath the notes. It defines *how* the capture system runs, so behavior stays consistent across sessions. Not something you read day-to-day — reference it when a skill's behavior needs to change.

## The problem this solves

Brain dumps are messy: unstructured thoughts, duplicate ideas, unclear statements, missing connections, hard to turn into action. Without a system, processing an idea is inconsistent — different format, different quality, different result every time. With a system, it's consistent — same process, same format, predictable result every time. That consistency is the entire point of this doc.

## The Consistency Rules

1. **Always use the same template** — every note follows `templates/idea-template.md`. No one-off formats.
2. **Always use standard categories** — `work` / `personal` / `other`, nothing invented per note.
3. **Always clarify ambiguous items** — when an idea is genuinely unclear, don't leave it guessed-and-unconfirmed, but don't interrogate either. Default to restating it back ("do you mean X?") so the user can correct in one word — this also helps them hear back what they actually said. Only ask an open question when a restatement isn't possible.
4. **Always find connections** — auto-check every new idea against existing notes' tags/category for overlap or related items, in the background, without being asked. Surface it briefly if something relevant turns up; say nothing if it doesn't.
5. **Always consolidate** — every note gets a row on the master list (`notes/master-list.md`) automatically at creation. No asking, no opt-in.
6. **Always convert to tasks** — every idea gets a `Next Actions` checklist unless it's a pure reflection with nothing to do yet.
7. **Always show your work** — the reasoning (translation, connections, why this priority) lives in the note file, where it's useful. It does not belong in the chat reply — don't explain *why* something was organized a certain way in chat, just state the result.

## Note format
- One idea = one file: `notes/YYYY-MM-DD-slug.md`.
- Frontmatter: `date`, `category`, `priority` (high/medium/low), `tags` (freeform list), `status`.
- Sections, always in this order: `Idea` → `Translation` → `Next Actions` → `Links`.
- `Links` section is mandatory even if empty-looking — if the user mentions ANY URL, it goes here verbatim, with a short label. Never paraphrase a link away. This exists because links get lost is a recurring failure — don't repeat it.
- `Next Actions` is skipped only when the idea is a pure reflection with nothing to do yet.

## Category vs. priority vs. tags
- `category` (work/personal/other) is for filing only — never use it to decide what matters today.
- `priority` is set from what the user says matters right now (explicit "I want to do X first/today"), not guessed from category. Re-set it whenever the user does a fresh brain dump and states what's important — don't leave stale priorities.
- `tags` are the cross-cutting connective tissue — freeform, can span categories (e.g. `ai`, `career`, `crm`). Use tags, not category, to pull related ideas together, and to auto-check connections (Rule 4).

## Master list
- Lives at `notes/master-list.md`. One row per captured idea: date, title, category, priority, tags, status, link to the note file.
- Every note gets added automatically at capture time — no asking, no confirmation needed. This is a change from the earlier version of this rule (which required an explicit yes each time).
- The master list is the recheck surface — it's what the user scans to see everything open, not the individual note files.
- **Backlink**: every note gets a `**Master list:** [notes/master-list.md](master-list.md)` line directly under its title, added at the same time as the master list row. This makes travel bidirectional — master list → note (via the Note column) and note → master list (via this line).

## Reflection / pattern review
- When the user asks something like "what have I been asking about most," "quick review," or "monthly reflection," scan `notes/*.md` (frontmatter tags/category/priority, not full bodies) over the relevant time window and summarize the patterns — recurring tags, categories that dominate, ideas that stayed `new` too long.
- Save the summary to `notes/reflections/YYYY-MM.md` (or a date range in the filename for ad-hoc reviews) so it's a running record, not a one-off chat answer.
- This is derived from existing notes, not a separately hand-maintained log — don't duplicate bookkeeping.

## Reply behavior
- Keep chat replies short (2-4 lines). Summarize, don't dump the file. Never explain the *why* behind formatting/organizing choices in chat (Rule 7) — that reasoning lives in the note.
- Guess category and structure first; when genuinely ambiguous, restate-and-confirm rather than open-ended questioning (Rule 3).
- When the user gives feedback on the system itself (not an idea), treat it as a system change: update the template/skill/strategy files, don't just apply it once by hand.
