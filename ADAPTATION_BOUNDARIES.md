# VolMax Edge Adaptation Boundaries (`ADAPTATION_BOUNDARIES.md`)

> [!IMPORTANT]
> **P10 Epistemological Standard & Mandate:**  
> This boundary map enforces strict evidence classification across all VolMax technical specifications. Every capability statement MUST carry an explicit status tag:
> - **`[MEASURED]`**: Empirical evidence verified via reproducible code execution (with Git SHA / DOI anchor).
> - **`[DERIVED]`**: Mathematically or logically derived from measured primitives.
> - **`[HYPOTHESIS]`**: Mechanistically grounded expectation backed by preliminary benchmarks.
> - **`[SPECULATION]`**: Untested architectural vision or un-benchmarked roadmap target.

---

## 1. Empirical Adaptation Matrix

| Task Category | Signal Character | Adaptation Mechanism | Status Tag | Empirical Findings & Proven Boundaries | Anchor Reference |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **PQ Waveform Classification** | Feedforward Signal | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | **Physical Gap Recovery $R_{\text{gap-A1}} = 61.10\%$** on local physical regime shift, BUT **Shift B Guard = $86.94\%$** (failed $\ge 90\%$ threshold). Single-domain adaptation exhibits generalization decay on decoupled phase shifts. | Git Commit [`ec2bcd0`](file:///home/volmax-studio/volmax-projects/iot2/PORTFOLIO/VolMax_Edge_PQ/RESULTS_1A_v2.md) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop (Joint Rehearsal)** | **`[MEASURED: PASS]`** | **Shift B Macro F1 = $99.14\%$**. Full backpropagation with joint domain rehearsal ($D_0 + D_{\text{shift-A1}}$) maintains complete cross-domain generalization. | Measured Live (`train_and_evaluate_v2.py`) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop (Single-Domain FT)** | **`[MEASURED: DECAY]`** | **Low-LR Fine-tuning F1 = $74.47\%$**, **Un-regularized Retrain F1 = $49.14\%$**. Demonstrates classic catastrophic forgetting when retrained on a single domain without rehearsal. | Measured Live (`train_and_evaluate_v2.py`) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | Forward-only adaptation collapses under seed variance on attention/SOH regression under INT4 constraints. Proven non-viable for noise-heavy regression. | Zenodo DOI [`10.5281/zenodo.21010289`](https://doi.org/10.5281/zenodo.21010289) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **LoRA-style Fine-tuning** | **`[HYPOTHESIS]`** | Expectation: Low-Rank Adapter routing accommodates noise-heavy regression OOD transfer based on INT4 benchmark findings. *Pending empirical verification.* | Mechanistic Hypothesis |
| **On-Device NILM Disaggregation** | High-Freq Waveform | **Forward-Only / LoRA** | **`[SPECULATION]`** | Concept: Disaggregation of household loads without raw telemetry transmission. *Unmeasured architectural vision.* | Unmeasured Roadmap |

---

## 2. Empirical Discoveries & Architectural Reality

### Discovery 1: Catastrophic Forgetting in Single-Domain Adaptation
* **Un-regularized Retraining Fallacy:** Retraining backpropagation exclusively on Shift A1 without domain rehearsal causes catastrophic forgetting ($49.14\%$ F1 on Shift B).
* **Proper Backpropagation Baseline:** When backpropagation includes joint domain rehearsal ($D_0 + D_{\text{shift-A1}}$), it achieves **$99.14\%$ Macro F1** across all shifts.
* **Forward-Only Constraint:** Forward-only adaptation operates strictly in $O(1)$ memory depth without storing historical raw domain rehearsal buffers. As a result, single-domain forward-only adaptation suffers from feature decay on decoupled shifts ($86.94\%$).

### Discovery 2: Boundary Between Classification & Regression
* **Feedforward Classification:** Forward-only adaptation is partially viable ($R_{\text{gap}} \ge 60\%$), but requires elastic weight consolidation (EWC) or adapter anchoring to match joint backprop generalization.
* **Stochastic Regression (SOH):** Forward-only adaptation fails entirely. SOH estimation requires structured gradient routing (LoRA / adapter rank decomposition).

---

## 3. Known Unknowns & Unmeasured Hypotheses (Section 3)

1. **`[HYPOTHESIS]` LoRA Performance on SOH Regression:** LoRA parameter-efficient fine-tuning has not yet been benchmarked on localized BMS cell telemetry within this repository.
2. **`[SPECULATION]` Field Performance on Physical Waveforms:** All PQ measurements to date utilize synthetic IEEE 1159 waveform synthesis. Performance on physical hardware noise remains unmeasured.
3. **`[HYPOTHESIS]` Elastic Weight Consolidation (EWC) for Forward-Only:** Whether EWC can prevent Shift B generalization decay without storing raw rehearsal buffers remains an unverified hypothesis.

---
*Document Version: 1.1.0 | Date: 2026-07-26 | VolMax Studio Lead Engineer*
