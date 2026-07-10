# BatchData List Builder — Design Handoff
**ORIL · March 2026 · CONFIDENTIAL**

---

## 1. What This Is
Single source of truth for the designer. Everything needed to start wireframing — no need to read all previous research docs.

---

## 2. Screen Inventory

| ID | Screen | Role | Priority | Flow | Open Questions |
|----|--------|------|----------|------|----------------|
| S-01 | Login | All | P1 | — | — |
| S-02 | List Builder | All | P1 | UF-01 | Q1, Q2 |
| S-03 | Download Confirmation Modal | All | P1 | UF-01 | Q1 |
| S-04 | Async Job Status Banner | All | P1 | UF-07 | Q3 |
| S-05 | Order History | All | P1 | UF-06 | — |
| S-06 | Order Detail | All | P2 | UF-06 | — |
| S-07 | Suppression Panel | All | P1 | UF-04, UF-05 | Q2 |
| S-08 | Import CSV Modal | All | P2 | UF-05 | — |
| S-09 | Settings — API Token | Admin | P1 | UF-02 | Q5 |
| S-10 | Settings — Users | Admin | P1 | UF-03 | — |
| S-11 | Invite User Modal | Admin | P1 | UF-03 | — |
| S-12 | Revoke User Confirmation | Admin | P1 | UF-03 | — |
| S-13 | Empty State — No Orders | All | P1 | UF-06 | — |
| S-14 | Error State — Failed Job | All | P1 | UF-07 | — |
| S-15 | Error State — Insufficient Credits | All | P1 | UF-08 | Q4 |
| S-16 | Error State — Invalid Token | Admin | P1 | UF-02 | — |

---

## 3. Wireframe Brief — By Flow

### UF-01 — List Builder (S-02, S-03)
The core screen. Entry point is location search at the top. Below it: QuickList templates as the default starting point (cards or chips), with an option to switch to custom filters. Filter panel sits to the left or in a collapsible panel. Live count + cost estimate are always visible — pinned, not buried. Suppression panel accessible inline (not a separate page). Download CTA is prominent but secondary to the count/cost display. Confirmation modal shows cost one final time before job is submitted.
- **Q1 pending** — cost estimate placement may shift depending on BatchData answer
- **Q2 pending** — suppression count update behaviour TBC

### UF-02 — Admin Token Setup (S-09)
First-run screen for admins. Simple, focused layout — token input field, save button, immediate validation feedback. On success: show a confirmation panel listing active datasets and per-record pricing. On failure: clear inline error with BatchData contact info. Platform should prompt admin to complete this step if token is not yet configured.
- **Q5 pending** — whether List Builder is accessible before token setup affects empty state design

### UF-03 — User Management (S-10, S-11, S-12)
User list screen with three status tabs or filters: Active / Invited / Revoked. Invite flow is a simple modal — email input only for MVP. Revoke is a confirmation modal with explicit feedback. No complex role management for MVP.

### UF-04 / UF-05 — Suppression Panel (S-07, S-08)
Panel lives inside List Builder — not a separate screen. Two modes: select from past orders (filterable by tag and date), or upload external CSV. Selecting an order or uploading a file immediately updates the live count. Show "X records suppressed" as inline feedback. Warn the user if suppression reduces count to zero before they can proceed to download.
- **Q2 pending** — confirm live count updates in real time on suppression change

### UF-06 — Order History (S-05, S-06, S-13)
List view showing past orders: date, filter summary, record count, tag, status. Filterable by tag and date. Each order has two actions: Re-export CSV and Use as Suppression. Empty state (S-13) should explain what will appear here and encourage the user to build their first list.

### UF-07 — Async Job Status (S-04)
Persistent banner — visible on every screen after a job is submitted. Not a page, not a modal. Shows: job name/tag, status (Pending / Processing / Ready), timestamp. On Ready: surface a prominent Export CSV action inline in the banner. On failure: show error with retry option.
- **Q3 pending** — email notification scope TBC

### UF-08 — Failed Order (S-15)
Error state shown when download fails due to insufficient credits. Clear message explaining what happened. Single CTA: "Contact BatchData to top up your account." Failed order still appears in Order History with Failed status.
- **Q4 pending** — exact API error message TBC

---

## 4. Key Design Constraints

| Constraint | Detail |
|------------|--------|
| Cost estimate | Must be visible before Download CTA — non-negotiable across all personas |
| Suppression count | Must visibly update when suppression is applied — P1 and P3 need proof it works |
| Async banner | Must persist across all screens — P1 and P4 navigate away while jobs run |
| QuickLists first | Templates are the default entry point — raw filters are secondary |
| Plain language | Filter labels must avoid real estate jargon — P2 and P4 are non-RE personas |
| Admin setup | Token config and user invite are the two highest-stakes admin moments — must be polished |

---

## 5. Open Questions Blocking Wireframes

| # | Blocks | Question | Owner |
|---|--------|----------|-------|
| Q1 | S-02, S-03 | Cost estimate during filtering or only at confirm? | Sean |
| Q2 | S-02, S-07 | Does suppression update live count in real time? | Joseph |
| Q3 | S-04 | In-app only or email notification when job is ready? | Sean |
| Q4 | S-15 | Exact API error on insufficient credits? | Joseph |
| Q5 | S-09 | Platform locked before token is configured? | ORIL + BatchData |

---

*Design handoff complete · ORIL · March 2026*
