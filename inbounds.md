# Inbound Partner Notes & Commercial Positioning (`inbounds.md`)

> [!IMPORTANT]
> **Partner Entity: Shelton Tang (EcoWatt)**  
> - **Date Recorded:** `2026-07-26`  
> - **Source Anchor:** Shelton Tang Public Post / EcoWatt Integration & Intersolar Europe Discussions  
> - **Exact Quotes:**  
>   *"Continuous adaptation — the software needs to evolve with them. A 100MW/200MWh asset behaves completely differently depending on its market application."*  
>   *"PV, PCS, battery, and EMS must be designed as one system. Hardware is the muscle, but smart, adaptive EMS control logic is the brain."*

---

## 1. EcoWatt Market Context & Vendor Scale Analysis

* **Market Footprint:** Established EMS vendor with commercial products deployed (e.g. Outdoor EMS Cabinet), active presence at Intersolar Europe, and engagements with Tier-1 OEMs (CATL, BYD, Jinko, Trina).
* **Existing Stack:** EcoWatt already maintains an "Edge Control" software layer ("real-time optimization, forecasting, cloud analytics, and edge control").
* **Strategic Implication:** Pitching a generic "edge ML module" is ineffective because an established EMS vendor already has internal software algorithms.

---

## 2. Refined VolMax Commercial Value Proposition: Independent P10 Verification Layer

> [!CAUTION]
> **The Independent Audit Advantage:**  
> Internal vendor engineering teams rarely audit or publish their own algorithm failure modes. VolMax does not compete as "another ML algorithm"; VolMax provides an **Independent Empirical Verification Layer (P10 Standard)** that audits, stress-tests, and certifies edge control adaptation algorithms before deployment to 100MW BESS assets.

* **Unique Differentiator:** Catching synthetic false-positive passes (e.g., catching LoRA SOH synthetic failure on real hardware) before asset deployment to protect vendor reputation in Tier-1 BESS projects.
* **Refined Outreach Hook (Post-Pass Verification):**  
  > *"Saw your post on continuous adaptation for 100MW assets. Established EMS edge controllers often suffer from synthetic parameter masking. We build the independent P10 empirical verification layer that stress-tests edge adaptation protocols on real hardware telemetry—certifying where edge adaptation works and isolating where it collapses before deployment."*

---

## 3. Engagement Prerequisites & Readiness Gate

1. **Prerequisite:** Do NOT initiate outreach prematurely without verified real-world hardware data anchors.
2. **Current Gate:** Complete real-world physical PQ waveform Joint Rehearsal verification to secure the first non-synthetic `[MEASURED: PASS]` anchor.
