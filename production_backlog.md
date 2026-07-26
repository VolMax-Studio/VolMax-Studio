# VolMax Studio — Production Backlog Registry (`production_backlog.md`)

> [!IMPORTANT]
> **Universe Metadata & Deterministic Ordering Doctrine**  
> - **Universe Version:** `ERCOT-BESS-universe-v1`  
> - **Date Frozen:** `2026-07-26T12:30:00+02:00`  
> - **L0 Source Anchor:** US Energy Information Administration (EIA) Form 860M / ERCOT Operating Generator Register (`Balancing Authority Code == 'ERCO'`, `Technology == 'Batteries'`).  
> - **Protocol Version:** `BATC-ERCOT v1.0` (P10 Verification Standard)  
> - **Deterministic Sort Criteria:** (1) Commercial Operation Date (COD) Oldest $\to$ Newest; (2) Federal EIA Plant ID Alphanumeric Tie-break.

---

## Production Backlog Queue (`BATC-ERCOT` Protocol)

*Rule: The queue order below is immutable. Target selection is strictly dictated by Queue #. Data readiness is checked strictly when an asset reaches Queue #1. If 60-day telemetry is unavailable at execution time, status marks `DEFERRED (INSUFFICIENT TELEMETRY)` and execution advances to the next Queue number without reordering.*

| Queue # | Audit ID | EIA Plant ID | Plant / Asset Name | Entity / Operator | County | Capacity | COD | Status | DOI / Source Anchor |
| :---: | :--- | :---: | :--- | :--- | :--- | :---: | :---: | :---: | :--- |
| **01** | `US-TX-NOTR-001` | `56961` | Notrees Windpower Hybrid BESS | Deriva Energy | Ector, TX | 36.0 MW | 2012-12 | **Pending Readiness Check** | EIA-860M #56961 |
| **02** | `US-TX-BLUS-001` | `60690` | Blue Summit Storage BESS | Blue Summit Storage LLC | Wilbarger, TX | 30.0 MW | 2017-08 | **Pending Queue #02** | EIA-860M #60690 |
| **03** | `US-TX-PYRO-001` | `56981` | Pyron Wind Farm Hybrid BESS | RWE Clean Energy | Fisher, TX | 9.9 MW | 2018-01 | **Pending Queue #03** | EIA-860M #56981 |
| **04** | `US-TX-INAD-001` | `56984` | Inadale Wind Farm Hybrid BESS | RWE Clean Energy | Nolan, TX | 9.9 MW | 2018-01 | **Pending Queue #04** | EIA-860M #56984 |
| **05** | `US-TX-KING-001` | `61741` | Kingsberry Energy Storage | Austin Energy | Travis, TX | 1.5 MW | 2018-09 | **Pending Queue #05** | EIA-860M #61741 |
| **06** | `US-TX-CAST-001` | `60123` | Castle Gap Solar Hybrid BESS | Upton County Solar 2 LLC | Upton, TX | 9.9 MW | 2019-06 | **Pending Queue #06** | EIA-860M #60123 |
| **07** | `US-TX-COMM-001` | `62609` | Commerce ESS | City of San Antonio (CPS) | Bexar, TX | 10.0 MW | 2019-06 | **Pending Queue #07** | EIA-860M #62609 |
| **08** | `US-TX-PROS-001` | `62753` | Prospect Storage BESS | GlidePath Power | Brazoria, TX | 9.9 MW | 2020-01 | **Pending Queue #08** | EIA-860M #62753 |
| **09** | `US-TX-WORS-001` | `64424` | TX8 Worsham BESS | Key Capture Energy | Pecos, TX | 9.9 MW | 2020-02 | **Pending Queue #09** | EIA-860M #64424 |
| **10** | `US-TX-PORT-001` | `64425` | TX2 Port Lavaca BESS | Key Capture Energy | Calhoun, TX | 9.9 MW | 2020-03 | **Pending Queue #10** | EIA-860M #64425 |
| **11** | `US-TX-RABB-001` | `60649` | Rabbit Hill Energy Storage | Rabbit Hill LLC | Williamson, TX | 9.9 MW | 2020-04 | **Pending Queue #11** | EIA-860M #60649 |
| **12** | `US-TX-FLAT-001` | `64423` | TX7 Flat Top BESS | Key Capture Energy | Reeves, TX | 9.9 MW | 2020-05 | **Pending Queue #12** | EIA-860M #64423 |
| **13** | `US-TX-ALVI-001` | `64293` | Alvin BESS | Engie North America | Brazoria, TX | 9.9 MW | 2020-10 | **Pending Queue #13** | EIA-860M #64293 |
| **14** | `US-TX-ODES-001` | `64294` | Odessa BESS | Engie North America | Ector, TX | 9.9 MW | 2020-10 | **Pending Queue #14** | EIA-860M #64294 |
| **15** | `US-TX-ANOL-001` | `64295` | Angleton / esVolta Anole BESS | esVolta / Engie | Brazoria, TX | 240.0 MW | 2020-11 | **Published** | DOI: [`10.5281/zenodo.21304135`](https://doi.org/10.5281/zenodo.21304135) |
| **16** | `US-TX-GAMB-001` | `64528` | Gambit Energy Storage BESS | Gambit Energy / Tesla | Brazoria, TX | 100.0 MW | 2021-06 | **Pending Queue #16** | EIA-860M #64528 |
| **17** | `US-TX-BATC-001` | `64314` | Bat Cave BESS (Dickinson) | Engie North America | Mason/Galveston, TX | 100.0 MW | 2021-06 | **Published** | DOI: [`10.5281/zenodo.21416615`](https://doi.org/10.5281/zenodo.21416615) |

---

## Operational Production & Provenance Doctrine

1. **Zero Hallucinated Resource IDs Rule:** Candidate audit targets MUST be extracted from official ERCOT/EIA public generator registration lists downloaded and inspected with L0 document anchors. Extrapolated or synthetic resource names are strictly banned.
2. **Zero Cherry-Picking Rule:** Target selection is strictly dictated by `Queue #` derived from the frozen register.
3. **Single Research Gate Limit:** Exactly **ONE** research gate is permitted to be open in the lab at any given time.
4. **Market Protocol Boundary:** Moving to a new market (e.g., AEMO or ELEXON/GB) requires a mandatory 1-time Research Gate to adapt and freeze a market-specific protocol (e.g., `BATC-NEM v1.0` or `BATC-GB v1.0`).
