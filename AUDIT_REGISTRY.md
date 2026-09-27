# Audit Registry

This registry preserves the detailed public audit record previously shown on the VolMax Studio Lab profile page.

## Asset audits

Five asset audits against public settlement and market telemetry. Rules were preregistered; raw-data provenance is pinned by SHA-256; each record links to the archived artifact or current repository.

| Asset | Claim under test | Verdict | Record |
|---|---|---|---|
| **Bat Cave BESS** — 100 MW / 100 MWh (ERCOT, US-TX) | 100 MW active power | **Not Demonstrated** — peak observed 72.61 MW | [10.5281/zenodo.21401795](https://doi.org/10.5281/zenodo.21401795) |
| **Bat Cave BESS** | 100 MWh energy capacity | **Not Demonstrated** — largest continuous discharge 58.0 MWh | [10.5281/zenodo.21401795](https://doi.org/10.5281/zenodo.21401795) |
| **Bat Cave BESS** | SoC telemetry consistency | **Inconsistent** per frozen rule; field definition **Deferred** | [10.5281/zenodo.21401795](https://doi.org/10.5281/zenodo.21401795) |
| **esVolta Anole ESS** — 240 MW / 480 MWh (ERCOT, US-TX) | 240 MW active power | **Demonstrated** | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| **esVolta Anole ESS** | 480 MWh energy capacity | **Demonstrated** | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| **esVolta Anole ESS** | SoC telemetry consistency | **Inconsistent** per frozen rule; field semantics **Deferred** | [10.5281/zenodo.21304135](https://doi.org/10.5281/zenodo.21304135) |
| **Pillswood BESS** — 98 MW / 196 MWh (Elexon, GB) | 98 MW active power | **Demonstrated** | [repository](https://github.com/VolMax-Studio/volmax-gb-bess-audit) |
| **Pillswood BESS** | 196 MWh energy capacity | **Verified with Limitations** (bounded) | [repository](https://github.com/VolMax-Studio/volmax-gb-bess-audit) |
| **ECO STOR Bollingstedt** — 103.5 MW (DE) | Physical grid limits | **Verified with Limitations** — 180 deviations, 0.47% of intervals | [10.5281/zenodo.21135861](https://doi.org/10.5281/zenodo.21135861) |
| **ECO STOR Bollingstedt** | Regime shift, July 2025 | **Verified with Limitations** — changepoint 5 July 2025 | [10.5281/zenodo.21135861](https://doi.org/10.5281/zenodo.21135861) |
| **AEMO NEM fleet** — 16 units ≥50 MW (AU) | 5-minute dispatch conformance | **Verified with Limitations** | [10.5281/zenodo.21190093](https://doi.org/10.5281/zenodo.21190093) |

### Pillswood archive note

The archived record is v1.0 (July 2026); the repository is at v2.4 and carries subsequent L0 corrections. The repository is the current state; the archive is the timestamped original. Both are public.

## Market measurement

These are descriptive baselines of public electricity markets. They pass no verdict on any operator or asset.

| # | Market | Measure | Record |
|---|---|---|---|
| 001 | AEMO NEM | Scarcity duration baseline, 13 months | [10.5281/zenodo.21693239](https://doi.org/10.5281/zenodo.21693239) |
| 002 | ERCOT | Scarcity duration baseline, 13 months | [10.5281/zenodo.21693245](https://doi.org/10.5281/zenodo.21693245) |
| 003 | ENTSO-E | Imbalance price duration baseline, 6 zones | [10.5281/zenodo.21693254](https://doi.org/10.5281/zenodo.21693254) |
| 004 | GB (Elexon BMRS) | BESS duration baseline, 13 months | [10.5281/zenodo.21693262](https://doi.org/10.5281/zenodo.21693262) |
| 005 | ENTSO-E | Cross-border physical flow dynamics | [10.5281/zenodo.21693276](https://doi.org/10.5281/zenodo.21693276) |

## Verdict vocabulary

**Demonstrated · Verified · Verified with Limitations · Inconsistent · Not Demonstrated · Not Verified · Deferred · Unfalsifiable-as-Stated**

The vocabulary is defined by the protocol rather than selected ad hoc per report.
