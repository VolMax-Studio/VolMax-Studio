# VolMax Studio Lab

**Power electronics engineer + energy ML.**

Domain-grounded open tools for grid monitoring, load disaggregation, battery diagnostics, motor fault detection, and embedded signal processing. The edge: real electrical domain knowledge combined with the ability to code — a combination that's rare enough to matter.

---

## Active Portfolio

### [PowerQuality_Classifier_Portfolio](https://github.com/VolMax-Studio/PowerQuality_Classifier_Portfolio)
17-class power quality disturbance classifier on IEEE-1159 parametric data. Random Forest + spectral feature engineering. Honest results: ~78% accuracy with full confusion matrix and Streamlit dashboard.

**Stack:** Python · scikit-learn · Streamlit

---

### [NILM_Disaggregation_Portfolio](https://github.com/VolMax-Studio/NILM_Disaggregation_Portfolio)
Energy disaggregation on real REDD data (Kolter & Johnson 2011) — House 3, ~3 days of smart meter measurements. Random Forest with physics-informed features for load separation from aggregate mains.

**Stack:** Python · scikit-learn · pandas

---

### [Battery_Health_Portfolio](https://github.com/VolMax-Studio/Battery_Health_Portfolio)
Three-task diagnostics on real NASA PCoE Li-ion data (B0005–B0018): SoH regression (R²=0.943, cross-battery), RUL prediction (RMSE=5.7 cycles), thermal anomaly detection (F1=0.842).

**Stack:** Python · scikit-learn · scipy.io

---

### [power_signal_tools](https://github.com/VolMax-Studio/power_signal_tools)
Importable Python library: windowed RMS, THD-F/R via FFT, DWT transient detection, Hilbert envelope for sag/swell, rolling z-score. 39/39 analytically verified tests.

**Stack:** Python · NumPy · SciPy · PyWavelets

---

### [Fluid_Leakage_Detection_Portfolio](https://github.com/VolMax-Studio/Fluid_Leakage_Detection_Portfolio)
Non-intrusive leak detection in water distribution networks — same NILM principle applied to hydraulic systems. DWT burst detection + RF baseline residual alarm + sensitivity matrix localization.

**Stack:** Python · scikit-learn · SciPy

---

### [MCSA_Fault_Diagnostics_Portfolio](https://github.com/VolMax-Studio/MCSA_Fault_Diagnostics_Portfolio)
Motor Current Signature Analysis: broken rotor bar, bearing outer-race, stator inter-turn short circuit — all from stator current alone. Welch PSD with Kaiser window, Fortescue sequence analysis. 12/12 tests.

**Stack:** Python · NumPy · SciPy

---

### [CWRU_Bearing_Diagnostics](https://github.com/VolMax-Studio/CWRU_Bearing_Diagnostics)
Envelope analysis on real CWRU lab bearing data (SKF 6205-2RS, NASA-collected). Hilbert envelope → Squared Envelope Spectrum → fault frequency detection (BPFO, BPFI, BSF, FTF). 17/17 tests. Real data fallback to CWRU-compatible synthetic.

**Stack:** Python · SciPy · NumPy

---

### [Grid_Frequency_Analysis](https://github.com/VolMax-Studio/Grid_Frequency_Analysis)
Continental European grid frequency dynamics: swing equation model (H=6s, IEC parameters), ROCOF calculation, EN 50160 compliance checking, disturbance event detection. 14/14 tests. Accepts real ENTSO-E CSV data.

**Stack:** Python · SciPy · NumPy

---

### [PV_Anomaly_Detection](https://github.com/VolMax-Studio/PV_Anomaly_Detection)
PV system anomaly detection on real NREL TMY3 meteorological data + real CEC module parameters (Canadian Solar CS5P-250M). Isolation Forest detection: Precision 0.985, Recall 0.565. Includes P&O MPPT cloud transient simulation at 10 Hz.

**Stack:** Python · pvlib · scikit-learn · NumPy

---

### [Transformer_Health_Portfolio](https://github.com/VolMax-Studio/Transformer_Health_Portfolio)
Transformer health assessment: IEC 60076-7 thermal model (top-oil + hot-spot), Arrhenius insulation aging, IEC 60599 DGA interpretation with Duval triangle + Rogers ratios. 40 MVA ONAN substation transformer. 27/27 tests.

**Stack:** Python · SciPy · NumPy

---

## Background

20+ years in electrical work — residential, industrial, telecom — across Serbia and Western Europe. Self-directed R&D in edge AI, power electronics control, and embedded signal processing. Company: VolMax Studio Lab d.o.o., Titel, Serbia.

The open portfolio is a direct extension of field work. The problems being solved here are problems encountered in real electrical infrastructure.

---

## Contact

**Email:** volmax.core@gmail.com  
**Location:** Novi Sad / Titel, Serbia  
**Website:** volmax-studio.rs

Open to: energy ML roles · embedded systems engineering · technical collaborations · contract work in power quality and grid monitoring.

