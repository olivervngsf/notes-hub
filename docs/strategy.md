# System strategy (internal — not a checklist)

This is the layer underneath the notes. It defines *how* the capture system runs, so behavior stays consistent across sessions. Not something you read day-to-day — reference it when a skill's behavior needs to change.

## The problem this solves

Brain dumps are messy: unstructured thoughts, duplicate ideas, unclear statements, missing connections, hard to turn into action. Without a system, processing an idea is inconsistent — different format, different quality, different result every time. With a system, it's consistent — same process, same format, predictable result every time. That consistency is the entire point of this doc.

## Why this works

Consistency buys: same quality every time, predictable results, nothing missed, faster processing (no re-deciding the format each time), better organization, and output that's clean enough to actually reuse (in an interview answer, a portfolio, a review). The system pays for itself the moment output needs to be trusted without re-checking it.

## When to use this system

Every time — not just for one-off "capture an idea" moments. Applies to: interview prep, organizing project ideas, clarifying vague goals, breaking down a complex problem, processing feedback, planning anything with more than one moving part. If it's a brain dump or something that needs breaking down, run it through this system rather than answering ad hoc.

## The Consistency Rules

1. **Always use the same template** — every note follows `templates/idea-template.md`. No one-off formats.
2. **Always use standard categories** — `work` / `personal` / `other`, nothing invented per note.
3. **Always clarify ambiguous items** — when an idea is genuinely unclear, don't leave it guessed-and-unconfirmed, but don't interrogate either. Default to restating it back ("do you mean X?") so the user can correct in one word — this also helps them hear back what they actually said. Only ask an open question when a restatement isn't possible.
4. **Always find connections, and dedupe** — auto-check every new idea against existing notes' tags/category for overlap, in the background, without being asked. If it's a genuine duplicate (not just related), fold it into the existing note instead of creating a new one — merge, don't multiply. If it's related but distinct, link them (see `## Related` convention) and say nothing unless something's actually relevant.
5. **Always consolidate** — every note gets a row on the master list (`notes/master-list.md`) automatically at creation. No asking, no opt-in.
6. **Always convert to tasks, in priority order** — every idea gets a `Next Actions` checklist unless it's a pure reflection with nothing to do yet. Within that list, the most important/urgent item goes first — don't leave tasks in whatever order they were mentioned if that's not the order they matter in.
7. **Always show your work** — the reasoning (translation, connections, why this priority) lives in the note file, where it's useful. It does not belong in the chat reply — don't explain *why* something was organized a certain way in chat, just state the result.

## Note format
- One idea = one file: `notes/YYYY-MM-DD-slug.md`.
- Frontmatter: `id` (sequential integer, see below), `date`, `category`, `priority` (high/medium/low), `tags` (freeform list), `status`.
- Sections, always in this order: `Idea` → `Translation` → `Next Actions` → `Links`.
- `Links` section is mandatory even if empty-looking — if the user mentions ANY URL, it goes here verbatim, with a short label. Never paraphrase a link away. This exists because links get lost is a recurring failure — don't repeat it.
- `Next Actions` is skipped only when the idea is a pure reflection with nothing to do yet.

## Category vs. priority vs. tags
- `category` (work/personal/other) is for filing only — never use it to decide what matters today.
- `priority` is set from what the user says matters right now (explicit "I want to do X first/today"), not guessed from category. Re-set it whenever the user does a fresh brain dump and states what's important — don't leave stale priorities.
- `tags` are the cross-cutting connective tissue — freeform, can span categories (e.g. `ai`, `career`, `crm`). Use tags, not category, to pull related ideas together, and to auto-check connections (Rule 4).

## ID
- Every note gets a short sequential integer `id` (1, 2, 3...) — the next unused number, read off the highest ID currently in `notes/master-list.md`.
- The `id` is the quick-reference handle: the user can say "update ID 6" instead of the full title, and it's the first column in the master list.
- Never reuse or renumber IDs, even if a note is later deleted or merged.

## Master list
- Lives at `notes/master-list.md`. One row per captured idea: id, date, title, category, priority, tags, status, link to the note file.
- Every note gets added automatically at capture time — no asking, no confirmation needed. This is a change from the earlier version of this rule (which required an explicit yes each time).
- **Sort order**: high priority first, then medium, then low. Within the same priority, keep insertion order (oldest first). A new note gets inserted into its priority band, not appended to the bottom — and if a note's priority changes later, move its row to match.
- The master list is the recheck surface — it's what the user scans to see everything open, not the individual note files.
- **Backlink**: every note gets a `**Master list:** [notes/master-list.md](master-list.md)` line directly under its title, added at the same time as the master list row. This makes travel bidirectional — master list → note (via the Note column) and note → master list (via this line).

## Reflection / pattern review
- When the user asks something like "what have I been asking about most," "quick review," or "monthly reflection," scan `notes/*.md` (frontmatter tags/category/priority, not full bodies) over the relevant time window and summarize the patterns — recurring tags, categories that dominate, ideas that stayed `new` too long.
- Save the summary to `notes/reflections/YYYY-MM.md` (or a date range in the filename for ad-hoc reviews) so it's a running record, not a one-off chat answer.
- This is derived from existing notes, not a separately hand-maintained log — don't duplicate bookkeeping.

## Pre-save checklist

Before saving a note (or presenting a brain dump's output), silently verify:
- [ ] Same template used?
- [ ] Items stated clearly (no leftover ambiguity)?
- [ ] Connections to existing notes checked?
- [ ] Duplicates merged, not re-created?
- [ ] Tasks specific and doable, not vague?
- [ ] Tasks in priority order?
- [ ] Is the reasoning captured in the note itself (Rule 7)?

This is a self-check, not something to show the user — if something fails, fix it before saving, don't narrate the check in chat.

## Reply behavior
- Keep chat replies short (2-4 lines). Summarize, don't dump the file. Never explain the *why* behind formatting/organizing choices in chat (Rule 7) — that reasoning lives in the note.
- Guess category and structure first; when genuinely ambiguous, restate-and-confirm rather than open-ended questioning (Rule 3).
- When the user gives feedback on the system itself (not an idea), treat it as a system change: update the template/skill/strategy files, don't just apply it once by hand.
