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
| **PQ Waveform Classification** | Feedforward Signal | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | **Physical Gap Recovery $R_{\text{gap-A1}} = 61.10\%$** on local physical regime shift, BUT **Shift B Guard = $86.94\%$** (failed pre-registered deployment criterion of $\ge 90\%$). Demonstrates generalization decay on decoupled phase shifts. | Git Commit [`ec2bcd0`](file:///home/volmax-studio/volmax-projects/iot2/PORTFOLIO/VolMax_Edge_PQ/RESULTS_1A_v2.md) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop (Joint Rehearsal)** | **`[MEASURED: PASS]`** | **Shift B Macro F1 = $99.14\%$**. Full backpropagation with joint domain rehearsal ($D_0 + D_{\text{shift-A1}}$) maintained generalization across the evaluated synthetic domains ($D_0, D_{\text{shift-A1}}, D_{\text{shift-B}}$). | Measured Live (`train_and_evaluate_v2.py`) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop (Single-Domain FT)** | **`[MEASURED: DECAY]`** | **Low-LR Fine-tuning F1 = $74.47\%$**, **Un-regularized Retrain F1 = $49.14\%$**. Demonstrates classic catastrophic forgetting when retrained on a single domain without rehearsal. | Measured Live (`train_and_evaluate_v2.py`) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | Forward-only adaptation collapses under seed variance on attention/SOH regression under INT4 constraints. Proven non-viable for noise-heavy regression. | Zenodo DOI [`10.5281/zenodo.21010289`](https://doi.org/10.5281/zenodo.21010289) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **LoRA-style Fine-tuning** | **`[HYPOTHESIS]`** | Expectation: Low-Rank Adapter routing accommodates noise-heavy regression OOD transfer based on INT4 benchmark findings. *Pending empirical verification.* | Mechanistic Hypothesis |
| **On-Device NILM Disaggregation** | High-Freq Waveform | **Forward-Only / LoRA** | **`[SPECULATION]`** | Concept: Disaggregation of household loads without raw telemetry transmission. *Unmeasured architectural vision.* | Unmeasured Roadmap |

---

## 2. Established General Findings

> [!CAUTION]
> **Core Scientific Discovery:**  
> **Single-domain continual adaptation without knowledge preservation leads to measurable degradation under independent distribution shifts.**

### Empirical Generalization Spectrum on Unseen Shift B ($D_{\text{shift-B}}$):

$$\begin{array}{rcc}
\text{Naive Un-regularized Retraining (Single Domain):} & \mathbf{49.14\%} & \text{(Catastrophic Forgetting)} \\
\text{Low-LR Fine-Tuning (Single Domain):} & \mathbf{74.47\%} & \text{(Partial Feature Decay)} \\
\text{Forward-Only Adaptation } (O(1)\text{ Memory Depth}): & \mathbf{86.94\%} & \text{(Moderate Decay — Failed } \ge 90\%\text{ Guard)} \\
\text{Joint Domain Rehearsal (Backprop } D_0 + D_{\text{A1}}): & \mathbf{99.14\%} & \text{(Preserved Generalization)}
\end{array}$$

### Architectural Takeaways:
1. **Causal Attribution (P10 Frame):** One plausible explanation for forward-only degradation on Shift B ($86.94\%$) is the absence of historical domain rehearsal buffers in $O(1)$ memory mode. The exact causal mechanism has not yet been experimentally isolated.
2. **Runtime Value Proposition:** The core product value of the VolMax Edge Runtime is NOT a single "magic" adaptation algorithm, but an **evidence-driven runtime that routes tasks to the appropriate strategy** based on measured boundary conditions (e.g. Joint Rehearsal vs LoRA vs Forward-Only).

---

## 3. Known Unknowns & Scope Boundaries

1. **`[SCOPE-LIMIT]` Synthetic Benchmark Boundary:** All PQ classification metrics were measured using parametric IEEE Std 1159/1459 AC waveform synthesis. Performance on physical hardware oscilloscope recordings from real inverters remains unmeasured.
2. **`[HYPOTHESIS]` LoRA Performance on SOH Regression:** LoRA parameter-efficient fine-tuning has not yet been benchmarked on localized BMS cell telemetry within this repository.
3. **`[HYPOTHESIS]` Elastic Weight Consolidation (EWC) for Forward-Only:** Whether EWC or adapter anchoring can prevent Shift B generalization decay without storing raw rehearsal buffers remains an unverified hypothesis.

---
*Document Version: 1.2.0 | Date: 2026-07-26 | VolMax Studio Lead Engineer*
