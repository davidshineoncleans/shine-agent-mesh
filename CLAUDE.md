# SHINE OS — Your AI Operating System

> Built by David Caldicott · hello@shineon.world · shineon.world
> Fork this. Use it. If you improve it, tell us: hello@shineon.world

---

## How to Use This File

This file is the brain of SHINE OS. Your AI reads it at the start of every session to understand your business, your agents, and how everything works.

**Claude Cowork** — This file loads automatically. Just open the folder and start talking.

**ChatGPT / Gemini / any AI** — Copy the contents of this file and paste it as your first message at the start of each session. Or use Custom Instructions / System Prompts to load it permanently.

**Obsidian + any AI** — Keep this as a note in your vault. Copy relevant sections when starting a session. The wiki-links still work natively in Obsidian.

The AI tool doesn't matter. The files are the system.

---

## What This Is

SHINE OS is an operating model for running your business with AI agents. Not a chat assistant — a structured squad of named agents, each with a defined role, working together through a shared task system.

You are the founder. Your agents are your AI operations team. This file is their shared briefing.

**What you get right now (no integrations needed):**
- A named AI squad with defined roles
- Session conventions that maintain context across days and weeks
- A task tracking system that survives between conversations
- A knowledge graph (wiki-links) connecting all your docs
- Agent prompt templates you can customise for any AI platform

**What you can add later (Tier 2 — shine-activated):**
- n8n Cloud — workflow automation between agents
- Supabase — persistent data (leads, tasks, customer records)
- Retell — AI voice agents that make and take calls
- Install guide: shineon.world/install

**What you can subscribe to (Tier 3 — shine-integrated):**
- Run on SHINE managed infrastructure
- Access Atlas (scheduling/ops), ShineOn (comms), full app suite
- Your agents powered by our existing mesh of workflows
- Free tier available — paid unlocks management agents and premium features
- Details: shineon.world/platform

---

## Your Business

> **First time?** Tell your AI: "I've just downloaded SHINE OS. Let's get set up." It will walk you through filling this section in.

| Field | Value |
|-------|-------|
| **Business name** | [YOUR_BUSINESS_NAME] |
| **What you do** | [ONE LINE DESCRIPTION] |
| **Primary service** | [YOUR_MAIN_SERVICE] |
| **Location/market** | [YOUR_MARKET] |
| **Your name** | [YOUR_NAME] |

---

## Your Agent Squad

Each agent has a defined role. Name them whatever suits your brand — the role is what matters.

| Agent | Role | What they handle |
|-------|------|-----------------|
| **[SERVICE_ADVISOR]** | Customer-facing | Enquiries, quotes, lead calls |
| **[OPS_CAPTAIN]** | Lead operations | Dispatching tasks, pipeline strategy |
| **[TASK_MANAGER]** | Task execution | Scheduling, follow-ups, reminders |
| **[RECEPTIONIST]** | Inbound routing | First contact, triage, handoffs |
| **[SUPPORT_AGENT]** | Customer support | Complaints, issues, aftercare |

> Agent prompts live in `Agents/[agent-name]/`. Rename the folders to match your agent names.

---

## Session Conventions

### Every Session Starts With

1. Note the date and time
2. Create `Reports/YYYY-MM-DD_session-{topic}_LIVE.md`
3. Write your opening objective in the S — Situation section
4. Set status: ⚡ IN PROGRESS

### During the Session

After each significant piece of work, log it:
```
### Work Block N — Description (HH:MM)
Brief note of what was done, decided, or created.
```

### Every Session Ends With

1. Update `TASKS.md` — mark done items `[x]`, add new items
2. Complete your session report (H, I, N, E sections)
3. Rename `_LIVE.md` → remove `_LIVE` suffix

Both steps are mandatory. The report captures the narrative. TASKS captures the state.

---

## File Organisation

Root contains 3 core files + 5 folders.

| Folder | What goes here |
|--------|---------------|
| `Agents/` | Your agent prompt files and knowledge bases |
| `Dev/` | Technical build assets — workflows, repos, integrations |
| `Memory/` | Persistent reference — glossary, branding, context |
| `Ops/` | Business operations — pricing, pipelines, campaigns |
| `Reports/` | Session reports (YYYY-MM-DD naming) |

**Archive convention:** Each folder may contain `_archive/` for superseded versions. Never delete — move to `_archive/`.

### File Naming

- `_DRAFT` — work in progress
- `_v2`, `_v3` — iterated versions
- `_FINAL` — ready to use
- `_BACKUP` — safety copy

---

## Task Tracking

`TASKS.md` is your single source of truth for everything in progress.

**Task levels:**

| Level | File | Purpose |
|-------|------|---------|
| **System** | `TASKS.md` (root) | Everything. Always updated. |
| **Project** | `TASKS.md` inside project folder | Detail for active projects |
| **Session** | Inline in session report | One-off items from a session |

Project-level task files must include `Parent: [[TASKS]]` in their header.

---

## Wiki-Links

If you're using Obsidian (or any tool that supports wiki-links), every `.md` file should include this header below the H1:

```
Parent: [[CLAUDE]]
Related: [[TASKS]] · [[glossary]]
```

Link to the note name (filename without `.md`), not the file path. Even if you're not using Obsidian, these links serve as a navigable reference — they tell you what connects to what.

---

## Safety Rules

- Never delete files — move to `_archive/` instead
- Never hardcode credentials in any file
- Never push real customer data to a public repository
- Credentials, API keys, and URLs belong in environment variables or a private config file

---

## Credits & Attribution

SHINE OS was created by David Caldicott — founder of Shine On Cleans, where this system runs a live business every day.

Three ways to go deeper:
- **shine-os** (this repo) — free, works with any AI
- **shine-activated** — self-hosted infrastructure (shineon.world/install)
- **shine-integrated** — managed platform under your brand (shineon.world/platform)

📧 hello@shineon.world
🌐 shineon.world

*Fork it. Ship it. Tell us what you improved.*
