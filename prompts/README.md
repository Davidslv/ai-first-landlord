# Prompt Library

Six copy-paste-ready prompts. Tool-neutral — each works against any business-tier vendor (Claude Team / Enterprise, ChatGPT Team / Enterprise / Edu, Gemini in Workspace Business / Enterprise) operating under a controller-processor agreement.

**Canonical reference:** Appendix A (Prompt Library), with the originating chapter cross-referenced in each prompt's header.

| Prompt | Originating chapter | Purpose |
|---|---|---|
| [`voice-training.md.txt`](voice-training.md.txt) | Chapter 7 §4 | Train a voice profile from ten anonymised concluded-tenancy emails. |
| [`daily-brief.md.txt`](daily-brief.md.txt) | Chapter 8 §6 | Generate the morning Daily Inbox Brief — categorised digest with draft replies. |
| [`categorisation-rule-set.md.txt`](categorisation-rule-set.md.txt) | Chapter 9 §4 | The five-bucket categoriser the daily brief loads at the start of every pass. |
| [`drafting.md.txt`](drafting.md.txt) | Chapter 10 §2 | Drafting prompt with the three-question review pass (factual / tonal / compliance). |
| [`save-as-template.md.txt`](save-as-template.md.txt) | Chapter 11 §5 | Pattern-extract a reusable template from three approved drafts. |
| [`mtd-itsa-quarterly.md.txt`](mtd-itsa-quarterly.md.txt) | Chapter 15 §4 | Draft the quarterly MTD ITSA extract for personal-name income (the bookkeeper submits via ASA). |

---

## Use rules

**Business-tier session only.** No identifiable tenant data goes into a public chat window. Ever. Each prompt assumes a session under the Chapter 4 §10 / §11 redaction discipline. Inside a documented business-tier vendor workspace with a controller-processor agreement, the internal-version TOM and Property Knowledge File can be attached as context with full names. Outside it, use the AI-submission redacted versions.

**The AI never auto-sends.** Every drafting prompt produces a draft that goes through human review — the Chapter 10 three-question pass (*factual / tonal / compliance*) sits between draft and send.

**Order of context loading.** Voice profile first (sets the register). Then TOM (per-tenancy facts). Then property knowledge file (building-level facts). Then the inbound email or trigger event. Then the prompt. The order matters — register first, facts second.

**Template artefacts the prompts reference:**

- Voice profile → `../voice/voice-profile-template.md` (the shape) + your populated `voice-profile.md`
- TOM → `../tenancies/tom-existing.md` / `tom-new.md.txt` / `tom-ai-submission.md.txt`
- Property knowledge files → `../properties/_template/` and `_hmo-template/`
- Templates referenced by save-as-template → `../templates/`
- Compliance dashboard slice → `../dashboard/compliance-calendar-template.md`

---

## Quick-fire usage notes

| Prompt | When to run | Inputs to attach |
|---|---|---|
| voice-training | Once at setup; re-train on the three triggers in `../voice/README.md` | Ten anonymised samples (concluded tenancies only) |
| daily-brief | Daily, 06:30 scheduled | Voice profile, TOMs for any tenancy referenced, property files referenced, last 24h mail, dashboard slice |
| categorisation-rule-set | Loaded by daily-brief; standalone for one-off categoriser audits (Chapter 9 §7 Friday five-minute audit) | None — versioned standalone artefact |
| drafting | Per inbound that doesn't fit a template | Voice profile, TOM, inbound email |
| save-as-template | Friday afternoon, when three approved drafts of the same scenario have piled up over ~2 weeks | Three anonymised approved drafts |
| mtd-itsa-quarterly | Quarter-end (5 Jul / 5 Oct / 5 Jan / 5 Apr) | Bookkeeping-software ledger, bank-reconciliation balances, categorisation rule-set |
