# PropExport List Builder — Project Context

**Client:** PropExport  
**Agency:** ORIL  
**Project:** List Builder web app (self-service B2B data platform)  
**Status:** UX Research complete → moving into design

---

## What This Product Is

PropExport List Builder is a self-service platform for pulling targeted contact/property records. Users search, filter, and download large lists (up to 1M+ records) as CSV exports. The product replaces a manual, 24–48hr delivery process. Downloads are async jobs paid per record.

**Critical business rule:** Users pay per record downloaded. No actual records are shown before purchase. Pre-download, users see only count and cost estimate. Records are only accessible after a completed async job via CSV export.

---

## Project Files

All project context lives in `PropExport_Project_Files/`. Read these before working on any task:

| File | What it is |
|------|-----------|
| `ORIL_UX_Research_Skill.md` | Reusable UX research process used on this project — how synthetic interviews work, wireframe brief rules, business model review process |
| `ORIL_Document_Style_Guide.md` | ORIL brand style guide — use for all document output (fonts, colors, table styling, cover page, Google Apps Script format) |
| `PropExport_UX_Research_Plan_v3.md` | Research plan with 5 personas, interview scripts, user flows list, open questions, timeline |
| `PropExport_Synthetic_Interviews.md` | Completed synthetic interview results for all 5 personas |
| `PropExport_Competitor_Research_Report.md` | Competitor research findings |
| `PropExport_IA.md` | Information architecture — navigation structure, screen hierarchy, two roles (Regular User / Admin) |
| `PropExport_User_Flows.md` | User flows UF-01 to UF-08 with triggers, decisions, failure states |
| `PropExport_Design_Handoff.md` | Design handoff — screen inventory (S-01 to S-16+), wireframe briefs per screen, business constraints |
| `PropExport_Open_Questions.md` | Open questions log (Q1–Q5) — check before making design decisions |
| `PropExport_MVP_PRD_docx.pdf` | Product requirements document |
| `PropExport_MVP_Backlog_docx.pdf` | MVP backlog |
| `SKILL_FigmaJam_IA_Prompt.md` | Skill for generating IA diagrams in FigJam |

---

## Personas

| ID | Who | Volume/Month |
|----|-----|--------------|
| P1 | Call Center Ops Manager | 1M+ records |
| P2 | Mortgage Lead Manager | 10–50k records |
| P3 | Real Estate Investor | 2–20k records |
| P4 | Solar Operator | 50–200k records |
| P5 | Platform Admin | — |

---

## Key Screens

S-01 Login · S-02 List Builder · S-03 Download Confirmation · S-04 Async Job Status · S-05 Order History · S-06 Order Detail · S-07 Suppression Panel · S-08 Import CSV · S-09 Settings API Token · S-10 Settings Users · S-11 Invite User · S-12 Revoke User · S-13–S-16 Empty/Error states

---

## How to Work on This Project

- **Before any design decision** — check `PropExport_Open_Questions.md` to see if the question is already logged
- **Before wireframing** — read `PropExport_Design_Handoff.md` for screen briefs and business constraints
- **For document output** — follow `ORIL_Document_Style_Guide.md` exactly (generate as Google Apps Script)
- **For UX research tasks** — follow the process in `ORIL_UX_Research_Skill.md`
- **Business rule always applies** — never show records before purchase/async job completion
