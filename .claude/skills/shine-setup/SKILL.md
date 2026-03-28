---
name: shine-setup
description: "First-time setup wizard for SHINE Agent Mesh. Runs a guided session that goes from zero to a working AI operating system — with something impressive happening before any speccing."
---

# SHINE Setup Skill

**Trigger phrases:** "let's get set up", "I've just downloaded SHINE", "set up my workspace", "run setup", or any first message from a user whose CLAUDE.md still contains `[PLACEHOLDER]` values.

**What this does:** Takes a new user from zero to a working AI operating system in about 10 minutes. Leads with something impressive before touching any configuration.

**Architecture note for builders:** This skill is intentionally modular. Each step is self-contained. To add a new step, copy the Step Template at the bottom and insert it where it fits. The webhook call step (Step 3) is a stub — wire it up when your n8n intake endpoint is ready.

---

## STEP 1 — Welcome & First Questions

Say this (warm, direct, no waffle):

> Welcome to SHINE Agent Mesh. 🙌
>
> In the next 10 minutes, you're going to have a named AI squad running your business. Not a chatbot. Not a prompt library. An operating model — with agents that handle enquiries, think strategically, keep things moving, and log everything.
>
> But first — before we configure anything — I want to show you what the end result actually feels like.
>
> Two quick questions:

Ask:
1. What's the name of your business?
2. What kind of business is it? (e.g. cleaning, plumbing, consulting, coaching — just a few words)

Store as `{{business_name}}` and `{{business_type}}`. Confirm and move to Step 2.

---

## STEP 2 — Find the Real Problem

Don't spec anything yet. Find the pain first.

Ask:

> What's the one thing in your business that's eating your time or driving you mad right now? Leads falling through the cracks, no-shows, quote follow-ups, late payments, admin — anything.

Let them answer freely. Reflect it back in one sentence. This becomes the anchor for everything that follows.

Store as `{{core_problem}}`.

Then say:

> Perfect. That's exactly what we're going to fix. And I want to show you *how* before we set anything up.

Move to Step 3.

---

## STEP 3 — The Demo Call ⭐ [WEBHOOK STUB — activate when endpoint is live]

**This is the "wow" moment. Run this before any agent naming or configuration.**

Say:

> Here's something a bit different. Instead of telling you what your AI agent will sound like — I want to let you hear it.
>
> If you give me your phone number, I'll send a message to the SHINE system and one of our agents will call you within 60 seconds. Short demo call — just to show you the kind of thing your own agent will be doing once we've built it.
>
> Want to try it?

If yes, ask for their phone number.

**Fire this webhook:**

```
POST https://shineon.world/api/welcome-call
Content-Type: application/json

{
  "business_name": "{{business_name}}",
  "business_type": "{{business_type}}",
  "core_problem": "{{core_problem}}",
  "phone": "{{phone_number}}",
  "source": "shine-setup"
}
```

Then say:

> Done — you should get a call in the next 60 seconds. Answer it and see what you think. While you're waiting, let's keep going.

If they skip: acknowledge it warmly and move on. Don't push.

> **[BUILDER NOTE: This step is a stub. The endpoint needs to be live and wired to an n8n workflow that triggers a Retell welcome call. See `Dev/NEXT_SESSION_PROMPT.md` for the build spec. To activate: build the endpoint, replace the URL, delete this note.]**

---

## STEP 4 — Name Your Squad

Now they've experienced (or heard about) the end result, naming agents feels real — not abstract.

Say:

> Now let's make this yours. Your AI squad needs names — not "Agent 1". Real names that fit your vibe.
>
> Here are the five roles. Name them whatever you want — someone you admire, a character, a team member you wish you had.

Present the five roles and ask for a name for each:

| Role | What they do | Default name |
|------|-------------|--------------|
| Service Advisor | Handles all customer enquiries, quotes, and calls | Archer |
| Ops Captain | Strategic brain — pipeline, decisions, dispatch | Marshall |
| Task Manager | Scheduling, follow-ups, keeps things moving | Gale |
| Receptionist | Triages inbound, routes to the right agent | Donna |
| Support Agent | Handles complaints, tricky situations | Giles |

Store as:
- `{{service_advisor_name}}`
- `{{ops_captain_name}}`
- `{{task_manager_name}}`
- `{{receptionist_name}}`
- `{{support_agent_name}}`

---

## STEP 5 — Build the Workspace

Do this efficiently — don't narrate every edit. Just do it.

**5a. Update CLAUDE.md**
- Replace `[YOUR BUSINESS NAME]` → `{{business_name}}`
- Replace `[YOUR BUSINESS TYPE]` → `{{business_type}}`
- Replace agent placeholder names with the names from Step 4

**5b. Update Memory/glossary.md**
- Fill in the agent squad table with chosen names and roles
- Add `{{business_name}}` to the business reference section

**5c. Update TASKS.md**
- Mark the first setup task (`[x]`) — done
- Add: "First session with {{ops_captain_name}} — describe your business and ask what to tackle first"

**5d. Update INDEX.md**
- Replace `[YOUR BUSINESS NAME]` with `{{business_name}}`
- Update the Last Updated timestamp

Confirm when done:

> All set. Your workspace is live for {{business_name}}. Your squad is ready.

---

## STEP 6 — First Real Win

Don't end on setup. End on action.

Remind them of the problem from Step 2, then say:

> You said earlier that {{core_problem}} is the thing driving you mad. Let's not leave that on the table.
>
> Want to tackle it right now? Tell me a bit more and we'll figure out which of your agents owns it and what the first move is.

If they engage: work the problem. Create a real task in TASKS.md. Show them the system in action.

If they want to stop: leave them with a ready-to-go prompt for next session:

> Next time you open this workspace, say: "{{ops_captain_name}}, I want to work on {{core_problem}} — where do we start?"

---

## [ADD NEW STEPS HERE]

> **For builders:** Insert additional steps between any existing ones. Good candidates for future steps:
> - **Step 3b:** "Design your first Retell agent" — walk through Retell setup, generate a prompt, test a live call
> - **Step 3c:** "Connect your calendar" — link Google Calendar so the Ops Captain can see what's coming
> - **Step 5e:** "Set up your first email drip" — configure outbound sequences for new leads
> - **Step 7:** "Invite your team" — multi-user workspace setup
>
> Each step should have: one clear goal, what Claude says, what Claude does, what gets stored, what gets written, and a confirmation line.

---

## Step Template

Copy this to add a new step:

```
## STEP N — [Name]

**Goal:** [One sentence — what this achieves for the user]

Say: [What Claude says to introduce this step]

Ask: [Questions to ask, if any]

Do: [What Claude does — files to edit, webhooks to fire, etc.]

Store: [Variable names for anything captured, e.g. {{phone_number}}]

Confirm: [What Claude says when the step is complete]

Then: Move to Step N+1.
```
