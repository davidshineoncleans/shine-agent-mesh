# SHINE Agent Mesh — Operating System

> Built by David Caldicott · hello@shineon.world · shineon.world
> Fork this. Use it. If you improve it, tell us: hello@shineon.world

---

## What This Is

SHINE is an operating model for running your business with AI agents. Not a chat assistant — a structured squad of named agents, each with a defined role, working together through a shared task system.

You are the founder. Your agents are your AI operations team. This file is their shared briefing.

**What you get without any integrations:**
- A named AI squad with defined roles
- Session conventions that maintain context across days and weeks
- A task tracking system that survives between conversations
- A knowledge graph (Obsidian wiki-links) connecting all your docs
- A setup wizard that customises everything for your business

**What you can add later:**
- n8n Cloud — for workflow automation between agents
- Supabase — for persistent data (leads, tasks, customer records)
- Retell — for AI voice agents that make and take calls

---

## Your Business

> **Run the setup wizard first.** Open Cowork, type `/shine-setup`, and it will fill this section in for you.

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

1. Run `date` to capture start time
2. Create `Reports/YYYY-MM-DD_session-{topic}_LIVE.md`
3. Note your opening objective in the S — Situation section
4. Set status: `⚡ IN PROGRESS`

### During the Session

After each significant piece of work, append a work block entry to your live report:
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

Root contains 3 files + 5 folders only.

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

## Wiki-Links (Obsidian)

Every `.md` file should include this header block below the H1:

```
Parent: [[CLAUDE]]
Related: [[TASKS]] · [[glossary]]
```

Link to the note name (filename without `.md`), not the file path. Use `[[glossary]]` not `[[Memory/glossary.md]]`.

---

## Safety Rules

- Never delete files — move to `_archive/` instead
- Never hardcode credentials in any file in this repo
- Never push real customer data to a public repository
- Credentials, API keys, and URLs belong in environment variables or a private config file (not tracked by git)

---

## Credits & Attribution

SHINE Agent Mesh was created by David Caldicott.

If you build something useful on top of this, we'd genuinely love to hear about it:
📧 hello@shineon.world
🌐 shineon.world

*Fork it. Ship it. Tell us what you improved.*
