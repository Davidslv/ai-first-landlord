# Property Knowledge File — single-family BTL

The per-property substrate. Three files per property covering everything that **does not change with each tenancy**: the building, the systems, the certificates, the quirks. Per-tenancy facts (who lives there, what they pay, when they signed) live in [`../../tenancies/`](../../tenancies/).

**Canonical reference:** Chapter 5 (Property Knowledge Files) and Appendix C.1 / C.3.

---

## Files in this folder

| File | What it holds |
|---|---|
| [`baseline.md.txt`](baseline.md.txt) | Address, title, building, period features, refurbishment history, services and meters, heating, safety installations, insurance, mortgage, neighbours, suppliers, keys, documents-on-file. Updated only on refurbishment or service-reference change. |
| [`compliance.md.txt`](compliance.md.txt) | Gas safety record (CP12), EICR, EPC, smoke and CO alarm checks, HMO licence (delete section if not applicable), buildings insurance, mortgage product expiry. Updated on every new certificate or renewal. |
| [`quirks.md.txt`](quirks.md.txt) | Free-text — the things that catch out a new contractor, tenant, or AI session. About 20 lines for a single BTL. Updated whenever you learn something. |

---

## How to populate

1. **Copy this entire folder** once per property. Rename it to `[property-short-name]/` — e.g. `47-bramwell-road-flat2/`. Keep the slug short, hyphenated, and stable; AI tooling reads filenames.
2. **Run the capture protocol** (Chapter 5 §3): about 30 minutes desk-time after the on-site walk; closer to 45–60 minutes end-to-end including the visit. By the eighth property the desk portion takes around half the time.
3. **Walk the property in a fixed order** every time so the file structure stays consistent: street view, entrance, hallway, kitchen, living, bathroom(s), bedroom(s), utility, outdoor space, services cupboard, loft.
4. **Photograph every nameplate** — boiler, immersion, consumer unit, gas meter, electricity meter, stopcock, smoke and CO alarms. Brand, model, serial.
5. **Fill in `baseline.md.txt` first** (services, building, period features). Then `compliance.md.txt` (certificates with expiries). Then `quirks.md.txt` last — it populates from your walk-pad rather than from documents.

---

## Naming convention

`[property-short]-[topic].md` if you flatten the structure, or use the topic-only filenames inside the property folder. Examples:

```
47-bramwell-road-flat2/
  baseline.md.txt
  compliance.md.txt
  quirks.md.txt
  documents/
    2026/
      cp12-2026-06-09.pdf
      epc-2026-08-11.pdf
```

PDFs of certificates live in a `documents/[YYYY]/` subfolder named `[document-type]-[YYYY-MM-DD].pdf`. The compliance file references each PDF by filename.

---

## When to refresh

Updates triggered by named events (Chapter 5 §8):

- **Annual gas safety inspection** → `compliance.md.txt` (engineer, date, expiry, filename, tenant-copy-served line). Five minutes.
- **Five-yearly EICR** → `compliance.md.txt` (update line, file certificate, close any remedials within 28 days).
- **Refurbishment** (boiler, rewire, windows, kitchen, bathroom) → `baseline.md.txt` (refurbishment history section plus related fittings).
- **New EPC** → `compliance.md.txt` (and `baseline.md.txt` if the refurbishment also changed the building).
- **Insurance renewal** → `compliance.md.txt`.
- **Quirks** → `quirks.md.txt` whenever you learn something.

**A new tenancy never updates these files.** Per-tenancy facts go in the [Tenancy Operating Manual](../../tenancies/).

Twice a year: a 20-minute pass across all property files. Open each baseline, scan *Documents on file*, confirm linked documents exist, fix any drift.

---

## HMO?

If the property is a licensed HMO, also copy [`../_hmo-template/`](../_hmo-template/) into the same folder. HMOs need three additional files: `licence.md.txt`, `fire-system.md.txt`, `room-ledger.md.txt`.
