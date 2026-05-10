# Voice Training

The voice profile is a one-time output that converts ten anonymised emails from concluded tenancies into a saved profile, so that every AI-drafted communication sounds like the landlord rather than a property-management firm.

**Canonical reference:** Chapter 7 (Voice Training) and Appendix B (Voice Training Worksheet).

---

## Files in this folder

| File | What it holds |
|---|---|
| [`training-prompt.md.txt`](training-prompt.md.txt) | The verbatim prompt. Copy and paste into a fresh business-tier session; attach the ten anonymised samples beneath it. |
| [`voice-profile-template.md.txt`](voice-profile-template.md.txt) | The shape of the profile the AI returns (five sections, 600–900 words). Save the populated version as `voice-profile.md` in your own systems folder. |
| [`README-anonymisation.md`](README-anonymisation.md) | The per-sample anonymisation checklist. Apply to every one of the ten samples before submission. |

---

## The 10-email rule

Ten emails — five categories, two samples each, all from **concluded** tenancies. Fewer leaves the model too little signal; more produces diminishing returns.

The five categories:

1. **Vendor reassurance after a maintenance issue.** The engineer attended; the work is done; here's what to do if symptoms return.
2. **Maintenance acknowledgement.** Inbound tenant maintenance email gets a same-day human reply with a clear next step.
3. **Section 13 rent-review cover communication.** Form 4A goes with a covering email that explains the increase in plain English.
4. **Late-rent first follow-up.** A polite, specific, no-implication chase. The first late-rent email sets the tone for the arrears conversation.
5. **Move-out coordination.** Keys, final inspection, deposit return, forwarding address.

Two samples per category, ideally from different tenancies and different property types (one single-family BTL, one HMO room) so the model sees the same register across contexts.

**Concluded tenancies only.** Never live correspondence — this extends the redaction discipline to a second principle: a concluded tenancy is a closed file with lower re-identification exposure if anonymisation misses something. UK GDPR Article 5(1)(c) data minimisation favours concluded.

---

## The dry-run gate

Before the profile goes live, run **five test drafts** (Chapter 7 §6 / Appendix B §4):

1. Maintenance acknowledgement to a settled long-term tenant.
2. Late-rent first follow-up to a tenant on a borderline payment record.
3. Section 13 rent-review cover note.
4. Move-out coordination email at the end of an amicable tenancy.
5. Vendor reassurance after a maintenance issue at an HMO room.

Read each draft aloud against *does this sound like me?* Count *Yes* boxes:

- **5/5 Yes** — profile is live. Save, file, use.
- **4/5 Yes** — usable. Note failing category in this README; substitute at next re-train.
- **3/5 Yes** — usable, but re-train within a month before high-stakes use (Section 13 covers, complaints, deposit disputes).
- **2/5 or fewer** — full re-train before live use.

The gate is feel-judged. No metric for *does this sound like me* — only reading aloud and asking.

---

## Saving and filing pattern

Active profile is always **`voice-profile.md`** — singular, no date suffix; the daily brief and drafting workflow reference it by that exact name. Superseded versions archive as `voice-profile-YYYY-MM-DD.md`.

Suggested folder structure inside your own systems folder (not this repo — your populated copy stays out of version control under `.private/`):

```
[your-systems-folder]/
  voice/
    voice-profile.md                                 (the active profile)
    voice-profile-archive/
      voice-profile-2026-05-15.md
      voice-profile-2027-05-12.md
    training-samples/
      voice-training-samples-2026-05-15.md           (the 10 anonymised samples)
      voice-training-samples-2027-05-12.md
    README.md                                         (training log — see below)
```

### The training log

One paragraph per training pass. Minimum fields:

- **Date trained**
- **Vendor and tier** (e.g. Claude Team, ChatGPT Enterprise, Gemini in Workspace Business)
- **Samples used** — reference to the file in `training-samples/`
- **Categories with thin signal** — any category where the model flagged fewer signals
- **Dry-run gate result** — Yes count out of five, with notes on which prompts passed
- **Reviewer** — who read the calibration drafts
- **Live from / superseded** — active date range

---

## When to re-train

Three triggers; otherwise the profile holds.

1. **A senior person takes over the comms** — re-train against ten of their concluded-tenancy samples.
2. **A deliberate brand-voice shift** — re-train when the voice has actually moved.
3. **Twelve months elapsed** — schedule alongside the annual audit (Chapter 16). The annual re-train is around 90 minutes once the protocol is built.

Resist the urge to fiddle outside the triggers — value comes from consistency across hundreds of drafts.
