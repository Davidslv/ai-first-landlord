# Template Library

The eleven-template starter library — roughly 80% of recurring tenant comms by volume. The high-stakes 20% (Section 8 service itself, complaint responses heading to redress, anything that might end up at the First-tier Tribunal) is drafted from scratch under the Chapter 10 override rule.

**Canonical reference:** Chapter 11 (Templates That Compound) and Chapter 13 §5 (Written Statement of Terms cover). Worked artefact: Chapter 11 §3 (the maintenance-acknowledgement template populated against a real Reeves boiler email).

---

## Templates in this library

| # | File | Scenario | Source |
|---|---|---|---|
| 1 | [`maintenance-acknowledgement.md.txt`](maintenance-acknowledgement.md.txt) | Inbound maintenance ticket from a tenant. Same-day human reply, named engineer, visit shape, recourse if symptoms recur. The most-fired template. | Ch 11 §2 template 1; worked at §3 |
| 2 | [`rent-confirmation.md.txt`](rent-confirmation.md.txt) | Standing-order receipt acknowledgement at start of tenancy or after a rent change. | Ch 11 §2 template 2 |
| 3 | [`late-rent-first-chase.md.txt`](late-rent-first-chase.md.txt) | Polite, specific, no-implication note on a payment that did not arrive. Not a Section 8 ground 8 notice. | Ch 11 §2 template 3 |
| 4 | [`section-13-cover-note.md.txt`](section-13-cover-note.md.txt) | Annual rent-review cover note. Sits alongside Form 4A; explains in plain English; signals the First-tier Tribunal route. | Ch 11 §2 template 4 |
| 5 | [`section-8-ground-8-first-chase.md.txt`](section-8-ground-8-first-chase.md.txt) | Two-plus months' arrears: the email before any Form 3A is contemplated. **The Form 3A itself is human-signed and solicitor- or NRLA-helpline-reviewed before service.** | Ch 11 §2 template 5 |
| 6 | [`hmo-room-turnover-outgoing.md.txt`](hmo-room-turnover-outgoing.md.txt) | HMO sharer has given notice. Confirms move-out date, deposit-return logistics, schedule of dilapidations slot, forwarding address, household heads-up. | Ch 11 §2 template 6, §4 worked detail |
| 6m | [`hmo-room-turnover-incoming.md.txt`](hmo-room-turnover-incoming.md.txt) | The mirror — incoming sharer onboarding into an HMO household. | Ch 11 §4 (mirror reference) |
| 7 | [`deposit-return.md.txt`](deposit-return.md.txt) | End-of-tenancy reconciliation: deductions schedule with reasons, scheme reference, return date. | Ch 11 §2 template 7; worked Ch 12 §7 |
| 8 | [`information-sheet-cover.md.txt`](information-sheet-cover.md.txt) | RRA Information Sheet 2026 covering email — used once for the existing-tenant rollout before 31 May 2026. | Ch 11 §2 template 8 |
| 8n | [`written-statement-cover.md.txt`](written-statement-cover.md.txt) | Written Statement of Terms cover note for new lets (1 May 2026 onwards). The post-1-May cohort's equivalent of template 8. | Ch 13 §5 (worked Maya Lindgren cover) |
| 9 | [`mid-tenancy-gas-safety-reminder.md.txt`](mid-tenancy-gas-safety-reminder.md.txt) | Eight weeks before annual CP12 expiry: heads-up, named engineer, two slots, no-cost-to-tenant. Fires from the dashboard. | Ch 11 §2 template 9; Ch 14 §5 worked |
| 10 | [`viewings-request.md.txt`](viewings-request.md.txt) | Mid-tenancy viewings for re-let or refinance valuation. Cross-refs Chapter 12. | Ch 11 §2 template 10 |
| 11 | [`nrla-helpline-summary.md.txt`](nrla-helpline-summary.md.txt) | Internal note after every NRLA legal helpline call. The only template that does not fire on inbound traffic. | Ch 11 §2 template 11 |

---

## How to use these templates

**Templates are starting points, not final drafts.** The voice profile makes the draft sound like you; the TOM and the property file make it specific. The template only sets the *shape*. Sent without review, a template reads as generic.

**Three rules for the library** (Chapter 11 §1):

1. *Templates are starting points, not final drafts.* The Chapter 10 review pass sits between draft and send.
2. *Templates are the product of repeated drafting, not the input.* A frozen template dragged into a workflow drags the workflow back to retyping. A template extracted from three approved drafts carries the same signal as the voice profile. Use [`../prompts/save-as-template.md`](../prompts/save-as-template.md) to extract.
3. *Templates respect the regulatory frame.* A Section 13 cover note refers to **Form 4A** because that is the post-RRA prescribed notice. A Section 8 ground-8 first-chase template treats serving the **Form 3A** as the human-signed step the AI may not perform.

**Order of inputs to the drafting session:**

1. Voice profile (sets the register)
2. TOM for the relevant tenancy (per-tenancy facts)
3. Property knowledge file (building-level facts)
4. Inbound email (the trigger)
5. Template (sets the shape)
6. Drafting prompt → [`../prompts/drafting.md`](../prompts/drafting.md)

---

## Where each template draws its variables from

Every template carries a `VARIABLES` block at the foot, listing which placeholder comes from where. Typical sources:

- **From the inbound email:** issue summary, frequency claim, tenant's preferred date.
- **From the TOM:** tenant first name, tenancy reference, deposit reference and scheme, rent amount, contractor preferences (line 21).
- **From the property knowledge file:** boiler model, contractor name and accreditation, lead engineer's first name.
- **From the voice profile:** sign-off form, register adjustments.
- **Set at draft:** target window, visit duration, interim-use line.

---

## Maintaining the library

Three triggers refresh templates outside the compounding flow (Chapter 11 §6):

- **A regulatory commencement.** Phase 2 of the RRA — the PRS Database in late 2026, the PRS Ombudsman in 2028 — will move the language in templates that touch redress, registration references, and Information Sheet covering emails.
- **A new property or contractor.** A new contractor at any property does not need a template change — the property file change carries it. A new HMO does need the room-turnover template re-tested.
- **A failed dry-run on a live draft.** If the Chapter 10 review pass catches a draft that reads off and the issue traces to the template rather than the TOM or property file, the template is the thing to fix.

The annual audit (Chapter 16) carries a templates step: re-seed drifted templates from the last quarter's approved drafts.
