# VolMax Studio Lab

**Power electronics engineer + energy ML.**

Domain-grounded open tools for grid monitoring, load disaggregation, battery diagnostics, and embedded signal processing. The edge: real electrical domain knowledge combined with the ability to code — a combination that's rare enough to matter.

---

## Active Portfolio

### [PowerQuality_Classifier_Portfolio](https://github.com/VolMax-Studio/PowerQuality_Classifier_Portfolio)
17-class power quality disturbance classifier trained on IEEE-1159 parametric data. Random Forest + feature engineering on RMS, THD, spectral components. Honest results: ~78% accuracy with full confusion matrix, per-class breakdown, and Streamlit dashboard. No synthetic inflation.

**Stack:** Python · scikit-learn · Streamlit · NumPy · SciPy

---

### [NILM_Disaggregation_Portfolio](https://github.com/VolMax-Studio/NILM_Disaggregation_Portfolio)
Energy disaggregation pipeline on real REDD data (Kolter & Johnson, 2011) — House 3, ~3 days of low-frequency smart meter measurements. Random Forest regressor with physics-informed features for refrigerator load separation from aggregate mains. Domain-aware: models standby baseline and compressor cycling separately.

**Stack:** Python · scikit-learn · pandas · matplotlib

---

### [Battery_Health_Portfolio](https://github.com/VolMax-Studio/Battery_Health_Portfolio)
Three-task diagnostics pipeline on NASA PCoE Li-ion battery data (B0005–B0018):
- **SoH regression** — R² = 0.943, MAE = 0.043 Ah (cross-battery: train B0005, test B0006)
- **RUL prediction** — RMSE = 5.7 cycles to EOL (threshold: 1.4 Ah)
- **Thermal anomaly detection** — Isolation Forest, F1 = 0.842 on injected fault cycles

EOL threshold and split strategy (by battery, not by row) documented and defended.

**Stack:** Python · scikit-learn · scipy.io · matplotlib

---

## What's Coming

**Signal Processing Toolkit** — Clean, documented Python utilities for power and signal analysis: RMS, THD, wavelet decomposition, FFT, transient detection, frequency-domain anomaly scoring. Tools other engineers can actually use, not a demo.

**Fluid Flow Anomaly Detection** — Non-invasive flow monitoring from pipe acoustic/vibration signatures. Same principle as NILM applied to fluid systems: disaggregate flow events from a single sensor. Target datasets: open ultrasonic or differential pressure logs. Relevant to water utilities, industrial process monitoring.

**Edge ML for Embedded** — Embedded signal processing implementations targeting microcontrollers (STM32G4 series). Hardware-validated latency measurements, deterministic execution, no cloud dependency.

---

## Background

7+ years in electrical work — residential, industrial, telecom — across Serbia and Western Europe. Self-directed R&D in edge AI, power electronics control, and neuromorphic signal processing. Currently: power electronics engineer and R&D developer at BPM FiberNetworks.

The open portfolio is a direct extension of domain work, not a career pivot. The problems being solved here are problems from the field.

---

## Contact

**Email:** volmax.core@gmail.com  
**Location:** Novi Sad / Titel, Serbia  

Open to: energy ML roles · embedded systems engineering · technical collaborations · contract work in power quality and grid monitoring.
