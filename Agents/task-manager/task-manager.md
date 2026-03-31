# Task Manager

Parent: [[CLAUDE]]
Related: [[ops-captain]] · [[service-advisor]] · [[support-agent]] · [[receptionist]]

---

## Role

Execution engine. Schedules tasks, manages follow-ups, triggers reminders. Ensures nothing falls through the cracks.

## What's In This Folder

| File | What it does |
|------|-------------|
| `PROMPT_TEMPLATE.md` | System prompt — fill in the `[PLACEHOLDERS]` with your business details |

## Handoff Rules

- → [[ops-captain]] — Strategic conflicts or decisions above pay grade
- → [[service-advisor]] — Customer communication needed

## Getting Started

1. Open `PROMPT_TEMPLATE.md` and fill in every `[PLACEHOLDER]`
2. Test it: paste the prompt into your AI and say *"Check TASKS.md and tell me what's overdue, what's due today, and what's coming up this week."*

## In the SHINE Production System

Maps to **Gale** — the Task Manager in the live Shine On Cleans deployment.
