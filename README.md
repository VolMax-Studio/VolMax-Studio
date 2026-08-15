# VolMax Studio Lab

**Independent verification of operational claims about grid-scale energy storage.**

We do not build models, sell optimisation, or advise on decisions. We take a public,
attributable claim about an asset, freeze the test rules in Git before pulling data,
and publish the verdict with the code that regenerates every number in it.

If we say a claim holds, it is because we first tried to show it does not.

---

## Evidence registry

Five asset audits against public settlement and market telemetry. Rules pre-registered;
every number regenerates from one script; raw-data provenance pinned by SHA-256.

| Asset | Claim under test | Verdict | Record |
|---|---|---|---|
| **Bat Cave BESS** — 100 MW / 100 MWh (ERCOT, US-TX) | 100 MW active power | **Not Demonstrated** — peak observed 72.61 MW | [10.5281/zenodo.21401795](https://doi.org/10.5281/zenodo.21401795) |
| **Bat Cave BESS** | 100 MWh energy capacity | **Not Demonstrated** — largest continuous discharge 58.0 MWh | [10.5281/zenodo.21401795](https://doi.org/10.5281/zenodo.21401795) |
| **Bat Cave BESS** | SoC telemetry consistency | **Inconsistent** per frozen rule; field definition **Deferred** | [10.5281/zenodo.21401795](https://doi.org/10.5281/zenodo.21401795) |
| **esVolta Anole ESS** — 240 MW / 480 MWh (ERCOT, US-TX) | 240 MW active power | **Demonstrated** | [10.5281/zenodo.21304134](https://doi.org/10.5281/zenodo.21304134) |
| **esVolta Anole ESS** | 480 MWh energy capacity | **Demonstrated** | [10.5281/zenodo.21304134](https://doi.org/10.5281/zenodo.21304134) |
| **esVolta Anole ESS** | SoC telemetry consistency | **Inconsistent** per frozen rule; field semantics **Deferred** | [10.5281/zenodo.21304134](https://doi.org/10.5281/zenodo.21304134) |
| **Pillswood BESS** — 98 MW / 196 MWh (Elexon, GB) | 98 MW active power | **Demonstrated** | [repository](https://github.com/VolMax-Studio/volmax-gb-bess-audit) |
| **Pillswood BESS** | 196 MWh energy capacity | **Verified with Limitations** (bounded) | [repository](https://github.com/VolMax-Studio/volmax-gb-bess-audit) |
| **ECO STOR Bollingstedt** — 103.5 MW (DE) | Physical grid limits | **Verified with Limitations** — 180 deviations, 0.47% of intervals | [10.5281/zenodo.21135861](https://doi.org/10.5281/zenodo.21135861) |
| **ECO STOR Bollingstedt** | Regime shift, July 2025 | **Verified with Limitations** — changepoint 5 July 2025 | [10.5281/zenodo.21135861](https://doi.org/10.5281/zenodo.21135861) |
| **AEMO NEM fleet** — 16 units ≥50 MW (AU) | 5-minute dispatch conformance | **Verified with Limitations** | [10.5281/zenodo.21190093](https://doi.org/10.5281/zenodo.21190093) |

Two ERCOT assets, the same telemetry source, the same frozen rules, opposite outcomes.
The method distinguishes; it does not decide in advance. An audit practice that has
never returned an adverse verdict is not evidence of independence.

**Pillswood note:** the archived record is v1.0 (July 2026); the repository is at v2.4
and carries subsequent L0 corrections. The repository is the current state; the archive
is the timestamped original. Both are public.

**Verdict vocabulary:** Demonstrated · Verified · Verified with Limitations ·
Inconsistent · Not Demonstrated · Not Verified · Deferred · Unfalsifiable-as-Stated.
Defined in the protocol, not chosen per report.

---

## Method

**The Verification Gap in Grid-Scale Assets: The P10 Non-Invasive Falsification Protocol**
— [10.5281/zenodo.21320140](https://doi.org/10.5281/zenodo.21320140)

Claim pinned verbatim → decomposed into falsifiable sub-claims → rules frozen and
committed before data acquisition → licence verified before download → integrity,
physics, statistics, reproducibility → verdict → immutable package with checksums.

A failure at any stage halts the audit and is reported as such. Limitations lead the
report; they are not an appendix. We audit public nameplate claims against independent
public telemetry — no access to operator systems, and none requested.

---

## Market measurement

Descriptive baselines of public electricity markets. These pass no verdict on any
operator or asset; they measure the market.

| # | Market | Measure | Record |
|---|---|---|---|
| 001 | AEMO NEM | Scarcity duration baseline, 13 months | [10.5281/zenodo.21693239](https://doi.org/10.5281/zenodo.21693239) |
| 002 | ERCOT | Scarcity duration baseline, 13 months | [10.5281/zenodo.21693245](https://doi.org/10.5281/zenodo.21693245) |
| 003 | ENTSO-E | Imbalance price duration baseline, 6 zones | [10.5281/zenodo.21693254](https://doi.org/10.5281/zenodo.21693254) |
| 004 | GB (Elexon BMRS) | BESS duration baseline, 13 months | [10.5281/zenodo.21693262](https://doi.org/10.5281/zenodo.21693262) |
| 005 | ENTSO-E | Cross-border physical flow dynamics | [10.5281/zenodo.21693276](https://doi.org/10.5281/zenodo.21693276) |

---

## Our own errors are published with the findings

Every package carries a failure log. Errors found in our own work stay visible, dated,
and archived — including a pre-registration scoping error that voided one of our own
hypotheses mid-audit rather than being quietly re-anchored to the observed data.

If you reproduce different numbers from ours, tell us. We will re-run and publish the fix.

---

## Contact

Ivan Nestorov · VolMax Studio Lab d.o.o., Serbia
ORCID [0009-0006-7940-9539](https://orcid.org/0009-0006-7940-9539) · volmax.core@gmail.com
