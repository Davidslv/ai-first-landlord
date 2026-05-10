# Compliance Dashboard

The system that quietly does the chasing. Every regulated next-due date for the portfolio, derived from the per-property compliance files (see [`../properties/`](../properties/)) and the Tenancy Operating Manuals (see [`../tenancies/`](../tenancies/)), surfaced on an eight-week / four-week / one-week chase rhythm so that no human has to remember any of it.

**Canonical reference:** Chapter 14 (The Tenancy Lifecycle Chase) and Appendix E (Compliance Calendar Template).

---

## Files in this folder

| File | What it holds |
|---|---|
| [`compliance-calendar-template.md.txt`](compliance-calendar-template.md.txt) | The empty dashboard — header, property-level panel template (one row per property, seven columns), tenancy-level panel template (one row per active tenancy, four columns), chase-queue template. |
| [`chase-rhythm.md.txt`](chase-rhythm.md.txt) | The eight-week / four-week / one-week chase rhythm explainer. What each chase point tests; what fires; what the codes do. Plus the parallel twelve-week documents-to-refresh chase for HMO licence renewals. |
| [`status-codes.md.txt`](status-codes.md.txt) | The nine fixed status codes — SET / 8W / 4W / 1W / SCH / EXP / END / MISS / DOCS-REFRESH — and what each means in the cell. |

---

## What the dashboard is — and what it isn't

**Not a triage rule.** Categorisation is in [`../prompts/categorisation-rule-set.md`](../prompts/categorisation-rule-set.md). The dashboard pushes items into the **Notice** queue at the eight-week mark; the daily inbox brief surfaces them.

**Not a drafting workflow.** The AI drafts a cover comm against the voice profile and the relevant template (see [`../templates/`](../templates/)) — gas safety reminder, Section 13 cover, HMO licence-renewal heads-up — queues it in the review pile, and waits for sign-off.

**Not a substitute for booking the contractor.** The dashboard generates the prompt; you take the action. The system escalates; it does not dispatch.

**A derived view, not a source of truth.** Updating a date on the dashboard does not change anything; the substrate files (compliance.md.txt per property, the TOM per tenancy) are where the dates live. The dashboard refreshes overnight, re-deriving every cell from the substrate.

---

## How to populate

1. Open [`compliance-calendar-template.md.txt`](compliance-calendar-template.md.txt). Copy it into your own systems folder.
2. **Fill the property-level panel** — one row per property. Read the next-due dates straight from each property's `compliance.md.txt`. Status starts as `SET` everywhere, with the date populated.
3. **Fill the tenancy-level panel** — one row per active tenancy. Read the Section 13 anniversary from TOM lines 4 + 16; the Information Sheet / Written Statement state from line 19; the Right to Rent re-check from line 10; the pet-permission state from line 12.
4. **Run the chase rhythm overnight** — every cell regenerates from the substrate. As an expiry approaches the threshold, the cell flips from `SET` to `8W`, then to `4W`, then to `1W`, then to `EXP` if the action is not visible.
5. **Read the dashboard Tuesday and Friday** — alongside (not instead of) the daily brief.

---

## The obligations the dashboard tracks

Every regulated obligation maps to a column. The dashboard does not restate the rules — those live in the book — but it surfaces the next-due date.

**Property-level (per row):**

- Gas Safety Record (CP12) — annual. 8-week chase opens at expiry minus 56 days.
- EICR — five-yearly. 8-week chase opens 56 days before expiry; remedials within 28 days of report.
- EPC — ten-yearly. Chase at twelve months out for the band-C 2030 lookahead.
- Deposit last-protected — TOM line 8. Record-keeping on a continuing tenancy; chases fire only on a new let or dispute.
- HMO licence renewal — five-yearly. **Twelve-week documents-to-refresh chase plus the standard eight-week chase.**
- Awaab's-Law-style hazard timelines — when triggered (event-driven).
- Pet-permission policy posture — property-level standing rule.

**Tenancy-level (per row):**

- Section 13 rent-review anniversary — annual. Chase opens against the **service deadline** (two months before anniversary), not the anniversary itself.
- Information Sheet / Written Statement of Terms — once-off / per new let.
- Right to Rent re-check — only for time-limited statuses; *N/A — Group 1* otherwise.
- Pet-permission 28-day window — event-driven; 21-day-elapsed nudge into Notice.

**Off-dashboard** (carried in the per-property file but not chased on the dashboard):

- Mortgage product expiry — bookkeeper's quarterly note.
- Smoke / CO alarm annual visual confirmation — covered at the gas safety inspection.
- Buildings insurance renewal — bookkeeper's quarterly note.

The dashboard carries only obligations whose breach carries regulatory or tribunal exposure.

---

## The quarterly bottleneck pass

The dashboard tells you the chase fires on time. It does **not** tell you whether the substrate is correct, or whether you are taking the right actions when chases fire. That is the job of the audit (Chapter 16):

- **Quarterly bottleneck-finding pass** — every 90 days. Re-read EXP / MISS items against the chase-points-fired record. Catch repeated root causes (one tenant always missing the booking; one obligation always slipping at 4-week chase).
- **Annual full revalidation** — every 12 months. Re-validate every dashboard cell against the source file and the underlying primary document.

The dashboard's success metric is whether the failure was **visible at every chase point**, not whether the action was taken.

---

## How this fits with the rest of the system

The dashboard reads from [`../properties/`](../properties/) (per-property next-due dates) and [`../tenancies/`](../tenancies/) (per-tenancy next-due dates). It writes into the daily brief's Notice block. Drafts that fire run through the voice profile, the [drafting prompt](../prompts/drafting.md), and the [template library](../templates/). Decisions taken when chases fire (raise the rent on the anniversary, defer the cycle, decline the pet request) get logged in the [`../decision-log/`](../decision-log/).
