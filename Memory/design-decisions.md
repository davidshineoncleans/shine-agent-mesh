# SHINE OS — Design Decisions & Context

Parent: [[CLAUDE]]
Related: [[TASKS]] · [[LIMITATIONS]] · [[USE_CASES]]

> This file records the key design decisions made during the creation of SHINE OS,
> with the reasoning behind each. New sessions working on this repo should read this first.

---

## Origin

SHINE OS was extracted from the SHINE Agent Mesh — a live AI operating system built by David Caldicott for Shine On Cleans, a UK cleaning service. The full SHINE system includes n8n workflow automation, Supabase data layer, and Retell voice agents. SHINE OS is the Claude Cowork layer of that system, genericised for public release.

The decision to release: the methodology (named agents, session conventions, task tracking, knowledge graph) is valuable even without the automation stack. Other founders need this. The automation layer can follow.

Contact: David Caldicott · hello@shineon.world · shineon.world

---

## Key Decisions

### 1. Name: SHINE OS (not "SHINE Agent Mesh")

**Decision:** The public repo is called SHINE OS, not SHINE Agent Mesh.

**Reason:** "Agent Mesh" refers specifically to the n8n automation layer (the network of workflows that dispatch between agents). That layer is not included in this release. Calling it "Agent Mesh" would mislead users into thinking they're getting the automation system. "SHINE OS" correctly describes what this is: an operating system for running your business with AI. The full Agent Mesh is a future release.

---

### 2. Include n8n + Supabase in the vision from day one

**Decision:** SHINE OS documents the full three-layer stack (Cowork + Supabase + n8n + Retell) even though only the Cowork layer ships now.

**Reason:** The watered-down version is a weaker product. Users should understand what they're building toward and set up with the full architecture in mind. `Setup/02_ADD_YOUR_STACK.md` documents the stack layers. The README is explicit about what each layer adds.

**Contra-argument considered:** "Only document what ships" — rejected. Users need to understand the full picture to make an informed install decision, and the no-stack version is more compelling when you can see what it grows into.

---

### 3. License: CC0 1.0 Universal (Public Domain)

**Decision:** CC0. No attribution required by law.

**Reason:** Maximum adoption. Legal attribution requirements create friction. The contact line in `CLAUDE.md` ensures David's name and contact are present in every running install as a social norm and practical embedding — every Claude session running SHINE OS will have `hello@shineon.world` in context. This is more durable than a legal attribution clause.

**Note:** CC0 means David cannot take legal action if someone strips his name and republishes as their own. This is an accepted trade-off for the broadest possible reach.

---

### 4. One folder, no Cowork Projects

**Decision:** SHINE OS assumes everything lives in a single selected folder. Cowork Projects (Anthropic's separate context feature) are not used.

**Reason:** Cowork Projects add complexity that new users don't need. The single-folder model is simpler to explain, simpler to set up, and covers the vast majority of use cases (one person, one business). Multi-project or multi-client scenarios can be handled by running multiple installs or by future versions of SHINE OS.

**Known limitation:** This should be documented clearly. See `LIMITATIONS.md`.

---

### 5. The setup wizard (/shine-setup) is the core product

**Decision:** The `shine-setup` skill is the primary differentiator, not the folder structure.

**Reason:** Anyone can clone a folder structure. The setup wizard — which asks 10 questions and customises everything for the user's specific business — is what makes this feel like a product rather than a template dump. It names the agents, fills in the glossary, sets up the first tasks, and ends with an offer to run the first real session. That first session experience is what converts users from "interesting" to "this actually works."

---

### 6. n8n Onboarding Agent (planned, not yet built)

**Decision:** The full onboarding vision is: user hits a landing page, submits a form, an n8n workflow provisions their Supabase tables, imports starter workflows, generates their custom CLAUDE.md, and emails them a setup package with a control panel app.

**Status:** Not yet built. The current setup wizard does the customisation locally. The n8n onboarding adds automated provisioning.

**Why it matters:** This moves SHINE OS from "developer-adjacent" to genuinely accessible. A non-technical founder should be able to go from landing page to running system without editing a single file.

**Next session prompt:** See `Dev/NEXT_SESSION_PROMPT.md`.

---

### 7. Control Panel App

**Decision:** Include a self-contained HTML control panel in the setup package.

**Reason:** Users need a visual anchor. A dashboard that shows their active agents, stack status, feature request form, and link to docs makes SHINE OS feel like a real product. Built as a self-contained HTML file initially — no hosting required, lives in the workspace folder, opens in a browser.

**Status:** Not yet built. Planned as part of the n8n onboarding session.

---

### 8. TikTok as primary distribution channel

**Decision:** First marketing push via short TikTok videos, positioned as "free, no catch."

**Reason:** The target audience (SMB founders, tradespeople, solo operators) is on TikTok. The hook is authentic: David built this for his own business, it works, he's giving it away. The "tell us if you improve it" call to action builds community without being transactional.

**Honest framing agreed:** *"This is the thinking layer, not the automation layer."* Don't overpromise.

---

### 9. What the repo is NOT selling

**Key distinction:** This is not selling SHINE On Cleans methodology. The cleaning business specifics (pricing, Bark lead pipeline, specific agent prompts) are all stripped. What's released is the general operating model: the session conventions, the agent structure, the task tracking discipline, the knowledge graph approach.

The full SHINE Agent Mesh (with SOC-specific workflows, Retell agents, email sequences) is a separate future commercial product.

---

## Open Questions

- **Should the repo be called `shine-os` or `shineon`?** Current decision: `shine-agent-mesh` on GitHub, SHINE OS as the product name. Revisit.
- **One-click plugin install:** When is this ready to build? The `create-cowork-plugin` skill exists. Priority question.
- **Control panel design:** What does the first version look like? HTML file or Lovable-hosted?
- **Pricing for paid tiers:** What does "SHINE Pro" look like? Automated onboarding + support + commercial workflows?
