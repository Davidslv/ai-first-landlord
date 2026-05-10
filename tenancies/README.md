# Tenancy Operating Manuals (TOMs)

The per-tenancy substrate. One TOM per active tenancy — 25 fields, fixed structure, scannable in under a minute, populated once and updated on a small set of named events.

**Canonical reference:** Chapter 6 (The Tenancy Operating Manual) and Appendix D.

---

## Three variants — pick the right one for the cohort

The Renters' Rights Act 2025 created two distinct regulatory documents that look similar but serve different cohorts. Field 19 of the TOM is the load-bearing line — and which variant you use depends on **when the tenancy started**.

| Variant | When to use | Field 19 reads |
|---|---|---|
| [`tom-existing.md.txt`](tom-existing.md.txt) | Tenancies in residence **before 1 May 2026** (converted from periodic AST to Assured Periodic Tenancy by RRA Phase 1). | *Information Sheet served* (RRA Information Sheet 2026; statutory deadline 31 May 2026; Sched 6 para 7 RRA 2025 + s.16I HA 1988) |
| [`tom-new.md.txt`](tom-new.md.txt) | Tenancies granted **on or after 1 May 2026** (Assured Periodic Tenancy from outset under RRA Phase 1). | *Written Statement of Terms served* (s.16D HA 1988 as inserted by RRA 2025; served before signing) |
| [`tom-ai-submission.md.txt`](tom-ai-submission.md.txt) | The redacted version used for any AI workflow **outside a documented business-tier vendor session**. Variant-agnostic between the existing and new cohorts — only field 19 differs. | Whichever of the above applies, with placeholders for all identifiers. |

The two cohorts are **not interchangeable**. The Information Sheet was a one-off rollout document; its 31 May 2026 deadline is closed and does not apply to new lets. The Written Statement is an ongoing per-let obligation. Same penalty band (£4,000 starting / £7,000 first-breach maximum, £40,000 for uncorrected offences); different statutory anchor; different timing rule.

---

## Two versions of every populated TOM

Whichever cohort variant you use, a populated TOM lives in two versions:

- **Internal version** — full names and reference numbers. Stored on your business-tier vendor workspace under the controller-processor agreement. Used inside that workspace (TOM attached as context with full names).
- **AI-submission version** — all identifiers replaced with semantic upper-case placeholders (`[TENANT_A]`, `[DEPOSIT_REF]`, `[PROPERTY_REF]`, etc.). Used outside the business tier, or attached when you want belt-and-braces redaction inside it.

The internal version stays on your controlled storage. The AI-submission version is *generated when needed, not retained* — produced at prompt-build, lives only as long as the chat session.

---

## File naming

Suggested convention: `[TENANCY_REF].md` — where `TENANCY_REF` is `[PROPERTY-SHORT]-[YYYY-MM]` for single-family lets and `[PROPERTY-SHORT]-[ROOM]-[YYYY-MM]` for HMO room tenancies.

Examples:

```
tenancies/
  BRAM-2-2023-06.md           # internal — single-family BTL converted from AST
  BRAM-2-2023-06-ai.md        # AI-submission version of the above
  AVON-2026-10.md             # internal — new RRA-Phase-1 grant
  SELS-R1-2025-04.md          # internal — HMO room
  SELS-R1-2025-04-ai.md       # AI-submission version
  archive/
    LIND-2022-09.md           # concluded tenancies kept for the voice-training corpus
```

---

## File status discipline

Every TOM carries one of three statuses on field 25:

- **Active** — the tenancy is live.
- **Concluded** — notice received, deposit returned, tenancy closed. Concluded TOMs become eligible for the voice-training corpus (see [`../voice/`](../voice/)) under the Chapter 4 §11 redaction rules.
- **Archived** — more than two years post-conclusion. Retained per the Records of Processing Activities (ROPA) for as long as your retention policy specifies.

The transition from Active → Concluded happens once the deposit is confirmed returned by the protection scheme. Active TOMs never go into voice-training; only Concluded ones do.

---

## When to update

The TOM updates on a small set of named events (Chapter 6 §6):

| Event | Field(s) | Cadence |
|---|---|---|
| Rent paid | 7 | Monthly (your bookkeeper updates) |
| Section 13 rent review served | 16 | Once per twelve months |
| Information Sheet / Written Statement served | 19 | Once per tenancy |
| Right to Rent re-check | 10 | Only where a time-limited status was on file |
| Household change | 11 | Each change, dated |
| Maintenance ticket | 15 | Per ticket — TOM line points at latest reference |
| Pet permission granted or refused | 12 | Within 28 days per RRA |
| Special agreement signed | 20 | Date added, document filed |
| Last update | 24 | Every time any of the above happens |

---

## Where this fits

The TOM reads alongside the Property Knowledge File (one per property — see [`../properties/`](../properties/)) and the trained voice profile (see [`../voice/`](../voice/)). When the AI drafts a tenant comm, it loads voice profile first (sets the register), TOM second (supplies the tenancy-specific facts), property knowledge file third (supplies the building-level facts). The eleven-template starter library (see [`../templates/`](../templates/)) fires against TOM data.

The compliance dashboard (see [`../dashboard/`](../dashboard/)) reads anniversary fields directly from each TOM — Section 13 anniversary from field 4 + 16, Right to Rent re-check from field 10, Information Sheet / Written Statement from field 19.
