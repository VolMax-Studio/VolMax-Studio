# VolMax Studio — Production Backlog Registry (`production_backlog.md`)

> [!WARNING]
> **Status: `DRAFT — UNIVERSE UNVERIFIED (AWAITING DIRECT ERCOT REGISTER INSPECTION)`**  
> - **Universe Version:** `ERCOT-BESS-universe-v1-DRAFT`  
> - **Date Created:** `2026-07-26T12:15:00+02:00`  
> - **Protocol Version:** `BATC-ERCOT v1.0` (P10 Verification Standard)  
> - **Verification Mandate:** Unverified synthesized resource IDs are prohibited. Rows 03+ will be populated strictly upon direct browser/file extraction of official ERCOT Resource Registration tables with L0 URL/document anchors.

---

## Production Backlog Queue (`BATC-ERCOT` Protocol)

| Queue # | Audit ID | Resource ID | Asset Name | Location | Capacity | Status | DOI Record / Link |
| :---: | :--- | :--- | :--- | :--- | :---: | :---: | :--- |
| **01** | `US-TX-ANOL-001` | `ANOL_ESS_ESR1` | esVolta Anole BESS | Seagoville, TX | 240 MW / 480 MWh | **Published** | DOI: [`10.5281/zenodo.21304135`](https://doi.org/10.5281/zenodo.21304135) |
| **02** | `US-TX-BATC-001` | `BATCAVE_ESR1` | Engie Bat Cave BESS | Mason County, TX | 100 MW / 100 MWh | **Published** | DOI: [`10.5281/zenodo.21416615`](https://doi.org/10.5281/zenodo.21416615) |
| **03** | `UNVERIFIED` | `PENDING_REGISTER` | *Awaiting ERCOT Register Download* | ERCOT Market | TBD | **DRAFT (Unverified)** | Direct MIS / Register Extract Required |

---

## Operational Production & Provenance Doctrine

1. **Zero Hallucinated Resource IDs Rule:** Candidate audit targets MUST be extracted from official ERCOT public generator registration lists (e.g. ERCOT MIS / Capacity Changes / GIS reports) downloaded and inspected via browser. Extrapolated or synthetic resource names are strictly banned.
2. **Zero Cherry-Picking Rule:** Target selection is strictly dictated by `Queue #` derived from the frozen register.
3. **Single Research Gate Limit:** Exactly **ONE** research gate is permitted to be open in the lab at any given time.
4. **Market Protocol Boundary:** Moving to a new market (e.g., AEMO or ELEXON/GB) requires a mandatory 1-time Research Gate to adapt and freeze a market-specific protocol (e.g., `BATC-NEM v1.0` or `BATC-GB v1.0`).
