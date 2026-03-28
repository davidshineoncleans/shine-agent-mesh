# SHINE OS — Use Cases & Day-to-Day Experience

Parent: [[CLAUDE]]
Related: [[README]] · [[Setup/01_QUICK_START]]

> Real examples of what SHINE OS looks like in practice, for different business types.
> All based on the no-stack version (no n8n, no Supabase, no Retell) unless stated.

---

## Who This Is For

SHINE OS is built for founders and operators running service businesses who use Claude heavily but feel like they're starting from scratch every session. You have context in your head that Claude doesn't have. You're losing decisions between conversations. Your AI tools add noise instead of removing it.

SHINE OS gives your Claude a named squad, a shared task list, and a session discipline that means every conversation picks up where the last one left off.

---

## Use Case 1 — Freelance Trades (Plumber, Electrician, Landscaper)

**The problem:** Spending 30+ minutes a day quoting jobs, following up on enquiries, and chasing leads that came in yesterday and got buried.

**Setup:** Names their service advisor "Jake." Pastes their pricing guide into `Agents/jake/pricing.md`. Three sentences about their service area and what they won't touch.

**Day one:** Opens Cowork. *"Jake, quote this job — 3-bed semi, full rewire, Manchester."* Jake knows their day rates, their minimum job size, their standard exclusions. Quote back in 60 seconds. Not generic — their voice, their numbers.

**Week two:** The task list has follow-up reminders. *"Jake, who did we quote last week that we haven't heard back from?"* Not a perfect CRM. But better than the Post-it notes.

**Month two (with Supabase):** Every lead logged. Every quote tracked. The ops captain shows them their conversion rate for the first time. They find out they're closing 40% of kitchen rewires and 15% of garage conversions. They stop quoting garage conversions.

**What Claude actually does:** Holds the business context so the owner doesn't have to re-explain it every time. That alone saves 10 minutes per session.

---

## Use Case 2 — Solo Consultant / Coach

**The problem:** Juggling 6 clients, no EA, living in the inbox. Every session with a client ends with commitments they need to track. Notes exist in 4 different places.

**Setup:** Names the ops captain "Morgan." Loads each active client as a folder in `Ops/clients/`. One markdown file per client with context, history, and open items.

**Day to day:** End of a client call, opens Cowork. *"Morgan, I just finished a session with [client]. Here's what was agreed: [bullets]. Update their file and add the follow-up tasks."* Two minutes. Done. Nothing lost.

**Between clients:** *"Morgan, what do I need to prepare for tomorrow's Acme call?"* Morgan reads the client file, the last session notes, the open tasks. Returns a briefing. The owner walks into the call prepared.

**Business development:** *"Morgan, I've got a prospect call on Friday. They're a 20-person SaaS company, Series A, struggling with churn. What angles should I lead with?"* Morgan knows their pricing, their methodology, their case studies (from `Memory/`). It's a real prep session, not a generic ChatGPT response.

**The honest limitation:** Morgan doesn't send emails, book meetings, or follow up automatically. That's the n8n layer. But Morgan remembers everything and helps the owner think clearly, and that's often more valuable.

---

## Use Case 3 — Small Agency (2–5 people)

**The problem:** Context lives in people's heads. When someone's off sick, work stops. New hires take months to get up to speed. Decisions made in Slack conversations never get written down.

**Setup:** Shared `shine-os` folder on a shared drive (or each person has their own — both work). The ops captain handles project strategy. The support agent handles client issues. Session reports become the institutional memory.

**Day to day:** Every piece of meaningful work generates a session report. Not because it's mandated, but because the reports make the next session 10 minutes shorter. After a month, there are 40 reports in `Reports/`. That's the company's memory.

**New hire joins:** Read the last 2 weeks of session reports. You're up to speed on every active project, every open decision, every client issue. No handover meeting needed.

**Client decisions:** *"The client wants to change the scope. What did we agree in the brief?"* The ops captain searches the reports. Finds the exact decision, the date, the context. The agency owner goes into the call with receipts.

**The key insight for agencies:** The value compounds. Month 1 it's useful. Month 6 it's indispensable.

---

## Use Case 4 — Property Manager / Landlord

**The problem:** Multiple properties, multiple tenants, maintenance issues that fall through the cracks. Disputes about what was agreed and when.

**Setup:** One subfolder per property in `Ops/properties/`. Each contains: tenant details, outstanding issues, maintenance log, lease dates. The task manager handles scheduled follow-ups.

**Day to day:** Tenant calls about a boiler issue. Opens Cowork. *"Log this: Property 3, boiler fault reported, tenant [name], 28 March. Assign follow-up task: confirm engineer booked within 48 hours."* Task logged, follow-up set.

**Dispute prevention:** Everything's written down with timestamps. When a tenant claims they reported a problem 3 months ago, the session reports show exactly when it was first logged and what was done.

**Renewals:** *"Which leases are coming up in the next 90 days?"* The ops captain checks the property files. Returns a list with lease end dates and current rents. The landlord sends renewal letters before the window closes.

**With Supabase:** Maintenance costs tracked per property. Annual summary generated in one session. Tax prep takes an hour instead of a weekend.

---

## Use Case 5 — Service Business with a Team (Cleaning, Care, Delivery)

**The problem:** Founder is the bottleneck. Every operational decision flows through them. Enquiries pile up. Complaints land in their personal inbox.

**Setup:** Full squad deployed — service advisor handles quotes, receptionist triages inbound, support agent handles complaints. Ops captain runs the daily briefing.

**Morning routine:** Opens Cowork. *"Morning briefing."* Ops captain summarises: 3 new enquiries (2 already quoted by the service advisor), 1 complaint (already triaged by support agent, pending founder approval on resolution), 4 tasks due today. The founder touches the things that actually need them.

**Quoting:** Customer emails asking for a price. The founder forwards it to Cowork. Service advisor generates a quote in their voice, using their pricing, with their standard terms. Founder reviews, sends. 3 minutes instead of 15.

**Scaling:** When the business grows and they hire someone, that person uses the same system. The squad is already documented. The session reports show how decisions get made. Training time drops significantly.

---

## What the Day-to-Day Actually Looks Like

**Without n8n (Cowork only):**

You are still the trigger. Nothing happens while you're not there. But when you open Cowork, you open it to a system that knows your business, remembers what you were working on, and has a named team ready to work. Sessions are faster, nothing falls through the cracks, and your AI stops feeling like a chat window and starts feeling like an ops system.

**With n8n added:**

Things happen while you sleep. New enquiry comes in at 2am — your service advisor drafts the response by morning. Follow-up due in 3 days — your task manager sends it automatically. You open Cowork to review and approve, not to execute.

**With Supabase added:**

Your data persists properly. Leads, customers, tasks, and session history live in a real database. Your ops captain can query it. *"How many leads did we get last month?"* is a real question with a real answer.

**With Retell added:**

Your service advisor picks up the phone. A prospect calls your number at 6pm on a Friday. They speak to your service advisor — warm, knowledgeable, on-brand — and get a quote. You see the call summary in Cowork on Monday morning.

---

## The Honest Pitch

SHINE OS is not magic. It's structure. The value is in having one place where your business context lives, one discipline for how sessions work, and a named squad that knows your business instead of starting blank every time.

Most AI tools give you power without organisation. SHINE OS gives you both.

*Built by David Caldicott · hello@shineon.world · shineon.world*
