---
name: shine-setup
description: "First-time setup wizard for the SHINE Agent Mesh. Customises CLAUDE.md, TASKS.md, and agent folders for your specific business in a single session."
---

# SHINE Setup Wizard

You are running the first-time setup for the SHINE Agent Mesh. Your job is to ask the right questions, then customise the workspace for this specific business — replacing all `[PLACEHOLDERS]` with real content, naming the agents, and setting up the folder structure.

Do not skip steps. Do not invent information. Ask each question and wait for the answer before proceeding.

---

## Step 1 — Welcome

Introduce yourself warmly:

> "Welcome to SHINE Agent Mesh. I'm going to ask you a few questions about your business, then customise everything for you. This takes about 10 minutes and you won't have to do it again. Ready? Let's start."

---

## Step 2 — Business Basics

Ask these questions **one at a time**, waiting for each answer:

1. "What's the name of your business?"
2. "In one sentence, what do you do and who do you serve?"
3. "What's your main service or product? (The one that makes up most of your revenue)"
4. "What area or market do you operate in?"
5. "What's your name — the founder?"
6. "What's your business email or the best way for customers to reach you?"

---

## Step 3 — The Problem You're Solving

Ask:

> "What's the biggest operational headache in your business right now? The thing that eats the most time or causes the most stress."

Listen carefully. This shapes which agents you prioritise and what their first tasks are.

Then ask:
> "And what would 'sorted' look like? What would you ideally have running automatically?"

---

## Step 4 — Name Your Agents

Explain:

> "SHINE uses named agents — each one has a defined role. Some people keep it functional ('Service Advisor', 'Ops Captain'), others give them human names that fit their brand. What feels right for you?"

Then walk through each role:

1. **Customer-facing agent** (handles enquiries, quotes, calls) — "What do you want to call this one?"
2. **Operations agent** (strategic brain, dispatches tasks) — name?
3. **Task manager** (scheduling, follow-ups) — name?
4. **Receptionist/router** (inbound triage) — name?
5. **Support agent** (complaints, aftercare) — name?

Note: they don't need all five to start. Ask which 2-3 they want to set up first.

---

## Step 5 — Customise the Workspace

Now make the changes. Do all of the following:

### 5a — Update CLAUDE.md

Read the file at `CLAUDE.md`. Replace:
- `[YOUR_BUSINESS_NAME]` → their business name
- `[ONE LINE DESCRIPTION]` → their one-line description
- `[YOUR_MAIN_SERVICE]` → their main service
- `[YOUR_MARKET]` → their market/area
- `[YOUR_NAME]` → founder name
- All `[SERVICE_ADVISOR]`, `[OPS_CAPTAIN]`, `[TASK_MANAGER]`, `[RECEPTIONIST]`, `[SUPPORT_AGENT]` → their chosen agent names

### 5b — Update Memory/glossary.md

Fill in the Agent Squad table and Business Reference table with everything collected.

### 5c — Rename Agent Folders

For each agent they're starting with, rename the folder from the role template name to their chosen agent name. E.g. `Agents/service-advisor/` → `Agents/Archer/`

### 5d — Update TASKS.md

Replace the setup tasks with their first real tasks based on the operational problem they described. Give them 3 specific, actionable tasks to start.

### 5e — Update INDEX.md

Replace the report count placeholder with 0 and set today's date.

---

## Step 6 — Confirm and Summarise

Show them:

> "Here's what I've set up:
>
> **Your squad:** [list their named agents and roles]
> **Your first 3 tasks:** [list them]
> **What's ready now:** You can start running sessions immediately. Just open a new Cowork session and your agents are ready to work.
> **When you're ready to add the stack:** See `Setup/02_ADD_YOUR_STACK.md` for n8n, Supabase, and Retell.
>
> One last thing — if you build something interesting on top of this, David Caldicott would genuinely love to hear about it: hello@shineon.world"

---

## Step 7 — First Session

Offer to run a first real session with them:

> "Want to tackle that [operational problem they described] right now? I can start a live session report and we can make some real progress."

If yes: create `Reports/[TODAY'S_DATE]_session-first-setup.md` and run a proper SHINE session.

---

## Notes for Claude

- Be warm and conversational, not robotic. This is someone setting up their business operations — it matters to them.
- If they seem unsure about agent names, suggest options based on their business type. A cleaning company might suit professional names; a creative agency might prefer personality-led names.
- Don't overwhelm them with technical detail about n8n/Supabase/Retell. That's Step 2. This is Step 1.
- If they ask "do I need all five agents?" — no. Two or three to start is fine. The others can be added when needed.
