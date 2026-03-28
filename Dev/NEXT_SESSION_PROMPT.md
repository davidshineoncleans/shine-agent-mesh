# Next Session — n8n Onboarding Agent Build

> Copy this prompt into a new Cowork session (pointed at the shine-agent-mesh folder) to continue.

---

## Prompt to paste

```
I'm David Caldicott (david@shineon.world). I'm building SHINE OS — a public,
open-source AI operating system for small business founders built on Claude Cowork.
It's been extracted from my live system at Shine On Cleans (shineon.uk) and is
being released free under CC0.

The repo is at: Dev/Local Repositories/shine-agent-mesh/ in my Claude's Files folder.

Read these files first (they contain full context):
- README.md (what it is)
- Memory/design-decisions.md (all key decisions and reasoning)
- LIMITATIONS.md (honest constraints)
- USE_CASES.md (target users and day-to-day experience)
- TASKS.md (open items)

## What's been built

The Cowork layer is complete:
- CLAUDE.md (generic operating system file with my attribution baked in)
- TASKS.md, INDEX.md
- Agents/ — prompt templates for 5 roles (service-advisor, ops-captain, task-manager,
  receptionist, support-agent)
- Skills/shine-setup/SKILL.md — setup wizard that customises everything in one session
- Skills/shine-reports/SKILL.md — session report format
- Memory/glossary.md, Memory/design-decisions.md
- Setup/01_QUICK_START.md, Setup/02_ADD_YOUR_STACK.md
- USE_CASES.md, LIMITATIONS.md, LICENSE (CC0)

## What we're building this session

The n8n onboarding agent. The goal: a user hits shineon.world/install, fills in a
short form (business name, type, n8n URL, Supabase URL, email), and receives:

1. A customised CLAUDE.md for their business
2. Their Supabase tables provisioned (SQL migrations run)
3. Starter n8n workflows imported to their n8n instance
4. A self-contained HTML control panel app (their workspace dashboard)
5. A setup email with everything packaged

The onboarding runs on MY n8n instance (oxnmcfdkifrenxogzisq Supabase project)
and provisions THEIR infrastructure.

## Architecture decisions to make this session

1. What does the intake form look like? (Fields, where hosted — probably shineon.world/install)
2. What Supabase tables does every SHINE OS user need? (tasks, session_reports, leads minimum)
3. What n8n starter workflows ship with SHINE OS? (Lead_Intake, Task_Dispatcher, Session_Logger minimum)
4. What does the HTML control panel contain? (agent status, feature request form, stack status, docs links)
5. How does the onboarding workflow provision their n8n? (n8n has a REST API for workflow import)

## My existing infrastructure (you have MCP access to all of these)

- n8n Cloud: my instance at n8n.shineon.uk (MCP connected)
- Supabase: project oxnmcfdkifrenxogzisq (MCP connected)
- Gmail: davidcaldicottonline@gmail.com (MCP connected for sending setup emails)
- Stripe: connected (for future paid tiers)

## Important constraints

- Do NOT use any Shine On Cleans specific data, workflows, or customer information
- The onboarding workflows must work for ANY service business, not just cleaning
- Keep the intake form short — 5-8 fields maximum
- The control panel HTML must be self-contained (no hosting required, opens from local file)
- Be honest about what the automated onboarding can and can't do on day one

## Start here

1. Read the files listed above
2. Propose the architecture for the onboarding workflow (intake → provision → deliver)
3. Build it step by step

shineon.world contact: hello@shineon.world
```

---

## Context notes for the session

The full design decisions are in `Memory/design-decisions.md`. Key things to know:

- The product is called **SHINE OS** (not SHINE Agent Mesh — that's the internal n8n system)
- David wants this to be genuinely accessible to non-technical founders
- The control panel is a priority — it's the visual anchor that makes it feel like a product
- Paid tiers are coming (SHINE Pro = automated onboarding + support + commercial workflows)
- First distribution is TikTok — "free, no catch, tell us if you improve it"
- TikTok scripts and marketing copy are a separate session after the onboarding agent is built
