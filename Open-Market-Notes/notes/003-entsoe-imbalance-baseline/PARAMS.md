# VolMax Note #3: ENTSO-E Imbalance Duration Baseline — Frozen Parameters
**Class of Work:** VolMax Descriptive Analytical Note (Not a P10 Audit)
**Status:** Frozen
**Frozen Timestamp:** 2026-07-27T21:10:00+02:00

---

## 1. Scope & Datasets
- **Analysis Period:** 1 June 2025 00:00:00 CEST – 30 June 2026 23:59:59 CEST (13 months, localized in `Europe/Brussels` market timezone to eliminate UTC daylight saving shift boundary artifacts).
- **Verified Bidding Zones (Live API Audited & Unpacked):**
  - **`NL`** (Netherlands — `10YNL----------L`)
  - **`BE`** (Belgium — `10YBE----------X`)
  - **`FR`** (France — `10YFR-RTE------C`)
  - **`DK_1`** (Denmark West — `10YDK-1--------W`)
  - **`DK_2`** (Denmark East — `10YDK-2--------T`)
  - **`AT`** (Austria — `10YAT-APG------L`)
- **Excluded Zone Boundary Note:** `DE-LU` (Germany/Luxembourg) is explicitly excluded from the ENTSO-E API ingestion pipeline. Empirical dry-run audit confirmed that Germany does not publish DocumentType `A85` (Imbalance Prices [17.1.G]) via the ENTSO-E REST API endpoint (imbalance settlement is published via `regelleistung.net`).
- **Data Source:** Primary ENTSO-E Transparency Platform (Imbalance prices [17.1.g / 17.2.f]). Formally listed on the CC BY 4.0 free re-use list (item #27, "Imbalance prices"), version 18 October 2023, accessed 2026-07-24.
- **Evidence Anchors:**
  - Page 1 License: `PORTFOLIO/VolMax_Lineage_Credit_Sandbox/evidence/ENTSOE_FreeReuse_Page1_License_2026-07-24.png`
  - Page 4 Row 27 Listing: `PORTFOLIO/VolMax_Lineage_Credit_Sandbox/evidence/ENTSOE_FreeReuse_Page4_Row27_ImbalancePrices_2026-07-24.png`
- **Data Provenance Rule:** All raw data files must be accompanied by explicit provenance metadata in `data_manifest.json` (including exact API query endpoint / source URL, UTC acquisition timestamp, sha256 hash, and byte count). Unanchored or silent cache fallbacks without verified provenance metadata are prohibited.

---

## 2. Parameter Definitions & Doctrinal Rules

### Structural Settlement Column Mapping (Frozen Unapred)
Per ENTSO-E Transparency Specification and Electricity Balancing Guideline (EBGL), imbalance price columns represent physical deviation settlement rates for Balance Responsible Parties (BRPs):
- **`Short` Column ($P_{\text{imb}}^{-}$):** Represents the settlement price applied to a BRP in a **Short position** (under-generation / deficit). Evaluates system shortage severity.
- **`Long` Column ($P_{\text{imb}}^{+}$):** Represents the settlement price applied to a BRP in a **Long position** (over-generation / surplus). Evaluates system excess/surplus absorption incentives.

**Frozen Target Mapping Rule:**
- **Single-Pricing Regimes / Single Column Data:** If the payload contains a single price column (or where $P_{\text{imb}}^{+} == P_{\text{imb}}^{-}$ across valid intervals), both M1 and M2 evaluate directly on that single price time series $P_{\text{imb}}$.
- **Dual-Pricing Regimes:**
  - **M1 (System Shortage Scarcity Spikes):** Evaluated strictly on the **`Short` column ($P_{\text{imb}}^{-graphics}$)**.
  - **M2 (System Surplus Absorption):** Evaluated strictly on the **`Long` column ($P_{\text{imb}}^{+}$)**.

*No post-hoc distribution inspection or dynamic column re-mapping is permitted.*

---

### Metric 1 (M1): System Shortage Scarcity Duration
- **Physical Meaning:** Measures the continuous duration of severe grid generation shortfalls where imbalance settlement prices spike to incentivize fast-responding BESS discharge / generation.
- **Threshold A (Volatility):** 15-minute Imbalance Price $\ge €100/\text{MWh}$.
- **Threshold B (Extreme Scarcity):** 15-minute Imbalance Price $\ge €250/\text{MWh}$.
- **Event Definition:** A continuous sequence of 15-minute intervals meeting the price threshold.
- **Separation Rule:** Events separated by $<30\text{ minutes}$ (less than 2 intervals of 15 minutes) of prices below the threshold are counted as separate events.
- **Metrics Collected:** Histogram of event durations, median, mean, P90, and maximum single event duration (with date) per Bidding Zone.

---

### Metric 2 (M2): Grid Surplus Absorption & Negative Settlement Window Availability
- **Physical Meaning:** On imbalance markets, imbalance prices $\le €0/\text{MWh}$ or $\le €25/\text{MWh}$ do NOT represent day-ahead procurement costs. They represent periods of **severe grid over-generation (wind/solar surplus)** where the TSO financially incentivizes demand-side assets (BESS charging) to absorb excess energy and prevent grid frequency over-frequency.
- **Surplus Settlement Thresholds:**
  - **Zero / Negative Imbalance Pricing:** $P_{\text{imb}} \le €0/\text{MWh}$ (TSO pays assets to absorb excess energy or zero cost).
  - **Cheap Surplus Settlement:** $P_{\text{imb}} \le €25/\text{MWh}$.
- **Accumulation Rule:** Cumulative hours within a single calendar day (00:00 to 00:00 local market time, `Europe/Brussels`). Continuous blocks are *not* required.
- **Target Duration Thresholds (Direction of Conservatism):**
  - **8-Hour BESS Target:** $\ge 9.5\text{ hours}$ cumulative ($8\text{h} \div 0.85\text{ RTE} = 9.412\text{h}$, rounded up to $9.5\text{h}$).
  - **4-Hour BESS Target:** $\ge 4.8\text{ hours}$ cumulative ($4\text{h} \div 0.85\text{ RTE} = 4.706\text{h}$, rounded up to $4.8\text{h}$).
  *Note on Conservatism:* Rounding up raises the required window duration, which **strictly lowers the reported percentage of qualifying days**. This is conservative with respect to BESS feasibility claims (ensuring reported qualifying days strictly cover 100% of RTE energy losses).

---

### Cross-Zonal Incomparability Rule
> [!WARNING]
> Bidding zones in Europe operate under different TSO imbalance settlement rules (e.g. single-pricing post-harmonization in NL vs dual-pricing structures in specific historical regimes). **Direct quantitative comparison between zones operating under different settlement regimes is prohibited.** Each zone's metrics represent an empirical baseline of its own local TSO settlement environment.

---
*Status Timestamp: 2026-07-27T21:10:00+02:00 | VolMax Studio Lead Engineer*
