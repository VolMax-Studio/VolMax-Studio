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

VolMax Edge Intelligence operates as an **Evidence-Driven Runtime** that presides over task feasibility before routing execution parameters. Rather than asserting universal adaptation capabilities, the runtime categorizes workloads into high-feasibility, regime-adaptable, and feature-constrained regimes based on empirical verification:

```
                            [ Incoming Edge Telemetry ]
                                         │
                          Is Task Class Edge-Adaptable?
                    ┌────────────────────┼────────────────────┐
                    ▼                    ▼                    ▼
          [ High Feasibility ]  [ Regime-Adaptable ]  [ Feature-Constrained ]
          (Feedforward Waveform) (Charging Policy Shift) (Sparse Cross-Cell SOH)
                    │                    │                    │
             Route to Edge         Trigger Regime         Flag Risk Guard /
              Adaptation            Alert (2.39x)         Class F4 (1.04x)
```

---

## 2. General Feasibility Matrix (High-Level Classification)

| Task Category | Signal Character | Adaptation / Detection | Status Tag | Feasibility & Boundary Summary |
| :--- | :--- | :--- | :--- | :--- |
| **PQ Waveform Classification** | Feedforward Signal | **Joint Domain Rehearsal** | **`[MEASURED: PASS]`** | **High Feasibility.** Feedforward waveform classification exhibits strong adaptability ($99.14\%$ Macro F1) when domain rehearsal buffers preserve historical features. |
| **PQ Waveform Classification** | Feedforward Signal | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | **Moderate Feasibility.** $O(1)$ adaptation recovers local shifts ($61.10\%$), but exhibits generalization decay under un-rehearsed phase shifts ($86.94\%$). |
| **Operational Regime Shift** | Battery Charging Policy | **Mahalanobis Input Distance** | **`[MEASURED: WORKS]`** | **Regime-Adaptable ($2.39\times$ Separation).** Mahalanobis distance in feature space cleanly detects operational protocol shifts across 124 Severson cells (`b1` vs `b2`/`b3`). |
| **Cross-Cell SOH Degradation** | Aggregate Telemetry | **Input-Space Distance / LoRA** | **`[MEASURED: FEATURE-CONSTRAINED]`** | **Feature-Constrained ($1.04\times$ In-Batch Ratio).** Public aggregate cycling features (`temp`, `IR`, `capacity`) do NOT encode per-cell degradation variance under identical charging policies. Requires cell-level BMS telemetry. |
| **On-Device NILM Disaggregation** | High-Freq Waveform | **Forward-Only / LoRA** | **`[SPECULATION]`** | **Unmeasured Concept.** On-device disaggregation without raw telemetry transmission remains an un-benchmarked roadmap target. |

---

## 3. The Model Risk Detector Proposition

> [!CAUTION]
> **Core Value Proposition & Product Specification:**  
> The VolMax Edge Runtime functions as an **Avionics-Grade Feasibility & Risk Detector Layer**. From public aggregate telemetry, it certifies **Operational Regime Shifts ($2.39\times$)** (alerting when asset charging policy deviates from baseline), while flagging **Per-Cell Internal Drift ($1.04\times$)** as `Class F4` (uncalibrated from public features alone).

---
*Specification Version: 2.1.0 (Public Framework Specification) | Date: 2026-07-27 | VolMax Studio*
