---
name: shine-reports
description: "Write structured session reports using the SHINE Dispatch format (S-H-I-N-E). Use for session reports, daily summaries, weekly wrap-ups, or any recurring operational report."
---

# SHINE Reports

Write all reports using the SHINE Dispatch format. Every session should produce one.

## Report Format

```markdown
# [Report Type] — [Topic/Date]

Parent: [[CLAUDE]]
Related: [[TASKS]]

**Status:** ⚡ IN PROGRESS → ✅ COMPLETE
**Session slug:** `YYYY-MM-DD_topic-name`

---

## Session Timing
- Started: YYYY-MM-DD HH:MM
- Ended: YYYY-MM-DD HH:MM
- Duration: ~Xh Ym

---

## S — Situation
[What was the opening prompt or situation that started this session? Include verbatim if possible.]

---

## H — Hypothesis
[What was the plan going in? What did you expect to solve?]

---

## I — Implementation
[What actually happened? Work block by work block. Be specific.]

### Work Block 1 — [Description] (HH:MM)
[What was done, decided, or created]

### Work Block 2 — [Description] (HH:MM)
[What was done, decided, or created]

---

## N — Next Steps
[What needs to happen next? Be concrete and assignable.]

---

## E — Evidence
[Files created, decisions made, metrics changed. A future session should be able to read this and know exactly what happened.]
```

---

## When to Use This

- **Session start:** Create `Reports/YYYY-MM-DD_session-{topic}_LIVE.md` immediately
- **During session:** Append Work Block entries after each significant piece of work
- **Session end:** Complete all sections, rename to remove `_LIVE` suffix

## Rules

- Always run `date` at session start and end to capture timing
- Always update `TASKS.md` before writing the final report
- The report captures the narrative. TASKS captures the state. Both are mandatory.
- `_LIVE` files are visible to other sessions — they mean "this work is happening now"
- If a session ends without a formal close, the `_LIVE` file stays. That's intentional.
