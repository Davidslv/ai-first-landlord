# The AI-First Landlord — Toolkit

This repository is the companion toolkit to *The AI-First Landlord — An Operating Manual for UK Landlords in the Renters' Rights Era* (David Silva, 2026). It carries every reusable template the book references — Property Knowledge File scaffolds, the Tenancy Operating Manual in three variants, the voice-training prompt, the eleven-template starter library, the compliance dashboard scaffolding, the decision-log shape, and the 90-day build checklist — so readers can clone the substrate rather than retype it from a printed page.

**The book:** [The AI-First Landlord — An Operating Manual for UK Landlords in the Renters' Rights Era](https://www.amazon.co.uk/dp/B0H43MR1SP) (Kindle edition; paperback to follow)

The repo is the *blank* version. Worked artefacts (Margaret Whitfield's portfolio, the Reeves at 47 Bramwell Road, the Selsdon HMO, the Avon Way re-let) live in the book — they show the populated shape and the reasoning. The repo is what you copy and fill in.

---

## Directory structure

| Folder | What it holds | Canonical book reference |
|---|---|---|
| `properties/_template/` | Single-family BTL Property Knowledge File scaffold (baseline, compliance, quirks) | Chapter 5; Appendix C.1, C.3 |
| `properties/_hmo-template/` | HMO-only files (licence, fire system, room ledger) | Chapter 5 §7; Appendix C.2 |
| `tenancies/` | Tenancy Operating Manual scaffolds — three variants for the existing-tenant cohort, the post-1-May-2026 cohort, and AI-submission redaction | Chapter 6; Appendix D |
| `voice/` | Voice-training prompt, voice-profile output template, anonymisation checklist | Chapter 7; Appendix B |
| `prompts/` | Six copy-paste-ready prompts: voice training, daily brief, categorisation, drafting, save-as-template, MTD ITSA quarterly | Chapters 7–11, 15; Appendix A |
| `templates/` | The eleven-template starter library plus the HMO room-turnover incoming mirror and the Written Statement of Terms cover | Chapter 11; Chapter 13 §5 |
| `dashboard/` | Compliance-calendar template, chase-rhythm explainer, status codes | Chapter 14; Appendix E |
| `decision-log/` | Master template plus nine worked-example entries (anonymised) | Appendix F |
| `90-day-build/` | The 135-tickbox build checklist | Chapter 18; Appendix G |

Every subdirectory has its own README with the chapter pointer, what each file is for, and the order in which to populate them.

---

## Quick start: fork-and-rename for your own portfolio

The 90-day-build checklist is the ordered entry point. **Do not start by filling in templates.** The substrate (Property Knowledge File + Tenancy Operating Manual + voice profile) has to come first; the templates and the dashboard read from it.

1. Fork or clone this repo to a private location — your business-tier vendor workspace, a private GitHub repo, or local-only storage. **Do not put a populated copy into a public repo.**
2. Read [`90-day-build/README.md`](90-day-build/README.md) and [`90-day-build/checklist.md`](90-day-build/checklist.md). Tick along as you go.
3. Phase 1 (Days 1–7): two folders in your inbox; subscribe to a business-tier AI service; pick one property and one tenancy as your worked example.
4. Phase 2 (Days 8–30): copy `properties/_template/` once per property; copy the right `tenancies/tom-*.md` once per tenancy; train your voice profile against [`voice/training-prompt.md`](voice/training-prompt.md).
5. Phase 3 onwards: install the daily inbox brief, the five-bucket categoriser, the drafting workflow, the eleven-template library, the compliance dashboard.

---

## Conventions

**Placeholder format:** `[UPPER_CASE_TOKEN]` in plain square brackets. Examples: `[TENANT_NAME]`, `[PROPERTY_REF]`, `[DEPOSIT_REF]`, `[your UPRN — look up at findmyaddress.co.uk]`. Never angle brackets (collide with HTML); never backticks (overflow LaTeX margins). One bracket convention across the whole toolkit.

**Cohort split — Information Sheet vs Written Statement of Terms.** Two distinct regulatory documents under RRA 2025:

- **Information Sheet 2026** — served on **existing tenants** (assured tenancies in place before 1 May 2026). One-off rollout. Statutory deadline: 31 May 2026. Use [`tenancies/tom-existing.md`](tenancies/tom-existing.md) for these tenancies; line 19 records *Information Sheet served*.
- **Written Statement of Terms** — served on **new tenants** at the point of letting (tenancies granted on or after 1 May 2026). Ongoing obligation; served before signing. Use [`tenancies/tom-new.md`](tenancies/tom-new.md) for these tenancies; line 19 records *Written Statement of Terms served*.

Same field, different label, different statutory anchor. The two documents are not interchangeable.

**TOM file status:** every Tenancy Operating Manual carries one of three statuses on line 25 — **Active** (live tenancy), **Concluded** (notice given, deposit returned, tenancy closed), **Archived** (more than two years post-conclusion, retained per the ROPA). Only Concluded TOMs are eligible for the voice-training corpus.

**Chase rhythm:** the compliance dashboard runs an **eight-week / four-week / one-week** chase against every regulated next-due date. Eight weeks absorbs the first contractor *not this week*; four weeks tests *is the appointment in the diary?*; one week tests *is the action visible?* Expiry escalates to Urgent. HMO licence renewals carry a parallel **twelve-week documents-to-refresh** chase. Full nine-code status taxonomy in [`dashboard/status-codes.md`](dashboard/status-codes.md).

**Redaction discipline.** Every populated artefact in this toolkit contains identifying data. Internal versions live on your business-tier vendor workspace under a controller-processor agreement. AI-submission versions (where you are working outside that workspace) use the redaction conventions in [`tenancies/tom-ai-submission.md`](tenancies/tom-ai-submission.md) and [`voice/README-anonymisation.md`](voice/README-anonymisation.md).

**UK English throughout.** *organise*, *behaviour*, *colour*, *licence* (noun) / *license* (verb), *Buy-to-Let*, *flat*, *post*. £ never $. Dates *DD/MM/YYYY* in transactional artefacts, *14 May 2026* in prose.

---

## What this toolkit is not

This toolkit does not include:

- **The book's worked examples.** Margaret Whitfield's eight-property portfolio, the Reeves boiler chain, the 76-day Avon Way re-let timeline, the Selsdon HMO documents-to-refresh chase, the Crescent View missed Section 13 cycle, the Q1 MTD ITSA quarterly extract — these stay in the book because they teach what a populated artefact looks like.
- **Regulatory citations.** The book carries the statutory anchors (RRA 2025, Housing Act 1988, Tenant Fees Act 2019, Immigration Act 2014, Limitation Act 1980) and the gov.uk references. The toolkit names obligations operationally.
- **Diagrams.** The Mermaid diagrams in the book illustrate the workflows. The toolkit is artefact-only.
- **Margaret-specific contractors.** Croydon Heating Solutions, Lambeth Electrical Ltd, Bramwell Block Management — these are the book's recurring counterparties and stay there. The toolkit is generic.

---

## License

MIT — see [`LICENSE`](LICENSE). Copyright David Silva 2026.

---

## Contributing

Not accepting pull requests at this stage. This is published-companion material; the canonical version is the book, and the toolkit shape is fixed against the book's chapter and appendix structure. Issues for typos and broken links are welcome.
