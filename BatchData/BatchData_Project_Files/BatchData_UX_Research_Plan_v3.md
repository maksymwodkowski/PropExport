# BatchData List Builder — UX Research Plan
**ORIL · March 2026 · CONFIDENTIAL**

---

## 1. Why This Exists
No real users available. We use **Synthetic User Interviews** — AI personas based on PRD assumptions — to surface UX risks before design starts.

---

## 2. Personas (5)

| ID | Who | Volume/Month | Biggest Pain Today |
|----|-----|--------------|--------------------|
| P1 | Call Center Ops Manager (AK Callers) | 1M+ records | 24–48hr manual delivery, no suppression |
| P2 | Mortgage Lead Manager | 10–50k records | No self-service, no cost visibility |
| P3 | Real Estate Investor | 2–20k records | Export caps, re-pulls same records constantly |
| P4 | Solar Operator | 50–200k records | Needs developer to pull lists, no self-service |
| P5 | Platform Admin | — | Fears misconfiguring token, password reset overhead |

---

## 3. Synthetic Interview — Question Script

5 questions per phase. Ask all personas unless marked.

**Phase 1 — Their World**
1. Walk me through your day. Where does pulling a list fit in?
2. What tools do you use today? What frustrates you most?
3. Last list you pulled — how long from "I need it" to "team has it"?

**Phase 2 — Pain Points**
4. Tell me about a time a broken list process cost you a deal or wasted time.
5. Have you ever pulled records you already had? How often? What did you do?
6. How do you decide what filters to apply? What filter do you wish you had?

**Phase 3 — Core Flow Reactions**
7. You open the platform — first thing you do is type a location. What do you type?
8. What's your "sweet spot" record count? Too small? Too large?
9. What do you need to know before you hit Download?
10. After the CSV lands — what happens in the next 30 minutes?

**Phase 4 — Suppression & Orders**
11. You never want a duplicate record again. What does that look like practically?
12. Do you ever go back to a list you pulled months ago? What for?
13. You pulled records outside this platform. How do you stop re-pulling them?

**Phase 5 — Admin Only (P5)**
14. First thing you configure on a new platform?
15. How do you handle a teammate locked out today? How long does it take?
16. Someone on your team made a huge accidental download. Do you want to know?

---

## 4. User Flows to Map

| ID | Flow | Personas | Priority |
|----|------|----------|----------|
| UF-01 | Search → Filter → Count → Export | P1–P4 | P1 |
| UF-02 | Admin Setup & Token Config | P5 | P1 |
| UF-03 | Invite & Revoke Users | P5 | P1 |
| UF-04 | Suppress Past Orders → New Pull | P1, P3 | P1 |
| UF-05 | Import External CSV as Suppression | P1, P3 | P2 |
| UF-06 | View Order History & Re-export | P1–P4 | P1 |
| UF-07 | Async Job → Pending → Ready → Download | P1–P4 | P1 |
| UF-08 | Failed Order (No Credits) | P1–P4 | P1 |

**For each flow, answer before wireframing:**
- What triggers this flow?
- What decisions does the user make mid-flow?
- What does a failure state look like?

---

## 5. Open Questions — Must Resolve Before Design

| # | Question | Owner |
|---|----------|-------|
| Q1 | Show cost estimate during filtering or only at Download confirm? | BatchData / Sean |
| Q2 | Does suppression update the live count in real time? | BatchData / Joseph |
| Q3 | In-app notification when async job is ready — or email too? | BatchData / Sean |
| Q4 | What error does the API return on insufficient credits? | BatchData / Joseph |
| Q5 | Platform locked or partially usable before token is configured? | ORIL + BatchData |

---

## 6. Timeline (1 Day)

| # | When | Activity | Output |
|---|------|----------|--------|
| 1 | Morning | Run synthetic interviews (all 5 personas) | Interview notes |
| 2 | Morning | Synthesize — top 3 insights per persona | Insight summary |
| 3 | Afternoon | Map user flows UF-01 to UF-08 | Annotated flow diagrams |
| 4 | Afternoon | Define Information Architecture | Navigation structure + screen hierarchy |
| 5 | Afternoon | Resolve Q1–Q5 with BatchData | Updated open questions log |
| 6 | End of day | Hand off to design | Screen inventory + wireframe brief |

---

*v1.3 · ORIL · March 2026*
