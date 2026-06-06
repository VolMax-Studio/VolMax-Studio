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

### [Power_Signal_Tools_Portfolio](https://github.com/VolMax-Studio/Power_Signal_Tools_Portfolio)
Domain-grounded, production-grade Python package for power and signal analysis. Features: windowed RMS, THD-F/THD-R (with Hann windowing and coherent gain correction), physical-scaled FFT, custom Mallat filterbank DWT (Haar & db4) for transient localization, rolling Z-score anomaly detection, and Hilbert amplitude envelope sag/swell analysis. Fully verified with 39 analytical unit tests.

**Stack:** Python · numpy · scipy · pandas · pytest

---

### [Fluid_Leakage_Detection_Portfolio](https://github.com/VolMax-Studio/Fluid_Leakage_Detection_Portfolio)
Transient leak detection and isolation pipeline on water distribution networks modeled after the BattLeDIM international benchmark. Integrates baseline pressure prediction (Random Forest), leak localization via hydraulic sensitivity matrices (mapping pressure drops to network nodes), and transient wave onset detection using Discrete Wavelet Transforms (DWT).

**Stack:** Python · scikit-learn · numpy · scipy · pandas · pytest

---

### [MCSA_Fault_Diagnostics_Portfolio](https://github.com/VolMax-Studio/MCSA_Fault_Diagnostics_Portfolio)
Motor Current Signature Analysis (MCSA) diagnostics for 3-phase induction motor faults:
- **Broken Rotor Bars (BRBs)** — detecting sidebands at $f_0 (1 \pm 2s)$ with measured -45.4 dBc (vs -45 dBc injected).
- **Bearing Faults** — modulating BPFO sidebands, measured at -50.0 dBc (vs -50 dBc injected).
- **Stator Short Circuits** — positive/negative sequence unbalance ratio ($I_2/I_1$) and 3rd/5th harmonics analysis (measured -29.6 dBc on 3rd harmonic).
Includes 50 Hz fundamental attenuation to prevent spectral leakage masking sidebands. Fully verified with 12 unit tests.

**Stack:** Python · numpy · scipy · scikit-learn · pytest

---

### [CWRU_Bearing_Diagnostics](https://github.com/VolMax-Studio/CWRU_Bearing_Diagnostics)
Fault diagnostics pipeline using the Case Western Reserve University (CWRU) bearing dataset. Implements Squared Envelope Spectrum (SES) analysis to isolate outer race, inner race, and ball defects under varying load levels (0HP–3HP).
- **Signal Processing**: bandpass filtering, Hilbert transform demodulation, and Welch PSD.
- **Robustness**: includes a physical CWRU-compatible simulator for offline/CI test suites (17/17 tests passing).
- **Diagnostics**: extracts defect characteristic frequencies (BPFO, BPFI, BSF, FTF) under load-modulated slip/RPM.

**Stack:** Python · numpy · scipy · matplotlib · pytest

---

### [Grid_Frequency_Analysis](https://github.com/VolMax-Studio/Grid_Frequency_Analysis)
Analysis of continental European (CE) synchronous area grid frequency dynamics. Implements a physics-based power system Swing Equation simulator and EN 50160 compliance evaluator.
- **Dynamics**: models system inertia $H$, governor response, load damping, and stochastic load variations.
- **Analysis**: computes Rate of Change of Frequency (ROCOF) using a sliding 0.2s window (IEC 60255-181) and tracks frequency nadir/settling values.
- **Robustness**: loads and parses real ENTSO-E historical measurements with synthetic fallback for offline CI runs. Fully verified with 14 unit tests.

**Stack:** Python · numpy · scipy · pandas · matplotlib · pytest

---

### [PV_Anomaly_Detection](https://github.com/VolMax-Studio/PV_Anomaly_Detection)
PV system performance monitoring and anomaly detection pipeline using NREL TMY3 data combined with a high-fidelity physical CEC module model.
- **Anomaly Detection**: identifies soiling, shading, degradation (PID), and inverter failures via Isolation Forests on temperature-corrected Performance Ratio (PR) indicators.
- **MPPT Transients**: simulates cloud shadow ramps (100–500 W/m²/s) and models a 10 Hz Perturb & Observe (P&O) MPPT tracker to calculate dynamic tracking efficiency.
- **Physics Engine**: models logarithmic $V_{mpp} \propto \ln(G/G_{stc})$ corrections to verify why slow cirrus cloud transitions cause larger cumulative energy losses than rapid cumulus edges. Fully verified with 26 unit tests.

**Stack:** Python · pvlib · scikit-learn · numpy · scipy · pandas · matplotlib · pytest

---

## What's Coming

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
