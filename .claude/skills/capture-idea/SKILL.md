---
name: capture-idea
description: Capture a raw, messy idea from conversation and turn it into a short markdown note — plain-language translation plus next actions. Use whenever the user is thinking out loud, rambling, brainstorming, or says things like "capture this", "idea:", "random thought", or just drops an unstructured idea without asking for anything else.
---

# Capture Idea

Goal: let the user talk, not type. Turn a messy spoken idea into one short markdown note. Never make them open an app or write it themselves.

## Steps

1. **Read the raw idea** as given — don't ask clarifying questions unless it's genuinely impossible to guess intent. Guessing wrong and fixing later is cheaper than an interrogation.
2. **Guess the category**: `work`, `personal`, or `other`. Use context clues (mentions of job/team/product → work; mentions of health/family/hobbies → personal; everything else → other).
3. **Write the translation**: 2–4 short sentences, plain words, the user's own voice/tone. This answers "what does this actually mean" — not a restatement, an interpretation.
4. **Break it into next actions**: 2–5 concrete, doable checkbox items. Skip this section if the idea has no action yet (pure thought/reflection) — don't force actions that don't exist.
5. **Save the note** to `notes/YYYY-MM-DD-slug.md` (slug = 3-6 words from the idea, kebab-case) using `templates/idea-template.md`.
6. **Reply short**: 2-4 lines max. Give the translation + actions inline in chat (so the user doesn't have to open the file), then the file path. No preamble, no re-explaining what you just wrote.

## Rules

- Keep every reply short. If the user wants more, they'll ask.
- Don't dump the whole file back into chat — summarize.
- Don't ask "is this work or personal" — decide, and let them correct you if wrong.
- One idea = one file. If they drop multiple ideas in one message, split into multiple files.
