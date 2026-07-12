# VolMax Studio Lab

**Independent verification of battery & energy-storage claims — models, telemetry, and operational data.**

The energy-storage market runs on confident numbers: "98% SOH accuracy," "grid limits never violated," "10-year RUL." We provide the independent check — whether the claim comes from a machine-learning model or a 100 MW asset's operating record.

We do not audit companies. We audit **claims**.

---

## Evidence Registry

All audits are DOI-archived on Zenodo with pinned data hashes and a reproducible pipeline. Verdicts below are quoted verbatim from each report's verdict ledger.

| Claim under test | Subject | Verdict | Record |
|---|---|---|---|
| Active power export capacity (98 MW claim) | Pillswood BESS (98 MW / 196 MWh, GB) | Verified with Limitations (Bounded) | [10.5281/zenodo.21254253](https://doi.org/10.5281/zenodo.21254253) |
| Energy storage capacity (196 MWh claim) | Pillswood BESS (98 MW / 196 MWh, GB) | Verified with Limitations (Bounded) | [10.5281/zenodo.21254253](https://doi.org/10.5281/zenodo.21254253) |
| Active power export capacity (240 MW claim) | esVolta Anole BESS (240 MW / 480 MWh, US-TX) | Verified with Limitations (Claim Demonstrated) | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| Energy storage capacity (480 MWh claim) | esVolta Anole BESS (240 MW / 480 MWh, US-TX) | Verified with Limitations (Claim Demonstrated) | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| SoC telemetry consistency | esVolta Anole BESS | Inconsistent (per frozen rule; 55.2% pass overall; exploratory major event stratification 81.8% pass) | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| SoC telemetry semantics | esVolta Anole BESS | Deferred (Peak SoC observed = 558.0 MWh, +78.0 MWh; max_soc = 560.3 MWh, +80.3 MWh above nameplate) | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| FCA regime transition from July 2025 | ECO STOR Bollingstedt BESS (103.5 MW, DE) | Verified with Limitations | [10.5281/zenodo.21135862](https://doi.org/10.5281/zenodo.21135862) |
| "Grid limits never violated" | ECO STOR Bollingstedt BESS | Verified with Limitations | [10.5281/zenodo.21135862](https://doi.org/10.5281/zenodo.21135862) |
| Netzdienlich (grid-supportive) operation | ECO STOR Bollingstedt BESS | Consistent with claim; intent not distinguishable from price-driven dispatch | [10.5281/zenodo.21135862](https://doi.org/10.5281/zenodo.21135862) |
| 5-minute dispatch conformance | AEMO NEM BESS fleet (16 units ≥50 MW, AU) | Verified with Limitations (Descriptive Band; not a regulatory determination) | [10.5281/zenodo.21190094](https://doi.org/10.5281/zenodo.21190094) |
| Cross-jurisdictional generalization of operational signatures (our hypothesis) | AEMO fleet vs. European reference | Not Verified — hypothesis rejected | [10.5281/zenodo.21190094](https://doi.org/10.5281/zenodo.21190094) |
| Unit-level FCAS response (Hornsdale) | AEMO NEM | Unfalsifiable-as-Stated — public 4-second telemetry withdrawn under FPP | [10.5281/zenodo.21190094](https://doi.org/10.5281/zenodo.21190094) |
| SOH early-prediction uncertainty under distribution shift | UQ / conformal prediction audit | UQ necessary but not sufficient under shift | [10.5281/zenodo.21084102](https://doi.org/10.5281/zenodo.21084102) |
| EKF state-estimation replication | Published SOC/thermal estimator | Replicated with documented deviations | [10.5281/zenodo.21009974](https://doi.org/10.5281/zenodo.21009974) |

*(Registry rows are added only after a report is frozen and its DOI is live. Exploratory analyses — no verdict issued — are published separately on GitHub and are not listed here.)*

---

## The P10 Verification Method

Every audit runs under the [P10 Verification Protocol](https://github.com/VolMax-Studio/P10-Verification-Method) — an ordered, halt-on-failure framework: **L0** admissibility (license & data access) → **L1** data integrity → **L2** physics compliance → **L3** statistical integrity → **L4** reproducibility → **L5** verdict. Every published number regenerates from a single script against hash-pinned data.

The methodology has been formalized in our v1.0 preprint:
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21320141.svg)](https://doi.org/10.5281/zenodo.21320141)

Verdict vocabulary:

- **Verified** — the data supports the claim as stated.
- **Verified with Limitations** — the claim holds within stated boundaries (resolution floors, descriptive bands, data provenance caveats).
- **Not Verified** — the data does not support the claim; includes our own rejected hypotheses.
- **Unfalsifiable-as-Stated** — the claim cannot be independently tested from publicly available data as currently published.

The protocol applies to our own work first: see the [public rejection notice](https://github.com/VolMax-Studio/P10-Verification-Method/blob/main/governance/REJECTION_NOTICE_v1.1.md) for a proposed protocol extension that failed its own admissibility rules.

---

## Foundational portfolio

The audit practice is grounded in two decades of hands-on power-electronics and power-systems work (DE / NL / RS) and a build portfolio spanning battery SOH modeling, power-quality analysis, NILM, condition monitoring, and embedded telemetry. Those repositories remain public below as domain groundwork; they are builds, not audits, and carry no P10 verdicts.

---

**Engagements:** independent battery & BESS audits under P10 — SOH/RUL model verification, operational-claims verification from field data, reproducibility and data-leakage checks.

**Contact:** volmax.contact@gmail.com · [volmax-studio.rs](https://volmax-studio.rs) · [LinkedIn](https://www.linkedin.com/in/ivan-nestorov-274157371) · Zenodo: [Ivan Nestorov](https://zenodo.org/search?q=Nestorov%2C%20Ivan)

VolMax Studio Lab d.o.o. · Titel, Serbia
