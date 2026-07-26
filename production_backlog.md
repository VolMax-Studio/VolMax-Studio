# VolMax Studio — Production Backlog Registry (`production_backlog.md`)

> [!IMPORTANT]
> **Universe Metadata & Deterministic Ordering Doctrine**  
> - **Universe Version:** `ERCOT-BESS-universe-v1`  
> - **Date Frozen:** `2026-07-26T12:00:00+02:00`  
> - **Protocol Version:** `BATC-ERCOT v1.0` (P10 Verification Standard)  
> - **Deterministic Sort Criteria:** (1) Commercial Operation Date (COD) Oldest $\to$ Newest; (2) Resource ID Alphanumeric Tie-break.

---

## Production Backlog Queue (`BATC-ERCOT` Protocol)

*Rule: The queue order below is immutable. Assets are processed sequentially. Data readiness is checked strictly when an asset reaches Queue #1. If 60-day telemetry is unavailable at execution time, status marks `DEFERRED (INSUFFICIENT TELEMETRY)` and execution advances to the next Queue number without reordering.*

| Queue # | Audit ID | Resource ID | Asset Name | Location | Capacity | Status | DOI Record / Artifact Link |
| :---: | :--- | :--- | :--- | :--- | :---: | :---: | :--- |
| **01** | `US-TX-ANOL-001` | `ANOL_ESS_ESR1` | esVolta Anole BESS | Seagoville, TX | 240 MW / 480 MWh | **Published** | DOI: [`10.5281/zenodo.21304135`](https://doi.org/10.5281/zenodo.21304135) |
| **02** | `US-TX-BATC-001` | `BATCAVE_ESR1` | Engie Bat Cave BESS | Mason County, TX | 100 MW / 100 MWh | **Published** | DOI: [`10.5281/zenodo.21416615`](https://doi.org/10.5281/zenodo.21416615) |
| **03** | `US-TX-BRAM-001` | `BRAMLEY_ESR1` | Broad Reach Bramley BESS | Fort Bend, TX | 100 MW / 100 MWh | **Pending Readiness Check** | Target Queue #03 |
| **04** | `US-TX-GIRV-001` | `GIRVIN_ESR1` | Girvin BESS | Pecos County, TX | 100 MW / 100 MWh | **Pending Queue** | Target Queue #04 |
| **05** | `US-TX-CROS-001` | `CROSSETT_ESR1` | Crossett BESS | Crane County, TX | 100 MW / 100 MWh | **Pending Queue** | Target Queue #05 |
| **06** | `US-TX-CHIS-001` | `CHISHOLM_ESR1` | Chisholm Grid BESS | Fort Worth, TX | 100 MW / 100 MWh | **Pending Queue** | Target Queue #06 |
| **07** | `US-TX-ANGE-001` | `ANGELITA_ESR1` | Angelita BESS | San Patricio, TX | 100 MW / 100 MWh | **Pending Queue** | Target Queue #07 |

---

## Operational Production Doctrine

1. **Zero Cherry-Picking Rule:** Target selection is strictly dictated by `Queue #`. No manual reordering based on asset performance, operator identity, or telemetry outcome.
2. **Single Research Gate Limit:** Exactly **ONE** research gate is permitted to be open in the lab at any given time. Production executes continuously and independently of open research gates.
3. **Market Protocol Boundary:** Moving to a new market (e.g., AEMO or ELEXON/GB) requires a mandatory 1-time Research Gate to adapt and freeze a market-specific protocol (e.g., `BATC-NEM v1.0` or `BATC-GB v1.0`) before opening a production queue for that market.
