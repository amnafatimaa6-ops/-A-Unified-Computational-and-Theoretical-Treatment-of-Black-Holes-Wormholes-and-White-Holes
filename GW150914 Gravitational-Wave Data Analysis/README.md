# GW150914 Gravitational-Wave Data Analysis

## Overview

This notebook analyses the historic gravitational-wave event **GW150914**, detected by the Laser Interferometer Gravitational-Wave Observatory (LIGO) on 14 September 2015.

The goal is to work with real gravitational-wave observational data and investigate whether the measured signal exhibits the characteristic behaviour predicted by General Relativity for a **binary black hole merger**.

The analysis uses data from both LIGO detectors:

* **H1 — Hanford Observatory**
* **L1 — Livingston Observatory**

The notebook combines observational data analysis, signal processing, numerical methods, and theoretical waveform modelling to connect real gravitational-wave measurements with General Relativity.

---

## Scientific Questions

This notebook investigates several questions:

1. What does the raw GW150914 detector data look like?
2. How can detector noise be reduced to reveal the astrophysical signal?
3. Can the characteristic gravitational-wave chirp be extracted from the data?
4. How does the observed frequency evolve near merger?
5. Does the observed waveform show the expected inspiral--merger--ringdown structure?
6. How closely does the observed signal resemble a theoretical General Relativity waveform?

---

## Dataset

The gravitational-wave strain data are obtained from the **Gravitational Wave Open Science Center (GWOSC)** using the `GWpy` library.

A 32-second segment surrounding GW150914 is analysed from both detectors.

### Dataset Characteristics

| Property             |                     Value |
| -------------------- | ------------------------: |
| Detectors            |                 H1 and L1 |
| Duration             |                32 seconds |
| Sampling rate        |                   4096 Hz |
| Samples per detector |                   131,072 |
| Quantity measured    | Gravitational-wave strain |
| Strain units         |             Dimensionless |
| Event                |                  GW150914 |
| Detection date       |         14 September 2015 |

The strain is defined as

$$
h=\frac{\Delta L}{L}
$$

where $L$ is the detector arm length and $\Delta L$ is the extremely small change produced by the passing gravitational wave.

---

## Analysis Pipeline

The notebook follows a complete observational-to-theoretical workflow:

```text
GWOSC
  ↓
Download LIGO strain data
  ↓
Inspect H1 and L1 datasets
  ↓
Visualise raw strain
  ↓
Band-pass filtering
  ↓
Select merger time window
  ↓
Extract GW150914 chirp
  ↓
Measure peak strain
  ↓
Estimate frequency evolution
  ↓
Analyse signal envelope
  ↓
Generate theoretical waveform
  ↓
Compare observation with General Relativity
```
