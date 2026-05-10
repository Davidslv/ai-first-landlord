# Decision Log

The Decision Log records what was decided, when, on what evidence, and the outturn — so contestable decisions can be defended and the rest of the portfolio runs against a consistent record. The PRS Ombudsman (mandatory 2028), local authority enforcement under RRA 2025, the First-tier Tribunal, and the County Court all ask the same first question: *show me what you decided, when, and on what basis*. The log answers in seconds.

**Canonical reference:** Appendix F (Decision Log Template).

---

## Files in this folder

| File | What it holds |
|---|---|
| [`master-template.md.txt`](master-template.md.txt) | The 6-field entry shape. Drop into any of the eight category files and start logging. |
| [`examples/`](examples/) | Nine worked examples — anonymised — covering Section 13, tenant selection, pet permission, Right to Rent, Information Sheet service, Awaab's-Law-style hazard, Section 8 hold, complaint handling. Each example carries a header noting which book chapter it illustrates. |

---

## The eight categories

Each category gets its own running file in your own systems folder (you populate; this repo only carries the master template and the worked examples). Cross-category decisions go in the most load-bearing category and cross-reference from the others.

| Category | File suggested | Covers |
|---|---|---|
| **S13** | `s13-rent-reviews.md` | Section 13 rent reviews. Once per twelve months post-RRA. |
| **S8** | `s8-possession.md` | Section 8 ground decisions. Form 3A and ground-specific wording. |
| **SELECT** | `selection.md` | Tenant selection: accept, reject, tie-break, holding deposit, security deposit lodged within 30 days. The bidding ban makes rejection rationales load-bearing. |
| **PETS** | `pets.md` | Pet permission: granted, refused, conditions. RRA 2025 28-day window; silence past 28 days deems consent. |
| **R2R** | `right-to-rent.md` | Right to Rent method, document group, re-check date. |
| **DOCS** | `docs-service.md` | Information Sheet (existing-tenant 31/05/2026 deadline) and Written Statement of Terms (new-let, s.16D HA 1988). |
| **MAINT** | `maintenance.md` | Major maintenance and Awaab's-Law-style hazard decisions. |
| **COMP** | `complaints.md` | Complaint handling, redress, Ombudsman escalation. End-of-tenancy deposit-deduction disputes fall here, cross-referenced to SELECT. |

---

## Suggested folder layout in your own systems folder

```text
[your-systems-folder]/
  decision-log/
    s13-rent-reviews.md     # Section 13 decisions, chronological
    s8-possession.md        # Section 8 decisions
    selection.md            # tenant selection decisions
    pets.md                 # pet permission decisions
    right-to-rent.md        # R2R method and re-check decisions
    docs-service.md         # Information Sheet + WST service
    maintenance.md          # major maintenance + hazard
    complaints.md           # complaint handling
    evidence/               # PDFs, applicant logs, call notes
  properties/               # per-property knowledge files
  tenancies/                # per-tenancy operating manuals
```

---

## The entry shape

Six fields per entry — see [`master-template.md.txt`](master-template.md.txt) for the drop-in form.

| Field | What goes in it |
|---|---|
| **Date** | DD/MM/YYYY of the decision — not the date of the underlying event. |
| **Decision** | One sentence, active voice. *Raise rent to £[NEW_RENT], effective [DD/MM/YYYY].* *Reject application from [APPLICANT_REF] on affordability.* |
| **Property / Tenancy** | Per-property reference and tenancy reference. |
| **Rationale** | One to three sentences. *Why this decision and not another.* |
| **Evidence pointer** | File path to the underlying artefact: AI draft, contractor quote, applicant log line, Form 4A, scheme correspondence. The log points to evidence; it does not duplicate it. |
| **Outcome** | Filled when the outcome resolves. *Tenant accepted; new rent live from [DD/MM/YYYY].* *Tribunal set market rent at £[X].* |

Entries are never deleted; superseded entries marked *superseded by entry [N]*; the new entry references back. The audit trail is the chain.

---

## Conventions

- **Append-only.** One entry per decision. Long-form rationale (over three sentences) goes under `evidence/`; the rationale field carries a one-sentence summary plus link.
- **Update at the time of the decision.** No batch entry. The drafting workflow produces the entry alongside the comm.
- **Internal version names tenants in full** (Article 6(1)(b)/(f) GDPR lawful basis: contract / legitimate interest). Any extract to a public chat window goes through the redaction protocol.
- **Retention: six years from resolution** (working floor — Limitation Act 1980 contract limitation). Subject to UK GDPR storage-limitation review under Article 5(1)(e) where no live dispute or regulatory enforcement is open. Confirm with your DPO.

---

## Review cadence

- **At the time of the decision** — the entry is created alongside the comm.
- **Quarterly bottleneck-finding pass** (Chapter 16) — re-read categories with repeated root causes.
- **Annual revalidation** (Chapter 16) — re-read every entry from the prior twelve months and flag any open >90 days.
