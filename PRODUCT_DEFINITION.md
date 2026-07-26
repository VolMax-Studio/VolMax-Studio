# Product Definition — VolMax Edge Runtime (`PRODUCT_DEFINITION.md`)

> [!IMPORTANT]
> **Executive Summary:**  
> **VolMax Edge Runtime** is an on-device, memory-constrained adaptive ML runtime engineered for distributed power hardware (Inverters, Smart Meters, Battery Management Systems). It enables local adaptation without backpropagation, operating strictly within $O(1)$ memory depth without transmitting raw operational telemetry to the cloud.

---

## 1. Core Technological Differentiation (On-Device Adaptation)

| Dimension | Standard Edge ML (TFLite Micro / ONNX) | VolMax Edge Runtime |
| :--- | :--- | :--- |
| **Execution Mode** | Static On-Device Inference Only | **On-Device Adaptation without Backpropagation** |
| **Memory Footprint** | Fixed model size; requires backprop GPU buffer for adaptation | **$O(1)$ Memory Depth (Forward-Only / INT4 Compatible)** |
| **Telemetry Transport** | Raw high-frequency telemetry streamed to cloud | **Local Classification & Derating Output Only** |
| **Privacy & Latency** | Cloud-roundtrip latency & data privacy risk | **Sub-millisecond local execution & zero telemetry leak** |

### Empirical Boundary Specification:
As established in the VolMax INT4 Benchmark (Zenodo DOI: [`10.5281/zenodo.21010289`](https://doi.org/10.5281/zenodo.21010289)):
* **Empirical Strength:** Forward-only adaptation excels on **feedforward signal classification** tasks under $O(1)$ memory constraint (holding $0.76 - 0.86$ accuracy with a $4-5\times$ memory reduction compared to standard LoRA).
* **Honest Limit:** Forward-only adaptation fails on noise-heavy regression OOD transfer (e.g., attention/SOH regression collapses under seed variance). VolMax enforces a strict boundary: forward-only is applied exclusively where feedforward classification is proven to hold.

---

## 2. Module Roadmap & Empirical Phasing

```
[Phase 1: Module 1]  ──> Power Quality & Disturbance Classification (Inverter / Meter Level)
[Phase 2: Module 2]  ──> LoRA-adapted SOH / RUL Degradation Tracking (BMS Level)
[Phase 3: Module 3]  ──> On-Device NILM Disaggregation (Smart Meter Level)
```

### Module 1: Power Quality & Anomaly Classification (Current Priority)
* **Hardware Target:** Inverter / Microgrid Controller / Power Quality Monitor.
* **Core Function:** On-device real-time classification of 17 power quality disturbance types (sags, swells, harmonics, transients) using localized forward-only adaptation.
* **Empirical Selection Rationale:** Selected as Module 1 because it represents feedforward signal classification—the exact category where forward-only adaptation was empirically proven to hold in the INT4 benchmark.
* **Baseline Lineage:** Leverages physical feature extraction from `PowerQuality_Classifier_Portfolio`.

### Module 2: SOH / RUL Degradation Tracking (Phased Architecture)
* **Hardware Target:** Battery Management System (BMS) / Battery Energy Storage System (BESS) Node.
* **Mechanism:** LoRA-style fine-tuning architecture (not forward-only), matching the empirical finding that battery regression requires structured gradient routing for noise-heavy OOD transfer.

### Module 3: Non-Intrusive Load Monitoring (NILM)
* **Hardware Target:** Smart Meter / Edge Energy Gateway.
* **Mechanism:** On-device disaggregation of high-frequency load signatures without streaming private household waveforms off-edge.

---

## 3. Telemetry Output & Edge Privacy Guarantee

VolMax Edge Runtime strictly prevents raw SCADA/waveform telemetry from leaving the physical hardware:
* **Suppressed:** High-frequency raw voltage/current waveforms, raw BMS cell voltages.
* **Emitted:** Discrete local state evaluations (e.g. `PQ_DISTURBANCE_FLAG`, `DERATING_RECOMMENDATION_KW`, `SOH_BAND_ESTIMATE`).
* **VPP Benefit:** Enables Virtual Power Plant (VPP) aggregators to coordinate thousands of distributed assets without incurring cloud bandwidth bills or violating privacy regulations.

---

## 4. Built-in P10 Verification Integration

VolMax Edge Runtime incorporates P10 Verification directly into the runtime:
* **Built-in Quality Proof:** P10 verification acts as an embedded performance certificate proving the exact bounds under which the local edge module operates.
* **Honest Boundary Enforcement:** The runtime self-reports performance boundaries, ensuring edge models do not issue false claims outside proven operating envelopes.

---

## 5. Explicit Non-Goals

1. **Not a Generic Inference Engine:** VolMax Edge Runtime does not compete with TFLite Micro or ONNX for generic static inference; it specifically delivers **on-device adaptation without backpropagation**.
2. **Not a Third-Party Audit Agency:** VolMax does not act as a passive news outlet for public market data; audits serve as credibility anchors (`production_backlog.md`), while the Edge Runtime is the primary technology product.

---

## 6. Narrative Continuity

VolMax Edge Runtime directly elevates the existing VolMax positioning:
* **Existing Narrative:** *"VolMax — Independent Verification & Measurable Energy Transition."*
* **Elevated Product Narrative:** *"VolMax — On-Device Adaptive Intelligence for Distributed Power Hardware with Built-In Performance Proof."*

---
*Document Version: 1.0.0 | Date: 2026-07-26 | VolMax Studio Lead Engineer*
