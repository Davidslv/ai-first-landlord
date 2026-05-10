<!--
Template: Anonymisation checklist for voice training samples
Source: Chapter 7 §3 + Appendix B §2
Pairs with: training-prompt.md.txt (the prompt that consumes anonymised samples);
            ../tenancies/tom-ai-submission.md (the same redaction discipline applied to TOMs)
Companion to *The AI-First Landlord* (David Silva, 2026)
-->

# Anonymisation Checklist — Voice Training Samples

Every identifier comes out **before** any sample enters a vendor session, business-tier included. Replace with semantic upper-case tokens in plain square brackets — never strip a name and leave the sentence half-broken.

The same redaction discipline applies to:

- Voice training samples (this checklist)
- AI-submission Tenancy Operating Manuals (`../tenancies/tom-ai-submission.md`)
- Any extract of an internal artefact to a public chat window

---

## Per-email checklist

Apply to **each** of the ten samples before submission to the training prompt:

- [ ] Landlord name replaced with `[LANDLORD_NAME]` / `[LANDLORD_FIRST_NAME]` at sign-off
- [ ] Tenant name replaced with `[TENANT_NAME]` / `[TENANT_FIRST_NAME]` at greeting
- [ ] Co-tenants, joint tenants, household members replaced with `[CO_TENANT_NAME]` or `[HOUSEHOLD_MEMBER]`
- [ ] Property address replaced with `[PROPERTY_REF]`; HMO rooms with `[ROOM_REF]`; postcodes removed or `[POSTCODE_AREA]`
- [ ] Specific dates replaced with `[DATE]`, `[MONTH]`, `[WEEKDAY]`, `[YEAR]` as appropriate
- [ ] Engineer / contractor first names replaced with `[ENGINEER_FIRST_NAME]`; firms with `[CONTRACTOR_NAME]`
- [ ] Neighbours replaced with `[NEIGHBOUR]` or removed; prior agents with `[PRIOR_AGENT]`
- [ ] Phone numbers replaced with `[PHONE]` / `[LANDLORD_PHONE]`; emails with `[EMAIL]`
- [ ] Bank references, standing-order references, deposit references replaced with `[PAYMENT_REF]` or `[DEPOSIT_REF]`; scheme IDs with `[SCHEME_REF]`
- [ ] Rent amounts: keep if they carry voice signal (how you frame increases); replace with `[AMOUNT]` if they tie to a specific tenancy
- [ ] Postcode-area comparables: keep the area type, remove the specific postcode
- [ ] Vehicle details, key safe codes, alarm codes — **remove entirely**, never anonymise
- [ ] Children's names, school names, employer names — **remove entirely**
- [ ] Health, hardship, relationship details — **remove entirely**; voice training does not need these
- [ ] Ongoing legal matters, complaints in train, insurance claims — **exclude the email**; pick another

---

## Two cross-cutting rules

- **Read each anonymised sample end to end before submission.** A broken-after-redaction sentence tells the model less than a properly placeholdered one. The voice has to survive intact — the rhythm, the specificity, the apology that does not over-apologise. Only the identifiers come out.
- **Date the batch.** Filename `voice-training-samples-YYYY-MM-DD.md`. At re-training you will want to know which samples produced which profile.

If a sample fails anonymisation — identifiers too entangled, redacted version no longer reads — drop it and pick another.

---

## Worked example

The original (from a concluded tenancy):

```text
From: Margaret Whitfield <margaret@whitfieldproperty.example>
To: David Hartley <d.hartley@example.co.uk>
Date: 14 January 2026 09:42
Subject: Re: Boiler — 8 Linden Grove

Hi David,

Thanks for letting me know last night. Dan from Croydon Heating
Solutions went round at 08:30 this morning — same engineer who did
the annual check in November. He says it's the diverter valve, three
to five years old on this boiler, and he's swapping it on Thursday.
In the meantime the boiler is running, but if hot water cuts out
again before Thursday, give me a ring on 07700 900456 and I'll get
him back same day.

Sorry for the disruption — it's been a cold week and you needed it
working. Dan will text you Thursday morning before he comes round.

Margaret
```

After anonymisation for voice training submission:

```text
From: [LANDLORD_NAME]
To: [TENANT_NAME]
Date: [DATE]
Subject: Re: Boiler — [PROPERTY_REF]

Hi [TENANT_FIRST_NAME],

Thanks for letting me know last night. [ENGINEER_FIRST_NAME] from
[CONTRACTOR_NAME] went round at 08:30 this morning — same engineer
who did the annual check in [MONTH]. He says it's the diverter valve,
three to five years old on this boiler, and he's swapping it on
[WEEKDAY]. In the meantime the boiler is running, but if hot water
cuts out again before [WEEKDAY], give me a ring on [LANDLORD_PHONE]
and I'll get him back same day.

Sorry for the disruption — it's been a cold week and you needed it
working. [ENGINEER_FIRST_NAME] will text you [WEEKDAY] morning before
he comes round.

[LANDLORD_FIRST_NAME]
```

The voice survives intact. The placeholders strip the identifiers; the rhythm, the specificity, the apology that does not over-apologise all stay.
