# PropExport List Builder — Synthetic User Interviews
**ORIL · March 2026 · CONFIDENTIAL**

---

## Method
AI personas based on PRD assumptions. Each persona answered the full question script. Output: top 3 insights per persona + design implications.

---

## P1 — Call Center Ops Manager (Marcus T. / AK Callers)

### Top 3 Insights
1. **Speed is everything.** Current 24–48hr turnaround from BatchLeads/PropStream means agents sit idle. Any delay in list delivery directly costs money. Even 2–3 hours is too long.
2. **Suppression is a daily operational need, not a nice-to-have.** Marcus runs multiple campaigns across different client companies simultaneously. He needs to suppress by client tag — not just globally — or agents will dial duplicates across campaigns.
3. **He thinks in bulk.** 1M+ records/month means he never pulls small lists. He expects async to be the default, not a fallback. A progress state that he can leave and come back to is essential.

### Design Implications
- Async job status must be persistent and visible from any screen — not just the page where it was submitted
- Suppression must support tag-based filtering (e.g. suppress "AK Callers - Campaign 3" only)
- Empty states and loading states must be explicit — "your list is processing" with a timestamp, not a spinner
- No export caps or artificial limits — this is a hard dealbreaker for P1

---

## P2 — Mortgage Lead Manager (Sandra K.)

### Top 3 Insights
1. **She doesn't know what she doesn't know about filters.** Sandra relies on whatever filters the platform shows her — she doesn't come in with a predefined filter strategy. She needs guidance, not just options. QuickLists are critical for her.
2. **Cost anxiety is real.** She has been surprised by charges before on BatchLeads. She won't commit to a download without seeing the exact cost first. If the cost isn't shown clearly before she clicks Download, she will not trust the platform.
3. **Post-export, she goes straight to her CRM.** The CSV lands, she opens it, checks column names match her CRM import template, and uploads it. Column naming and consistency matters more than she'd admit.

### Design Implications
- QuickList templates must be the primary entry point for P2, not raw filters
- Cost estimate must be prominent — shown before the Download CTA, not after
- CSV column headers must be consistent and predictable across exports
- Consider a "what does this filter mean?" tooltip layer for non-technical users

---

## P3 — Real Estate Investor (Derek W.)

### Top 3 Insights
1. **He stacks filters aggressively.** Derek combines 4–6 criteria per pull (e.g. failed listing + equity > 40% + specific zip + absentee owner). He is frustrated when platforms treat filter combinations as edge cases rather than the default workflow.
2. **Re-pulling is his biggest waste of money.** He estimates 20–30% of his pulls are records he already has. He would pay a premium for a platform that genuinely eliminates this — but he's skeptical because BatchLeads claimed to solve it and didn't.
3. **He moves fast.** After export, he skip traces and starts outreach the same day. He doesn't want to wait for a job queue if his list is under 5k records.

### Design Implications
- Filter combinations must be first-class — AND/OR logic, ability to stack multiple criteria without friction
- Suppression must visibly update the live count — Derek needs proof it's working, not a promise
- For small lists (under a threshold TBD with PropExport), consider sync export to eliminate wait time
- Order history must show exactly what filters were used on each past pull — Derek reviews old lists to avoid repeating them

---

## P4 — Solar Operator (Priya N.)

### Top 3 Insights
1. **Self-service is the entire value proposition for her.** Priya currently needs a developer to pull every list. The moment she can do it herself, she eliminates a 2–3 day bottleneck. The bar for "easy enough" is high — if it takes more than 10 minutes to learn, she'll go back to the developer.
2. **Her filters are different.** She doesn't think in real estate terms (equity, liens). She thinks in property attributes — ownership type, property age, roof type. The platform needs to surface relevant filters without burying them under real-estate-specific language.
3. **She needs volume confidence.** She pulls 50–200k records and needs to know before downloading whether the result will be large enough to be worth the cost. The live count is critical for her decision-making.

### Design Implications
- Onboarding / first-run experience must be near zero friction — consider a guided first pull
- Filter labels must use plain language, not industry jargon — or include plain-language descriptions
- Live count must be fast and reliable — Priya makes go/no-go decisions based on it
- QuickList templates scoped to solar use case would be a strong differentiator for this segment

---

## P5 — Platform Admin (Jordan M.)

### Top 3 Insights
1. **First action on any new platform is user setup.** Jordan invites the team before testing features. If inviting users is confusing or broken, his confidence in the whole platform drops immediately.
2. **Token configuration is high-stakes and low-confidence.** Jordan understands the API token controls everything, but he doesn't know what "wrong" looks like. He needs immediate confirmation that the token is valid and that the right datasets are loaded — not a silent success state.
3. **He wants an audit trail, not just access control.** Jordan doesn't just want to revoke users — he wants to know who did what, especially for large downloads. Without visibility, he can't answer to his manager if something goes wrong.

### Design Implications
- Token setup screen must validate immediately and confirm exactly which datasets + pricing are active
- User invite flow must be the most polished flow in the admin panel — it's the first thing admins do
- Consider a basic activity log (user, action, timestamp, record count) — even read-only for MVP
- Revoke access must be instant and confirmed with clear feedback ("Jordan M. can no longer log in")

---

## Cross-Persona Patterns

| Theme | Personas | Design Implication |
|-------|----------|--------------------|
| Cost must be visible before download | P1, P2, P3, P4 | Cost estimate is non-negotiable — show it during filtering, not just at confirm |
| Suppression must be provably working | P1, P3 | Live count must update after suppression is applied |
| Async job must be trackable | P1, P4 | Job status must persist across navigation — not page-bound |
| Plain language over jargon | P2, P4 | Filter labels need descriptions, especially for non-RE personas |
| First-run experience is trust-building | P4, P5 | Empty states and setup flows need extra polish |

---

*Synthetic interviews complete · ORIL · March 2026*
