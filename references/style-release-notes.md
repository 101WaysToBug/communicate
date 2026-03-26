# Communication Style: Release Notes

## Purpose
Clear, structured announcement of what changed in a release — aimed at users, stakeholders, or the broader team so they can quickly understand new capabilities, improvements, and the motivation behind them.

## Format Rules
- **Length:** As long as needed (typically 200-500 words)
- **Tone:** Informative, neutral, slightly celebratory for big features
- **Structure — use these four sections:**
  1. **What is the name of the feature?** — Clear, recognizable feature name as the heading
  2. **What's changing and why?** — Describe the previous behavior or gap, then explain what's now different and the motivation behind the change
  3. **Who is this for?** — Target audience: end users, admins, sales teams, specific segments, etc.
  4. **How it works** — Step-by-step or bullet-point breakdown of the feature's behavior, toggles, settings, and key details
- **Include:** Feature names, brief context on value, specific behavioral details
- **Avoid:** Internal jargon, implementation details, commit-level granularity, overly technical language
- **Focus:** What the user/stakeholder gains from the change

## Example

**Input:** We shipped contact owner-based routing — when enabled via an admin toggle, inbound messages and calls route back to the contact's owning agent before any automation kicks in. Owner and assignee stay in sync automatically.

**Output:**

## 1. Feature Name
**Contact Owner-Based Routing (Operator Scoping)**

## 2. What's Changing and Why?
Previously, automations and round-robin assignment could override an agent's ownership of a contact — meaning a salesperson's established lead might get routed to someone else when they message back.

Now, when enabled, **contact owner-first routing** ensures that inbound messages and calls are always routed back to the contact's owning agent before any automation or default assignment kicks in. This protects sales territory, maintains relationship continuity, and prevents automations from overriding explicit owner/assignee decisions.

## 3. Who Is This For?
- **Sales teams** who rely on dedicated contact ownership and territory protection
- **Admins** who want control over routing priority via a simple ON/OFF toggle
- **Any team using automations or round-robin** that needs to preserve agent-contact relationships

## 4. How It Works
- A new admin toggle — **Contact owner-based routing** (ON/OFF) — controls the behavior
- When **ON**, routing follows this priority:
  1. **Active conversation with a human assignee** — messages/calls continue routing to that assignee
  2. **Closed conversation, reopened by inbound message/call** — routes to the existing assignee (and syncs contact owner), or falls back to the contact owner
  3. **No owner or assignee** — falls through to automation rules, then default assignment
- **Owner and assignee stay in sync** — changing one automatically updates the other
- Automations and round-robin **will not override** the contact owner/assignee when the toggle is enabled
- When **OFF**, routing works exactly as before
