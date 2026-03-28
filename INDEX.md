# INDEX — SHINE Agent Mesh

Parent: [[CLAUDE]]
Related: [[TASKS]] · [[glossary]]

---

## Root Files

| File | Purpose |
|------|---------|
| [[CLAUDE]] | Operating system — read every session |
| [[TASKS]] | Work tracker — update every session |
| [[INDEX]] | This file |

---

## Folder Structure

```
shine-agent-mesh/
├── CLAUDE.md
├── TASKS.md
├── INDEX.md
├── Agents/        ← Named agent prompts and knowledge bases
├── Skills/        ← SHINE skill files (install to ~/.claude/skills/)
├── Memory/        ← Glossary, branding, business reference
├── Ops/           ← Business ops — pricing, pipelines, campaigns
├── Dev/           ← Technical assets (when you add the stack)
├── Reports/       ← Session reports
└── Setup/         ← Getting started guides
```

---

## Agents/

| Agent | Template | Role |
|-------|----------|------|
| service-advisor | [[PROMPT_TEMPLATE]] | Customer-facing: quotes, enquiries, calls |
| ops-captain | [[PROMPT_TEMPLATE]] | Strategic brain: pipeline, dispatch, decisions |
| task-manager | [[PROMPT_TEMPLATE]] | Execution: scheduling, follow-ups |
| receptionist | [[PROMPT_TEMPLATE]] | Inbound: routing and triage |
| support-agent | [[PROMPT_TEMPLATE]] | Support: complaints and aftercare |

---

## Skills/

| Skill | Command | What it does |
|-------|---------|-------------|
| shine-setup | `/shine-setup` | First-time setup wizard |
| shine-reports | `/shine-reports` | Session report format |

---

## Memory/

| File | Purpose |
|------|---------|
| [[glossary]] | Agent profiles, system IDs, key terms |

---

## Setup/

| File | Purpose |
|------|---------|
| [[01_QUICK_START]] | Up and running in 10 minutes |
| [[02_ADD_YOUR_STACK]] | n8n, Supabase, Retell when ready |

---

## Reports/

Session reports live here. Naming: `YYYY-MM-DD_session-{topic}.md`
