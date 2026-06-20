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
Predictability-horizon study on real NASA PCoE Li-ion cells (B0005/06/18; B0007 censored and excluded — never reaches EOL). Three measured findings, none assumed: a single cell hides its own end-of-life (B0005 mispredicted +157 cycles from a 50-cycle window), the textbook leading indicator Rct does not lead (late-life MAE 0.333→0.332 Ah — no gain), and the population reveals what the cell hides (cross-cell leave-one-out ~10–16 cycle EOL error). Predictability is population-level, not individual. DOI 10.5281/zenodo.20752869.

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
Incipient bearing-fault diagnostics on real Case Western Reserve University (CWRU) data (SKF 6205-2RS, 12 kHz drive-end, 0 HP, 0.007″ EDM faults). Bandpass-filtered Hilbert envelope → Squared Envelope Spectrum. On real measurements every fault frequency localizes within ~2% of theory (BPFO 108.0 vs 107.4 Hz, BPFI 162.0 vs 162.2 Hz, BSF 72.0 vs 70.6 Hz). The detection difficulty lives in time-domain impulsiveness: filtered kurtosis falls from outer-race 4.75 (sharp stationary defect) through inner-race 2.63 (load-zone modulated) to ball 0.0 (non-impulsive — the impulse train is smeared by rolling-element slip), quantifying why rolling-element faults are the hard case for envelope methods. Healthy baseline shows no fault peak (kurtosis −1.05). 17/17 tests.

**Stack:** Python · SciPy · NumPy

---

### [Grid_Frequency_Analysis](https://github.com/VolMax-Studio/Grid_Frequency_Analysis)
Continental European grid frequency dynamics: swing equation model (H=6s, IEC parameters), ROCOF calculation, EN 50160 compliance checking, disturbance event detection. 14/14 tests. Accepts real ENTSO-E CSV data.

**Stack:** Python · SciPy · NumPy

---

### [PV_Anomaly_Detection](https://github.com/VolMax-Studio/PV_Anomaly_Detection)
Controlled anomaly-detection benchmark on real NREL TMY3 meteorological data (ASOS 723170, Greensboro NC — 8760h measured) and real CEC module parameters (Canadian Solar CS5P-250M), modelled via pvlib single-diode physics (de Soto 2006). Synthetic faults (soiling, shading, PID, inverter) are injected as ground-truth; Isolation Forest scores Precision 0.985 / Recall 0.565 against the injected labels — a low-false-alarm, conservative-recall regime: reliable on clear anomalies, misses subtler ones. 26 passing tests.

**Stack:** Python · pvlib · scikit-learn

---

### [Transformer_Health_Portfolio](https://github.com/VolMax-Studio/Transformer_Health_Portfolio)
Transformer health assessment: IEC 60076-7 thermal model (top-oil + hot-spot), Arrhenius insulation aging, IEC 60599 DGA interpretation with Duval triangle + Rogers ratios. 40 MVA ONAN substation transformer. 27/27 tests.

**Stack:** Python · SciPy · NumPy

---

### [VPP_Frequency_Regulation](https://github.com/VolMax-Studio/VPP_Frequency_Regulation)
Virtual Power Plant (VPP) active frequency regulation simulation on a regional grid: FCR (Primary) and aFRR (Secondary AGC) control loops, battery storage (BESS), solar PV clipping, and flexible loads dispatch. Closed-loop swing equation dynamics. 21/21 tests.

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

