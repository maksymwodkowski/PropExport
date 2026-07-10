# PropExport List Builder — User Flows
**ORIL · March 2026 · CONFIDENTIAL**

---

## UF-01 — Search → Filter → Count → Export

**Trigger:** User logs in and needs a new list
**Personas:** P1, P2, P3, P4

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Enter location (zip / state / county) | Scope locked to geography |
| 2 | Select QuickList template or apply custom filters | Filters populate |
| 3 | Adjust filter criteria | Live count updates in real time (take=0) |
| 4 | Apply suppression (optional) | Live count updates to net-new total |
| 5 | View estimated cost (count × per-record rate) | Cost shown before CTA |
| 6 | Click Download → confirm | Job submitted via Async API |
| 7 | See status: Pending → Processing → Ready | In-app status indicator |
| 8 | Click Export CSV | File downloads |

**Failure states:**
- Count returns 0 → explain why (no results for filter combo)
- Insufficient credits → clear error + contact PropExport CTA
- Async job fails → Failed status in order history + error message

---

## UF-02 — Admin Setup & Token Config

**Trigger:** Admin receives credentials from PropExport, logs in for first time
**Personas:** P5

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Admin receives credentials via email | — |
| 2 | Logs in → lands on empty dashboard | Prompt to complete setup |
| 3 | Navigates to Settings → API Token | Token input screen |
| 4 | Enters token provided by PropExport | Immediate validation |
| 5 | System confirms token is valid | Shows active datasets + pricing |
| 6 | Platform unlocked for full use | — |

**Failure states:**
- Invalid token → clear error ("Token not recognised — contact PropExport")
- Token entered but datasets not loading → show which datasets failed

---

## UF-03 — Invite & Revoke Users

**Trigger:** Admin wants to add or remove a team member
**Personas:** P5

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Navigate to Users section | List of current users |
| 2 | Enter email → Send Invite | Email sent with login credentials |
| 3 | User appears in list as Invited | — |
| 4 | User logs in → status becomes Active | — |
| 5 | Admin revokes a user | Session invalidated immediately |
| 6 | Confirmation shown | "User can no longer log in" |

**Failure states:**
- Invalid email format → inline validation error
- Invite email bounces → show failed status in user list

---

## UF-04 — Suppress Past Orders → New Pull

**Trigger:** User wants to avoid re-pulling records from a previous list
**Personas:** P1, P3

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Filters applied, count visible | — |
| 2 | Open Suppression panel | Past orders list (filterable by tag / date) |
| 3 | Select one or more orders to suppress | Live count updates to net-new total |
| 4 | Confirmation shown | "X records suppressed" |
| 5 | Proceed to download | Job submitted with suppression applied |

**Failure states:**
- No past orders available → empty state with explanation
- Suppression reduces count to 0 → warn user before download CTA

---

## UF-05 — Import External CSV as Suppression

**Trigger:** User has records from outside the platform they want to exclude
**Personas:** P1, P3

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Open Suppression panel | Option to import external CSV |
| 2 | Upload CSV file | System parses and validates |
| 3 | Records added to suppression pool | Live count updates |
| 4 | Proceed to build list | Imported records excluded |

**Failure states:**
- Wrong file format → clear error ("CSV files only")
- File too large / malformed → error with guidance

---

## UF-06 — View Order History & Re-export

**Trigger:** User wants to review or re-download a past list
**Personas:** P1, P2, P3, P4

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Navigate to Orders | List of past orders (date, filter summary, count, tag, status) |
| 2 | Find order | Filter/search by tag or date |
| 3 | Click Re-export | CSV downloads again |
| 4 | Optionally use order as suppression | Redirects to List Builder with order pre-selected in suppression |

**Failure states:**
- Order file no longer available → show error + contact support CTA

---

## UF-07 — Async Job → Pending → Ready → Download

**Trigger:** Large list submitted (all exports go async)
**Personas:** P1, P2, P3, P4

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | Download confirmed | Job submitted → status: Pending |
| 2 | User navigates away | Status persists — visible from any screen |
| 3 | Job processes | Status: Processing |
| 4 | Job completes | Status: Ready + in-app notification |
| 5 | User clicks Export CSV | File downloads |

**Failure states:**
- Job stuck in Processing → timeout message + retry option
- Job fails → Failed status + clear error message

---

## UF-08 — Failed Order (No Credits)

**Trigger:** User attempts download but account has insufficient credits
**Personas:** P1, P2, P3, P4

| Step | Action | System Response |
|------|--------|-----------------|
| 1 | User confirms download | API returns insufficient credits error |
| 2 | — | Clear error message shown |
| 3 | — | CTA: "Contact PropExport to top up your account" |
| 4 | Failed order logged | Appears in Order History with "Failed" status |

**Failure states:**
- Error message unclear → user doesn't know what to do next (design must avoid this)

---

*User flows complete · ORIL · March 2026*
