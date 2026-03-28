# Honest Limitations

Parent: [[CLAUDE]]

> This is what SHINE OS doesn't do, what it costs, and where it breaks down.
> Read this before you invest time setting it up.

---

## What You Need (and What It Costs)

| Requirement | Cost | Notes |
|-------------|------|-------|
| Claude desktop app | Free | Available at claude.ai/download |
| Claude Pro plan | $20/month | Minimum to use Cowork |
| Claude Max plan | $100/month | Recommended for heavy sessions |
| Cowork mode | Included | Beta feature — enable in Claude settings |
| n8n Cloud (optional) | ~$20–50/month | Only needed for automation layer |
| Supabase (optional) | Free tier available | Paid for high-volume use |
| Retell (optional) | Per-minute pricing | Only needed for voice agents |

**Recommended minimum spend for serious use: ~$100/month (Claude Max)**

---

## Hard Limitations

**1. One folder, no Projects support**
SHINE OS assumes everything lives in a single folder selected in Cowork. Claude Code Projects (where you have separate project contexts) are not used here. Everything — agents, tasks, reports, memory — is in one filesystem folder. This works well for one business. For agencies running multiple independent clients, you'd need multiple installs or a workaround.

**2. You are still the trigger (without n8n)**
In the Cowork-only version, nothing happens automatically. Claude doesn't check your inbox while you sleep, doesn't send follow-ups, doesn't run scheduled tasks. You open Cowork, you ask, it acts. The n8n layer is what makes things autonomous. Be clear about this when setting expectations.

**3. Context window limits**
Large folders with many files can hit Claude's context limits in long sessions. SHINE OS is designed to avoid this (CLAUDE.md keeps things structured, only relevant files get loaded) but on very heavy build days you may hit limits. Max plan helps significantly.

**4. Cowork is a beta feature**
Cowork is a beta feature in the Claude desktop app. It could change, be paused, or behave differently across versions. SHINE OS is built on top of Anthropic's product roadmap. This is a real dependency risk to be aware of.

**5. Skills require manual installation**
There's no one-click plugin install yet. You copy two SKILL.md files into your Claude skills folder manually. Takes 5 minutes but it's not seamless. (One-click install is on the roadmap — see `Dev/ROADMAP.md`.)

**6. No mobile support**
Cowork is desktop only. You can't run SHINE sessions from your phone. You can read your session reports and TASKS.md on mobile (they're just markdown files in iCloud/Dropbox if you sync them), but you can't run an active session.

**7. No real-time collaboration**
Two people can't be in the same SHINE session simultaneously. The folder structure supports a team (multiple people running sessions against the same folder) but not true real-time co-working.

---

## What SHINE OS Is Not

- **Not a CRM.** It's not designed to replace HubSpot or Salesforce. It can act as a lightweight lead tracker without Supabase, but it's not a purpose-built CRM.
- **Not an email client.** Your agents can draft emails, but sending them requires a Gmail MCP connection or you copy-paste. This is intentional — Claude shouldn't be sending emails without you reviewing them.
- **Not a booking system.** SHINE OS doesn't replace your booking software. It can interact with booking data (with the right MCP), but it doesn't book appointments itself.
- **Not fully autonomous.** Even with n8n connected, SHINE OS is a human-in-the-loop system. Escalation paths, approval thresholds, and decision points are deliberately built in.

---

## When SHINE OS Is Probably Overkill

- You only use Claude occasionally (once a week or less)
- You have a single, simple workflow with no cross-session continuity
- You're not comfortable with markdown files and folder structures
- You want a no-setup, push-button AI tool

For those cases: just use Claude normally. SHINE OS is for people who use AI heavily enough that the lack of structure is costing them time.

---

## Known Issues (Current)

- The setup wizard (`/shine-setup`) does not yet interact with n8n or Supabase during setup — it customises local files only. Full automated provisioning is on the roadmap.
- `INDEX.md` is not auto-updated unless you set up the optional scheduled task.
- Agent prompt templates require manual editing — there's no guided form fill yet.

---

*Last updated: 2026-03-28 · hello@shineon.world*
