# VolMax Edge Adaptation Boundaries (`ADAPTATION_BOUNDARIES.md`)

> [!IMPORTANT]
> **P10 Empirical Rigor Mandate:**  
> This boundary map strictly demarcates **empirically measured evidence** from **unmeasured theoretical assumptions**. Every entry carries an explicit `[MEASURED]` tag (anchored by DOI or Git commit SHA) or an `[ASSUMED]` tag (flagged for future verification).

---

## 1. Empirical Adaptation Matrix

| Task Category | Signal Character | Adaptation Mechanism | Status Tag | Empirical Findings & Proven Boundaries | Anchor Reference |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **PQ Waveform Classification** | Feedforward Signal | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | **Gap Recovery $R_{\text{gap-A1}} = 61.10\%$** on local physical regime shift, BUT **Shift B Guard = $86.94\%$** (failed $\ge 90\%$ threshold). Single-domain adaptation causes feature over-fitting to local frequency drift. | Git Commit [`ec2bcd0`](file:///home/volmax-studio/volmax-projects/iot2/PORTFOLIO/VolMax_Edge_PQ/RESULTS_1A_v2.md) |
| **PQ Waveform Classification** | Feedforward Signal | **Full Backprop Re-train** | **`[MEASURED: FAIL]`** | **Shift B Collapse ($49.14\%$ Macro F1)**. Full backpropagation re-training on Shift A1 severely degrades general feature representation on unseen Shift B ($>50\%$ drop relative to static baseline $99.89\%$). | Measured Live (`train_and_evaluate_v2.py`) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **Forward-Only** ($O(1)$ Memory) | **`[MEASURED: FAIL]`** | Forward-only adaptation collapses under seed variance on attention/SOH regression under INT4 constraints. Proven non-viable for regression. | Zenodo DOI [`10.5281/zenodo.21010289`](https://doi.org/10.5281/zenodo.21010289) |
| **SOH / RUL Degradation** | Noise-Heavy Regression | **LoRA-style Fine-tuning** | **`[ASSUMED: Pending]`** | Hypothesis: Low-Rank Adapter routing accommodates noise-heavy regression OOD transfer. *Requires pre-registered empirical verification.* | Unmeasured Hypothesis |
| **On-Device NILM Disaggregation** | High-Freq Waveform | **Forward-Only / LoRA** | **`[ASSUMED: Pending]`** | Disaggregation of household loads without raw telemetry transmission. *Requires pre-registered empirical verification.* | Unmeasured Hypothesis |

---

## 2. Empirical Discoveries & Architectural Implications

### Discovery 1: Single-Domain Adaptation Trade-off
* **Physical Finding:** On feedforward signal classification (PQ waveforms), forward-only adaptation recovers **$61.10\%$ of lost physical regime accuracy** without backpropagating feature layers.
* **Generalization Trade-off:** Both forward-only adaptation AND full backpropagation re-training suffer from single-domain feature distortion. Re-training feature representations to fit local frequency drift (Shift A1) inherently degrades accuracy on un-adapted phase imbalance (Shift B).

### Discovery 2: Boundary Between Classification & Regression
* **Feedforward Classification:** Forward-only adaptation is mathematically viable ($R_{\text{gap}} \ge 60\%$), but requires multi-domain regularization or elastic weight consolidation (EWC) to preserve cross-domain generalization.
* **Stochastic Regression (SOH):** Forward-only adaptation fails entirely. SOH estimation requires structured gradient routing (LoRA / adapter rank decomposition).

---

## 3. Known Unknowns & Unmeasured Hypotheses (Section 3)

The following claims are **UNMEASURED** and MUST NOT be presented as verified capabilities until pre-registered experiments issue a verified `PASS`:

1. **`[UNMEASURED]` LoRA Performance on SOH Regression:** LoRA parameter-efficient fine-tuning has not yet been benchmarked on localized BMS cell telemetry within this edge runtime repository.
2. **`[UNMEASURED]` Field Performance on Physical Oscilloscope Recordings:** All PQ measurements to date utilize synthetic IEEE 1159 waveform synthesis. Performance on physical hardware noise remains unmeasured.
3. **`[UNMEASURED]` Multi-Task Elastic Weight Consolidation (EWC):** Whether EWC can prevent Shift B generalization collapse during forward-only adaptation remains an unverified hypothesis.

---
*Document Version: 1.0.0 | Date: 2026-07-26 | VolMax Studio Lead Engineer*
