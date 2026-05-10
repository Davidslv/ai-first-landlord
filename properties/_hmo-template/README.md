# Property Knowledge File — HMO variant

A licensed House in Multiple Occupation carries obligations a single BTL does not. **In addition to** the three single-family-BTL files in [`../_template/`](../_template/) (baseline, compliance, quirks), an HMO needs three more files:

| File | What it holds |
|---|---|
| [`licence.md.txt`](licence.md.txt) | Licence reference, licensing authority, conditions schedule, renewal trail with the eight-week / four-week / one-week reminder dates, documents required for renewal. |
| [`fire-system.md.txt`](fire-system.md.txt) | BS 5839-6 system, panel make/model, detector layout room-by-room, annual service contract, weekly call-point test schedule. |
| [`room-ledger.md.txt`](room-ledger.md.txt) | One block per room — size against licence-condition minimum, current room status (occupied / vacant / in-transition / notice-served), rent, deposit reference. **No tenant identifiers** — those live in the per-tenancy TOM. |

**Canonical reference:** Chapter 5 §7 (HMO files for Selsdon Road) and Appendix C.2.

---

## How to populate

1. Copy [`../_template/`](../_template/) into your property folder first — every HMO still needs `baseline.md.txt`, `compliance.md.txt`, `quirks.md.txt`.
2. **Then copy this folder** into the same property folder. Three more files: `licence.md.txt`, `fire-system.md.txt`, `room-ledger.md.txt`.
3. **`compliance.md.txt` already has an HMO licence section** — populate it with the licence reference and expiry. The full conditions schedule lives in `licence.md.txt`.
4. **The fire-system file is separate from the BTL smoke/CO alarms** — an HMO carries a panel-controlled fire system the licence depends on. Different cadence (12-monthly engineer service plus weekly manager-led call-point test).
5. **The room ledger is property-level**, not per-tenancy. Six rooms gets six blocks; copy or delete blocks to match the licence. Per-room tenant facts go in individual TOM files in [`../../tenancies/`](../../tenancies/).

---

## Example folder layout (HMO)

```
62-selsdon-road/
  baseline.md.txt           # from _template/ — building, systems, period features
  compliance.md.txt         # from _template/ — non-HMO certificates plus HMO licence summary
  quirks.md.txt             # from _template/ — things that catch out a new contractor
  licence.md.txt            # from _hmo-template/ — full HMO licence file
  fire-system.md.txt        # from _hmo-template/ — BS 5839-6 system, panel, service log
  room-ledger.md.txt        # from _hmo-template/ — six rooms, occupancy, room-level facts
  documents/
    2026/
      cp12-2026-03-09.pdf
      eicr-2024-04-04.pdf
      fire-system-service-2026-05-28.pdf
    licence/
      hmo-licence-current.pdf
      hmo-licence-renewal-application-2026.pdf
```

---

## When to refresh

- **HMO licence renewal** → `licence.md.txt` (reference, expiry, conditions); refile certificate; reset the dashboard chase.
- **Fire-system annual service** → `fire-system.md.txt` (service certificate reference; check no remedials).
- **Weekly call-point test** → `fire-system.md.txt` (rolling log entry — typically same day each week, different call-point each week).
- **Room turnover (notice received / signed / move-out)** → `room-ledger.md.txt` (status flips occupied → notice-served → vacant → occupied).

The dashboard reads room-status from the room ledger and licence-expiry from `licence.md.txt`. The HMO licence renewal carries a **twelve-week documents-to-refresh chase** alongside the standard eight-week chase (Chapter 14 §3) — refreshed CP12, EICR, fire-system certificate, manager fit-and-proper declaration all need to be in the renewal pack.
