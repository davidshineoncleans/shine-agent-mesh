---
name: shine-reports
description: "Write structured session reports using the SHINE Dispatch format (S-H-I-N-E). Mandatory at session start — create the _LIVE file BEFORE the first reply. Also covers daily, weekly, and project reports."
---

# SHINE Reports

Session reports are the memory layer. Every session produces one. The `_LIVE` file is the **first thing created** — before any tool calls, research, or reply to the user.

Invisible work is the enemy. A half-filled report beats nothing.

---

## The SHINE Dispatch format

Every report uses this backbone, adapted per type:

| Letter | Meaning |
|--------|---------|
| **S** | Situation — opening prompt (verbatim) + context |
| **H** | Hypothesis — what you thought would happen |
| **I** | Interventions — what actually happened, work block by work block |
| **N** | Next steps — assignable items |
| **E** | Evidence — files, decisions, metrics changed |

---

## Session report lifecycle (mandatory)

Three states. Each has a file suffix.

| State | Suffix | Location |
|-------|--------|----------|
| In progress | `_LIVE` | `Reports/` |
| Wrapped | `_COMPLETE` | `Reports/` |
| Archived | *(no suffix)* | `Reports/_archive/` |

### At session START (before the first reply)

1. Run `date` to capture start time
2. Create `Reports/YYYY-MM-DD_session-{topic}_LIVE.md`
3. Paste the user's opening prompt **verbatim** into the `S` section
4. Set status `⚡ IN PROGRESS`
5. **Only then begin the actual work**

### DURING the session

After each major action, append a work block to the `I — Interventions` section — decisions, not keystrokes. Every outgoing message to the user is **mirrored into the report**, so the report + prompts = the full session record.

### At session END

1. Update `TASKS.md`
2. Complete the remaining sections (`H`, `I`, `N`, `E`)
3. Rename `_LIVE` → `_COMPLETE`
4. Write the `.hc.md` companion (see the `humancode` skill)
5. Archive `_COMPLETE` files to `Reports/_archive/` after the active window (roughly a month)

---

## Report template

```markdown
# Session — {topic}

**Status:** ⚡ IN PROGRESS
**Date:** YYYY-MM-DD

---

## Session Timing

- Started: YYYY-MM-DD HH:MM
- Ended: *(fill at end)*
- Duration: *(fill at end)*

---

## S — Situation

{The user's opening prompt, verbatim. Context. Starting state.}

---

## H — Hypothesis

{What you expected. What you're trying to do and why.}

---

## I — Interventions

{Work blocks, in order. Append as you go.}

### {HH:MM} — {short title}

What happened. Decisions made. Files touched.

---

## N — Next Steps

- [ ] Task 1
- [ ] Task 2

---

## E — Evidence

- Files created: `path/to/file.md`
- Decisions made: …
- External links: …
```

---

## Other report types

The same `S-H-I-N-E` backbone works for:

- **Daily report** — all sessions + tasks + decisions for a day
- **Weekly report** — five highlights, issues, next-week priorities
- **Project report** — scope, milestones, blockers, next milestones
- **Lead / customer report** — situation, facts, blockers, next best action (for operational reporting)

Lean sections where they fit, heavier where data is involved. The skeleton is always the same.

---

## Rules

- `_LIVE` files are visible to other sessions — they mean *"this work is happening now."* If a session ends without a formal close, the `_LIVE` file stays. That's intentional.
- Always run `date` at session start and end to capture timing.
- Always update `TASKS.md` before finalising the report.
- Always write the `.hc.md` companion after `_LIVE` → `_COMPLETE`.
- Keep reports scannable — readers pick up context for the next session from them.
- Timing block is mandatory.
- Tone: clear, concise, factual. Tables over prose where data is involved.

---

## File naming

- Session (live): `YYYY-MM-DD_session-{topic}_LIVE.md`
- Session (complete): `YYYY-MM-DD_session-{topic}_COMPLETE.md`
- Session (archived): moved to `Reports/_archive/`
- Daily: `YYYY-MM-DD_end-of-day.md`
- Weekly: `YYYY-WNN_weekly-report.md`

---

## Companion files

Every `.md` session report gets a `.hc.md` companion — the compressed HumanCode version. Target <30% of the source line count. See the `humancode` skill.

---

> The report captures the narrative. `TASKS.md` captures the state. Both are mandatory.
