# VolMax Edge Adaptation Boundary Specification (`ADAPTATION_BOUNDARIES.md`)

> [!IMPORTANT]
> **P10 Verification Doctrine & Public Specification:**  
> This specification enforces strict evidence classification across all VolMax Edge Intelligence architecture documents. Every claim MUST carry an explicit epistemological tag:
> - **`[MEASURED]`**: Empirical evidence verified via reproducible code execution on target telemetry.
> - **`[DERIVED]`**: Mathematically or logically derived from measured primitives.
> - **`[HYPOTHESIS]`**: Mechanistically grounded expectation undergoing active benchmark verification.
> - **`[SPECULATION]`**: Untested architectural vision or roadmap target.
> - **`[SCOPE-LIMIT]`**: Explicitly acknowledged empirical boundary (e.g., protocol or dataset constraint).

---

## 1. Edge Feasibility Boundary Framework

VolMax Edge Intelligence operates as an **Evidence-Driven Runtime** that presides over task feasibility before routing execution parameters. Rather than asserting universal adaptation capabilities, the runtime categorizes workloads into high-feasibility and low-feasibility regimes based on empirical verification:

```
                            [ Incoming Edge Task ]
                                      │
                         Is Task Class Edge-Adaptable?
                                ┌─────┴─────┐
                                ▼           ▼
                        [ High Feasibility ]  [ Low Feasibility / High Risk ]
                         (Feedforward Waveforms) (Sparse Cross-Cell Telemetry)
                                │           │
                         Route to Edge      Trigger Model Risk Guard /
                          Adaptation         Maintain Static Baseline
```

---

## 2. General Feasibility Matrix (High-Level Classification)

| Task Category | Signal Character | Adaptation Mechanism | Status Tag | Feasibility & Boundary Summary |
| :--- | :--- | :--- | :--- | :--- |
| **PQ Waveform Classification** | Feedforward Signal | **Joint Domain Rehearsal** | **`[MEASURED: PASS]`** | **High Feasibility.** Feedforward waveform classification exhibits strong adaptability when domain rehearsal buffers preserve historical features. |
| **PQ Waveform Classification** | Feedforward Signal | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | **Moderate Feasibility.** $O(1)$ adaptation recovers local shifts but exhibits generalization decay under un-rehearsed phase shifts. |
| **SOH / RUL Degradation** | Sparse Telemetry | **LoRA / Forward-Only** | **`[MEASURED: FAIL]`** | **Low Feasibility / High Risk.** Sparse cross-cell telemetry ($N < 200$) exhibits high parameter variance across cells. The runtime flags this regime for Risk Guard intervention. |
| **On-Device NILM Disaggregation** | High-Freq Waveform | **Forward-Only / LoRA** | **`[SPECULATION]`** | **Unmeasured Concept.** On-device disaggregation without raw telemetry transmission remains an un-benchmarked roadmap target. |

---

## 3. The Model Risk Detector Proposition

> [!CAUTION]
> **Core Value Proposition:**  
> Rather than deploying un-verified adaptation models to critical 100MW BESS assets, the VolMax Edge Runtime functions as a **Feasibility & Risk Detector Layer**. It detects when an edge adaptation protocol enters an unreliable regime (e.g., sparse cross-cell transfer), protecting asset managers from un-quantified model drift.

---
*Specification Version: 2.0.0 (Public Framework Specification) | Date: 2026-07-26 | VolMax Studio*
