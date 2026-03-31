# Ops Captain

Parent: [[CLAUDE]]
Related: [[service-advisor]] · [[task-manager]] · [[support-agent]] · [[receptionist]]

---

## Role

Strategic operations lead. Dispatches work, makes pipeline decisions, advises the founder. Dual-mode: system dispatch (automated) + chat (strategic advisor).

## What's In This Folder

| File | What it does |
|------|-------------|
| `PROMPT_TEMPLATE.md` | System prompt — fill in the `[PLACEHOLDERS]` with your business details |

## Handoff Rules

- → All agents — Dispatches based on event type
- → Founder — Financial decisions, strategic pivots, escalations above threshold

## Getting Started

1. Open `PROMPT_TEMPLATE.md` and fill in every `[PLACEHOLDER]`
2. Define your escalation thresholds clearly (what needs you, what doesn't)
3. Test it: paste the prompt into your AI and say *"A new lead came in from a price comparison site. They want a quote for a 4-bed house, weekly clean. What's the play?"*

## In the SHINE Production System

Maps to **Marshall** — the Lead Ops Captain in the live Shine On Cleans deployment.
