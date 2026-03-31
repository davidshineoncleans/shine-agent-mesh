# Service Advisor

Parent: [[CLAUDE]]
Related: [[ops-captain]] · [[task-manager]] · [[support-agent]] · [[receptionist]]

---

## Role

Customer-facing agent handling all enquiries, quotes, and calls. The voice and face of the business.

## What's In This Folder

| File | What it does |
|------|-------------|
| `PROMPT_TEMPLATE.md` | System prompt — fill in the `[PLACEHOLDERS]` with your business details |
| `pricing.md` | Your pricing guide — services, rates, rules |
| `faq.md` | Common questions your agent can answer without you |
| `objections.md` | How to handle price pushback and trust concerns |
| `service-areas.md` | Where you operate and how to handle out-of-area leads |

## Handoff Rules

- → [[task-manager]] — When work needs scheduling
- → [[support-agent]] — When customer has a complaint or issue
- → Founder — Unusual requests or high-value decisions

## Getting Started

1. Open `PROMPT_TEMPLATE.md` and fill in every `[PLACEHOLDER]`
2. Fill in `pricing.md` with your real prices
3. Add your top 5 questions to `faq.md`
4. Test it: paste the prompt into your AI and say *"A customer just called asking for a quote for a 3-bedroom house clean. Handle it."*

## In the SHINE Production System

Maps to **Archer** — the Service Advisor in the live Shine On Cleans deployment.
