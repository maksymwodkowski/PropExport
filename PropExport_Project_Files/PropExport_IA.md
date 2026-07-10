# PropExport List Builder — Information Architecture
**ORIL · March 2026 · CONFIDENTIAL**

---

## 1. Navigation Structure

Two roles, two navigation contexts.

### Regular User
| # | Section | Purpose |
|---|---------|---------|
| 1 | List Builder | Search, filter, suppress, download |
| 2 | Orders | View history, re-export, use as suppression |
| 3 | Profile | Logout |

### Admin User
| # | Section | Purpose |
|---|---------|---------|
| 1 | List Builder | Same as regular user |
| 2 | Orders | Same as regular user |
| 3 | Settings → API Token | Configure PropExport token |
| 4 | Settings → Users | Invite, revoke, manage team |
| 5 | Profile | Logout |

---

## 2. Screen Hierarchy

### Auth
- Login
- Password reset (admin-triggered only)

### List Builder
- List Builder (main screen)
  - Location input
  - QuickList templates
  - Filter panel
  - Live count + cost estimate
  - Suppression panel
    - Select past orders
    - Import external CSV
  - Download confirmation modal
  - Async job status banner (persistent, all screens)

### Orders
- Order History (list view)
  - Filter by tag / date / status
  - Order detail (metadata: date, filters, count, tag, status)
  - Re-export CSV
  - Use as suppression (redirects to List Builder)

### Settings (Admin only)
- API Token
  - Token input + validation
  - Active datasets + pricing confirmation
- Users
  - User list (Active / Invited / Revoked)
  - Invite user (email input)
  - Revoke user (confirmation)

### States (apply across all screens)
- Empty state (no orders, no results, no users)
- Loading state (live count updating)
- Error state (invalid token, failed job, insufficient credits)
- Success state (invite sent, token valid, export ready)

---

## 3. Screen Inventory

| ID | Screen | Role | Flow |
|----|--------|------|------|
| S-01 | Login | All | — |
| S-02 | List Builder | All | UF-01 |
| S-03 | Download Confirmation Modal | All | UF-01 |
| S-04 | Async Job Status Banner | All | UF-07 |
| S-05 | Order History | All | UF-06 |
| S-06 | Order Detail | All | UF-06 |
| S-07 | Suppression Panel | All | UF-04, UF-05 |
| S-08 | Import CSV Modal | All | UF-05 |
| S-09 | Settings — API Token | Admin | UF-02 |
| S-10 | Settings — Users | Admin | UF-03 |
| S-11 | Invite User Modal | Admin | UF-03 |
| S-12 | Revoke User Confirmation | Admin | UF-03 |
| S-13 | Empty State — No Orders | All | UF-06 |
| S-14 | Error State — Failed Job | All | UF-07 |
| S-15 | Error State — Insufficient Credits | All | UF-08 |
| S-16 | Error State — Invalid Token | Admin | UF-02 |

---

## 4. Key Design Decisions

| Decision | Rationale |
|----------|-----------|
| Async job status is a persistent banner, not a page | P1 and P4 navigate away while jobs run — status must follow them |
| Suppression is a panel inside List Builder, not a separate screen | Keeps suppress → count → download in one flow without navigation breaks |
| Cost estimate lives on List Builder, not only on confirm modal | P1, P2, P3, P4 all need cost before committing — showing it only at confirm is too late |
| Admin settings behind a Settings section, not mixed with List Builder | Keeps regular user experience clean — admins access config separately |
| QuickList templates are the default entry point, filters are secondary | P2 and P4 need guided starting points — raw filters are for P3 power users |

---

*IA complete · ORIL · March 2026*
