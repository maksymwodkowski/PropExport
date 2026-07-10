# UX Research Skill
**ORIL · Reusable Process · CONFIDENTIAL**

---

## 1. Why This Exists
A reusable research process for projects where no real users are available. Uses Synthetic User Interviews — AI personas based on PRD assumptions — to surface UX risks before design starts.

---

## 2. Personas

Define personas from the PRD. For each, capture:

| ID | Who | Volume/Frequency | Biggest Pain Today |
|----|-----|------------------|--------------------|
| P1 | ... | ... | ... |

---

## 3. Business Model Review

**Run this before anything else — before personas, before interviews, before flows.**

Read the PRD and first understand how the business actually works — not just what the product does, but how value is created, delivered, and paid for. Then derive from that what it means for UX. This is a two-step read: first understand the model, then translate it into explicit rules.

**Step 1 — Understand the business model:**
- What does the company sell, and to whom?
- What does the user actually pay for — and at what moment does that transaction happen?
- What is the flow of value: what does the user do, what does the system do, what does the user get back?

**Step 2 — Derive UX rules from that model:**
- Is there anything a user must not see before a specific action or payment?
- Is any content or feature limited by role, plan, token, or prior action?
- What happens if a user tries to reach something they haven't unlocked yet?

**Output:** A short list of explicit rules. Write them as cause and effect — not just "no preview" but why:

> *"Users pay per record downloaded. Therefore: no actual records are shown before purchase. Pre-download, users see only count and cost estimate. Records are only accessible after a completed async job via CSV export."*

These rules must be carried explicitly into User Flows and the Wireframe Brief. The PRD may imply them clearly enough — but if they are not written down as rules here, they will not survive the handoff to design.

---

## 4. Synthetic Interview — Question Script

Adapt per project. Standard phases:

**Phase 1 — Their World**
1. Walk me through your day. Where does this product fit in?
2. What tools do you use today? What frustrates you most?
3. Last time you did this task — how long did it take from need to result?

**Phase 2 — Pain Points**
4. Tell me about a time this process cost you time or money.
5. What do you do today to avoid duplicating work?
6. How do you decide what criteria to apply? What do you wish you had?

**Phase 3 — Core Flow Reactions**
7. You open the platform — what's the first thing you do?
8. What's your comfort zone for output size / volume?
9. What do you need to know before you commit to an action?
10. After the output lands — what happens in the next 30 minutes?

**Phase 4 — Edge Cases & Recovery**
11. What does "never making the same mistake twice" look like for you practically?
12. Do you ever go back to past outputs? What for?
13. You have data from outside this platform. How do you want to use it here?

**Phase 5 — Admin Only (if applicable)**
14. First thing you configure on a new platform?
15. How do you handle a teammate locked out today?
16. Someone on your team made a large accidental action. Do you want to know?

---

## 5. User Flows to Map

For each flow, answer before wireframing:
- What triggers this flow?
- What decisions does the user make mid-flow?
- What does a failure state look like?
- Does any business rule from Section 3 affect what the user can see or do in this flow? If yes — write it explicitly in the flow description, not just in Section 3.

---

## 5a. Single Experience Audit

After all individual flows are mapped, run this before moving to IA or wireframing.

**Goal:** Identify which flows share a screen or moment — and design those touchpoints together, not as separate deliverables.

**How to run it:**
Narrate the full session as a single user, start to finish, per persona. If the narration feels unbroken, the flows are coherent. If you mentally switch gears mid-sentence, that's a seam.

**Questions to answer:**
- Which flows land on the same screen simultaneously? Those need a unified wireframe brief.
- Are there flows that hand off to another without a clear transition designed?

**Output:** A short list of seams — moments where two flows meet on a single screen — to be called out explicitly in the wireframe brief.

---

## 6. Open Questions — Must Resolve Before Design

Log any question where the answer changes what gets designed. Standard questions to always consider:

| # | Question | Owner |
|---|----------|-------|
| Q1 | Does any data update in real time, or is it static until a user action? | Tech / client |
| Q2 | What triggers notifications — in-app only, or email too? | Client |
| Q3 | What does the API return on key error states? | Tech |
| Q4 | Is the platform fully usable before initial setup is complete? | Client + Tech |
| Q5 | What fields from the data provider are actually queryable and exposable as filters? | Data provider |

---

## 7. Wireframe Brief Rules

When writing the wireframe brief — whether for Claude, Figma Make, or any other tool — apply these rules:

**Business constraints first.** Every brief must open with the constraints extracted in Section 3. The tool generating the wireframe must know what users cannot see before it decides what to show.

**Complex interaction patterns — always describe behaviour, not just components.** If a screen involves a non-obvious interaction — a count that updates from multiple sources simultaneously, a panel with two modes, a status that persists across navigation — write a short note explaining how it is supposed to behave. Not what components go on screen, but what happens when the user interacts. Without this, the designer or AI tool makes its own structural decision, and it will likely be wrong.

**Empty states — only where genuinely ambiguous.** If leaving a screen blank or letting a tool default would cause confusion or show something that shouldn't be there yet — define what the user sees before they have done anything. Not every screen needs this. A profile page, a settings form, a simple modal — these are self-evident. But any screen where the first-time state is non-obvious, or where showing the wrong default would break business logic, needs it written down explicitly.

**Do not let the tool fill empty states by default.** Any content visible before user interaction must be explicitly justified in the brief. If it is not written down, it should not appear on screen. AI design tools will pattern-match to common SaaS defaults — which may look reasonable but are not grounded in the actual product logic.

---

*UX Research Skill · ORIL · Reusable*
