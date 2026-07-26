# VolMax Edge Adaptation Boundaries (`ADAPTATION_BOUNDARIES.md`)

> [!IMPORTANT]
> **P10 Epistemological Standard & Mandate:**  
> This boundary map enforces strict evidence classification across all VolMax technical specifications. Every capability statement MUST carry an explicit status tag:
> - **`[MEASURED]`**: Empirical evidence verified via reproducible code execution (with Git SHA / DOI anchor).
> - **`[DERIVED]`**: Mathematically or logically derived from measured primitives.
> - **`[HYPOTHESIS]`**: Mechanistically grounded expectation backed by preliminary benchmarks.
> - **`[SPECULATION]`**: Untested architectural vision or un-benchmarked roadmap target.
> - **`[SCOPE-LIMIT]`**: Explicitly acknowledged empirical boundary (e.g. synthetic testbed limitation).

---

## 1. Empirical Adaptation Matrix

| Task Category | Signal Character | Adaptation Mechanism | Status Tag | Empirical Findings & Proven Boundaries | Anchor Reference |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **LoRA-style Fine-tuning** | **`[MEASURED: FAIL]`** | **Failed on Real NASA Data (Protocol v2).** Synthetic Arrhenius formula yielded $R^2 = +0.62$, BUT real NASA Ames cross-cell telemetry ($N=150$, `B0007`/`B0018`) caused seed collapse (average $R^2 = -0.6063$). | Git Commit [`f1f91f5`](file:///home/volmax-studio/volmax-projects/iot2/PORTFOLIO/VolMax_Edge_SOH/RESULTS_2_v2_RealSOH.md) |
| **PQ Waveform Classification** | Feedforward Signal | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | **Physical Gap Recovery $R_{\text{gap-A1}} = 61.10\%$** on local physical regime shift, BUT **Shift B Guard = $86.94\%$** (failed pre-registered deployment criterion of $\ge 90\%$). Demonstrates generalization decay on decoupled phase shifts. | Git Commit [`ec2bcd0`](file:///home/volmax-studio/volmax-projects/iot2/PORTFOLIO/VolMax_Edge_PQ/RESULTS_1A_v2.md) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop (Joint Rehearsal)** | **`[MEASURED: PASS]`** | **Shift B Macro F1 = $99.14\%$**. Full backpropagation with joint domain rehearsal ($D_0 + D_{\text{shift-A1}}$) maintained generalization across evaluated synthetic domains ($D_0, D_{\text{shift-A1}}, D_{\text{shift-B}}$). | Measured Live (`train_and_evaluate_v2.py`) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop (Single-Domain FT)** | **`[MEASURED: DECAY]`** | **Low-LR Fine-tuning F1 = $74.47\%$**, **Un-regularized Retrain F1 = $49.14\%$**. Demonstrates classic catastrophic forgetting when retrained on a single domain without rehearsal. | Measured Live (`train_and_evaluate_v2.py`) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | Forward-only adaptation collapses under seed variance on attention/SOH regression ($R^2 = -8.44$ synthetic, $R^2 = -0.21$ real NASA data). | Zenodo DOI [`10.5281/zenodo.21010289`](https://doi.org/10.5281/zenodo.21010289) |
| **On-Device NILM Disaggregation** | High-Freq Waveform | **Forward-Only / LoRA** | **`[SPECULATION]`** | Concept: Disaggregation of household loads without raw telemetry transmission. *Unmeasured architectural vision.* | Unmeasured Roadmap |

---

## 2. Established General Findings

> [!CAUTION]
> **Core Scientific Discovery:**  
> **1. Task-Class Feasibility Boundary:** Feedforward waveform classification (PQ) exhibits high signal adaptability ($99.14\%$ joint rehearsal, $86.94\%$ forward-only). Conversely, sparse small-sample cross-cell regression (SOH, $N=150$) triggers cross-cell transfer collapse across ALL evaluated adaptation mechanisms (Static $-0.03$, Forward-Only $-0.21$, LoRA $-0.60$).  
> **2. Continual Adaptation Decay:** Single-domain adaptation without knowledge preservation causes catastrophic forgetting under independent distribution shifts ($49.14\% \to 74.47\% \to 86.94\% \to 99.14\%$).

### Empirical Generalization Spectrum on Unseen Shift B ($D_{\text{shift-B}}$):

$$\begin{array}{rcc}
\text{Naive Un-regularized Retraining (Single Domain):} & \mathbf{49.14\%} & \text{(Catastrophic Forgetting)} \\
\text{Low-LR Fine-Tuning (Single Domain):} & \mathbf{74.47\%} & \text{(Partial Feature Decay)} \\
\text{Forward-Only Adaptation } (O(1)\text{ Memory Depth}): & \mathbf{86.94\%} & \text{(Moderate Decay — Failed } \ge 90\%\text{ Guard)} \\
\text{Joint Domain Rehearsal (Backprop } D_0 + D_{\text{A1}}): & \mathbf{99.14\%} & \text{(Preserved Generalization)}
\end{array}$$

### Architectural Takeaways:
1. **The Synthetic-to-Field Boundary:** Synthetic parametric formulas (Arrhenius / IEEE 1159) can mask underlying parameter sensitivity. Validating against real hardware datasets (NASA Ames cycling telemetry) is mandatory prior to declaring a `PASS`.
2. **VolMax Edge Runtime Proposition:** The runtime first presides over **Task Class Feasibility** before routing execution to Joint Rehearsal, LoRA, or Static modes.

---

## 3. Known Unknowns & Scope Boundaries

1. **`[SCOPE-LIMIT]` Hardware Noise & Sample-Size Limitation:** LoRA fine-tuning under NASA Ames protocol v2 ($N=150$, cells `B0007`/`B0018`) exhibits parameter instability without historical domain rehearsal buffers.
2. **`[SCOPE-LIMIT]` Synthetic Signal Verification Gate:** Real-world physical oscilloscope validation for PQ waveform classification remains the final verification gate before commercial deployment.

---
*Document Version: 1.5.0 | Date: 2026-07-26 | VolMax Studio Lead Engineer*
