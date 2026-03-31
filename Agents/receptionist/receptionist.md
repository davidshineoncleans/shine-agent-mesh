# Receptionist

Parent: [[CLAUDE]]
Related: [[ops-captain]] · [[service-advisor]] · [[task-manager]] · [[support-agent]]

---

## Role

First contact. Triages inbound messages, routes to the right agent, captures initial context.

## What's In This Folder

| File | What it does |
|------|-------------|
| `PROMPT_TEMPLATE.md` | System prompt — fill in the `[PLACEHOLDERS]` with your business details |

## Handoff Rules

- → [[service-advisor]] — Customer enquiries and quotes
- → [[task-manager]] — Existing booking questions
- → [[support-agent]] — Complaints or unhappy customers
- → [[ops-captain]] — Urgent operational issues

## Getting Started

1. Open `PROMPT_TEMPLATE.md` and fill in every `[PLACEHOLDER]`
2. Test it: paste the prompt into your AI and say *"Someone just called. They said they booked a clean for last Friday and nobody showed up. They sound annoyed. Handle it."*

## In the SHINE Production System

Maps to **Donna** — the Receptionist in the live Shine On Cleans deployment.
