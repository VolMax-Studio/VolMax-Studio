# VolMax Studio Lab

**Independent verification of technical claims. Frozen rules, reproducible code, bounded verdicts.**

We build public research artifacts around a narrow question:

> **What does the available evidence actually support — and where does it stop?**

Our work combines preregistered tests, reproducible computation, formal verification where appropriate, explicit provenance, and bounded conclusions.

Two ERCOT battery assets illustrate the method: the same public telemetry source and the same frozen rules produced opposite outcomes. esVolta Anole demonstrated its 240 MW / 480 MWh nameplate under the preregistered tests; Bat Cave did not demonstrate its 100 MW claim, with a peak observed value of 72.61 MW.  
→ [Full audit registry](AUDIT_REGISTRY.md)

## Current research

### P10 — proof-carrying adjudication

[`p10-underdetermination-profile`](https://github.com/VolMax-Studio/p10-underdetermination-profile) is a **release candidate** for a third-party-verifiable binding of `NotDemonstrated(reason=underdetermined)`.

A conforming receipt carries two witness worlds that are compatible with the same closed evidence set but produce different values for the same frozen claim. The repository includes the profile specification, Lean reference kernel, exact artifact manifests, and independent gate reports.

[`p10-core`](https://github.com/VolMax-Studio/p10-core) contains the Lean-oriented core work behind the broader P10 verification method.

### Representation lifting

[`representation-lifting-s1`](https://github.com/VolMax-Studio/representation-lifting-s1) is a **preregistered controlled experiment** testing whether representation-first formalization can discover useful structure on externally sampled blind theorem statements and amortize setup cost across related theorem families.

The experimental architecture, verifier, selection custody, negative control, and analysis rules are public. The blind evaluation remains pending; no outcome is claimed here.

### Formal mathematics & scientific reproduction

[`primitive-composition-square-content-s1`](https://github.com/VolMax-Studio/primitive-composition-square-content-s1) — Lean 4 formalization of gcd structure and square content in compositions of primitive Pythagorean triples.

[`rotation-gap-fano-lean-certificates`](https://github.com/VolMax-Studio/rotation-gap-fano-lean-certificates) — Lean certificates associated with an independent reproduction of bounded Willow Fano-statistics claims.

## Energy-system verification

We audit public operational claims about grid-scale storage against independent public telemetry from ERCOT, AEMO NEM, Elexon/BMRS, and continental European sources.

The detailed records, including adverse and limited verdicts, are preserved in the [audit registry](AUDIT_REGISTRY.md).

[`Open-Market-Notes`](https://github.com/VolMax-Studio/Open-Market-Notes) contains reproducible descriptive baselines of public electricity-market telemetry.

## Method

A typical investigation follows:

`claim pinned verbatim → falsifiable sub-claims → rules frozen before data → licence/provenance check → execution → verification → limitations → bounded verdict → archived package`

Verdicts come from a fixed vocabulary:

**Demonstrated · Verified · Verified with Limitations · Inconsistent · Not Demonstrated · Not Verified · Deferred · Unfalsifiable-as-Stated**

A formal proof establishes derivability inside a formal system. It does **not** by itself establish that the formal statement captures the intended real-world claim. That semantic boundary is stated rather than assumed.

Cryptographic hashes and signatures establish artifact identity and provenance; they do not establish semantic correctness.

## Reproducibility

Our own errors remain visible in the public record. If a preregistered hypothesis is invalidated by a scoping error, it is voided rather than silently re-anchored to the observed data.

If you reproduce different numbers from ours, open an issue. We will re-run the analysis and publish the correction.

---

**Ivan Nestorov** · VolMax Studio Lab d.o.o. · Serbia  
[ORCID 0009-0006-7940-9539](https://orcid.org/0009-0006-7940-9539) · volmax.core@gmail.com · [www.volmax-studio.rs](https://www.volmax-studio.rs)
