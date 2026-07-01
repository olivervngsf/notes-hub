---
name: capture-idea
description: Capture a raw, messy idea from conversation and turn it into a short markdown note — plain-language translation plus next actions. Also handles prioritizing a brain dump ("what should I focus on today") and pattern reviews ("what have I been asking about most", "quick review"). Use whenever the user is thinking out loud, rambling, brainstorming, asking what to prioritize, or asking for a reflection/review of their captured ideas.
---

# Capture Idea

Goal: let the user talk, not type. Turn a messy spoken idea into one short markdown note. Never make them open an app or write it themselves.

## Steps

1. **Read the raw idea** as given. If it's ambiguous, don't interrogate — restate it back ("do you mean X?") so it's a one-word confirm/correct, not an open question. Only ask a real open question when a restatement isn't possible.
2. **Guess the category**: `work`, `personal`, or `other`. Use context clues (mentions of job/team/product → work; mentions of health/family/hobbies → personal; everything else → other).
3. **Set priority and tags**: `priority` (high/medium/low) from what the user says matters right now — if they just did a brain dump and named what's important today, that item is high, don't leave it at a stale default. `tags` are freeform and cross-cutting (can span categories).
4. **Auto-check for connections**: before writing, scan existing notes' tags/category for overlap with this idea — do this every time, without being asked. Mention it briefly in the reply only if something relevant turns up; say nothing if it doesn't.
5. **Write the translation**: 2–4 short sentences, plain words, the user's own voice/tone. This answers "what does this actually mean" — not a restatement, an interpretation.
6. **Break it into next actions**: 2–5 concrete, doable checkbox items. Skip this section if the idea has no action yet (pure thought/reflection) — don't force actions that don't exist.
7. **Capture every link verbatim** in a `## Links` section — any URL the user mentions, exact and labeled. Never leave this out; losing links is the #1 failure mode of this skill.
8. **Save the note** to `notes/YYYY-MM-DD-slug.md` (slug = 3-6 words from the idea, kebab-case) using `templates/idea-template.md`.
9. **Add it to the master list automatically**: every note gets a row in `notes/master-list.md` at creation — no asking. Also add the `**Master list:** [notes/master-list.md](master-list.md)` backlink line under the note's title, so travel works both directions.
10. **Reply short**: 2-4 lines max. Give the translation + actions inline in chat (so the user doesn't have to open the file), then the file path. State the result, not the reasoning behind how it was organized — that reasoning lives in the note itself.

## Prioritizing across a brain dump

When the user drops several ideas and then says what matters most today, don't just file them evenly — set `priority` per idea based on what they said, and say back which one(s) you'd tackle first (stated urgency > time available > everything else). This is a judgment call each time, not a fixed rule.

## Pattern review

If the user asks what they've been asking about most, for a quick review, or a monthly reflection, see `docs/strategy.md` → "Reflection / pattern review": scan note frontmatter (tags/category/priority) across the time window, summarize the patterns, and save to `notes/reflections/YYYY-MM.md`.

## The Consistency Rules

Full rationale in `docs/strategy.md` → "The Consistency Rules." Short version: same template, standard categories, clarify by restating (not interrogating), auto-find connections in the background, always consolidate into the master list, always convert to tasks, keep the reasoning in the note — not in chat.

## Rules

- Keep every reply short. If the user wants more, they'll ask.
- Don't dump the whole file back into chat — summarize, and skip explaining formatting/organizing choices.
- Don't ask "is this work or personal" — decide, and let them correct you if wrong.
- One idea = one file. If they drop multiple ideas in one message, split into multiple files.
- Underlying behavior rules live in `docs/strategy.md`. If the user gives feedback on how the system itself works (not on an idea), update the template/skill/strategy files — don't just patch the one note by hand.
