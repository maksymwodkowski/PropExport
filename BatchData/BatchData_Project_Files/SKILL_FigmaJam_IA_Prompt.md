---
name: figma-jam-ia-prompt
description: Use this skill whenever the user asks to create a Figma Jam prompt for an information architecture diagram. Triggers include any mention of "Figma Jam IA", "IA prompt", "information architecture prompt", or "site map prompt". Do NOT use for user flow diagrams, user journey diagrams, flow prompts, or any diagram that involves steps, decisions, or sequences — those are a different diagram type with different rules.
---

# Figma Jam — Information Architecture Prompt

## When to use this skill

Use when the user wants a **Figma Jam prompt for an IA** — a static tree showing what screens and sections exist and how they are nested. No steps, no process, no decisions.

## When NOT to use this skill

Do not use for:
- User flow diagrams — steps a user takes to complete a task
- User journey diagrams — emotions and touchpoints over time
- Wireframe prompts
- Any diagram involving arrows between siblings, decision points, or sequences

For user flows, use a separate approach: instruction line + left-to-right steps with decision diamonds. Rules are different.

---

## What this skill produces

A ready-to-paste plain text prompt for Figma Jam's AI that generates a standard UX information architecture diagram: rectangular nodes, text labels only, top-down tree layout.

## Process

### Step 1 — Collect the structure

Ask the user for the platform name and screen/section list if not already provided. You need:
- Platform name (root node)
- Top-level sections
- Screens under each section
- Any nested child screens or UI elements

### Step 2 — Build the tree

Format the content as a plain ASCII tree using these characters only: `│`, `├──`, `└──`. One node per line. No parenthetical notes, no role labels, no annotations inside node names.

```
[Platform name]
├── [Section]
│   └── [Screen]
├── [Section]
│   ├── [Screen]
│   │   └── [Child screen]
│   │       ├── [Element]
│   │       └── [Element]
│   └── [Screen]
└── [Section]
    ├── [Screen]
    └── [Screen]
```

### Step 3 — Prepend the instruction line

Always open with this exact instruction line, before the tree:

```
Standard UX information architecture diagram. Simple rectangular nodes with text labels only. No icons, no badges, no colors, no roles, no annotations. Parent-to-child connections only. No arrows between siblings.
```

### Step 4 — Output

Deliver the full prompt inside a copyable code block or copy-button widget. Do not add any explanation inside the prompt itself — the instruction line and the tree are the entire output.

---

## Rules

- **Instruction line is mandatory** — it prevents Figma Jam from adding icons, colors, badges, and role annotations
- **Plain hyphens only** — use `-` not `—` (em dash breaks some parsers)
- **No arrows on connectors** — parent-to-child lines only, no flow arrows between siblings
- **No floating nodes** — every node must be attached to the tree
- **No labels on connectors** — if a redirect or cross-link is needed, omit it; the IA tree is not a flow
- **Short node names** — one line of text per node, no sub-labels or parenthetical notes
- **No visual rules in the prompt** — do not add color instructions, size instructions, or badge instructions; they cause Figma Jam to add unwanted decoration

---

## Full example output (BatchData List Builder)

```
Standard UX information architecture diagram. Simple rectangular nodes with text labels only. No icons, no badges, no colors, no roles, no annotations. Parent-to-child connections only. No arrows between siblings.

BatchData List Builder
├── Auth
│   └── Login
├── List Builder
│   ├── Location input
│   ├── QuickList templates
│   ├── Filter panel
│   │   └── Live count + cost estimate
│   ├── Suppression panel
│   │   ├── Select past orders
│   │   └── Import external CSV
│   └── Download confirmation modal
├── Orders
│   ├── Order history
│   │   └── Order detail
│   │       ├── Re-export CSV
│   │       └── Use as suppression
│   └── Empty state
├── Settings
│   ├── API Token
│   │   ├── Token input + validation
│   │   ├── Active datasets + pricing confirmation
│   │   └── Error - invalid token
│   └── Users
│       ├── User list
│       │   ├── Active
│       │   ├── Invited
│       │   └── Revoked
│       ├── Invite user modal
│       └── Revoke user confirmation
└── Error states
    ├── Error - failed job
    ├── Error - insufficient credits
    ├── Error - invalid token
    └── Empty state - no orders
```
