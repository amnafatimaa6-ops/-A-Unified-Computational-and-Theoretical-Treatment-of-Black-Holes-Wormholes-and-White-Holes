# Primordial Black Hole Evaporation Search Using Fermi-LAT Gamma-Ray Burst Data

## Research Overview

Can primordial black holes (PBHs) undergoing Hawking evaporation produce gamma-ray bursts detectable by the **Fermi Large Area Telescope (Fermi-LAT)**?

This project investigates that question by combining theoretical predictions of **Hawking radiation** with real observational data from the NASA Fermi-LAT Gamma-Ray Burst Catalog.

The objective is **not to claim the discovery of primordial black holes**, but to identify gamma-ray bursts whose observable properties are broadly compatible with the expected signatures of terminal PBH evaporation and rank them for potential follow-up investigation.

---

## Research Question

> **Could some short-duration gamma-ray bursts observed by Fermi-LAT be consistent with the observational signatures expected from primordial black holes evaporating in the present era?**

The analysis focuses on:

- Burst duration (`T90`)
- Maximum detected photon energy
- Photon spectral index
- LAT detection significance
- Gamma-ray flux and fluence
- Redshift availability

---

## Physical Motivation

According to Hawking's prediction, black holes emit thermal radiation and gradually lose mass.

For a non-rotating, uncharged black hole, the Hawking temperature is

\[
T_H =
\frac{\hbar c^3}
{8\pi G M k_B}.
\]

A primordial black hole with a mass of approximately

\[
M_{\rm PBH} \sim 5\times10^{11}\ {\rm kg}
\]

has an evaporation timescale comparable to the age of the Universe.

For this mass, the calculated Hawking temperature is approximately

\[
T_H \approx 21.15\ {\rm MeV}.
\]

This provides a theoretical energy scale for investigating high-energy emission associated with the final stages of PBH evaporation.

**Important:** 21.15 MeV is a characteristic thermal energy scale, not a prediction that every emitted photon will have exactly 21.15 MeV. Hawking radiation is a broad spectrum, and the final stages can involve secondary particle production.

---

# Dataset

The observational component uses the **Fermi-LAT Gamma-Ray Burst Catalog**, accessed through NASA's HEASARC archive using `astroquery`.

### Dataset summary

| Property | Value |
|---|---:|
| GRBs analysed | 231 |
| Catalogue features | 111 |
| GRBs with measured redshift | 45 |
| GRBs without redshift | 186 |
| GRBs with valid fluence | 219 |
| Short GRBs (`T90 < 2 s`) | 21 |

The catalogue was converted from an Astropy table into a Pandas DataFrame for data cleaning, statistical analysis, and visualization.

---

# Data Preparation

The original catalogue contains more than 100 observational parameters. A subset relevant to the PBH investigation was selected:

- `gbm_cat_t90` — burst duration
- `ext_emission_max_ene` — maximum detected photon energy
- `like_best_grbindex` — photon spectral index
- `like_lat_ts` — LAT detection Test Statistic
- `like_best_flux` — estimated gamma-ray flux
- `gbm_cat_fluence` — gamma-ray fluence
- `redshift` — cosmological redshift when available

### Preprocessing

The analysis included:

1. Removing unnecessary catalogue columns.
2. Inspecting missing values.
3. Handling missing fluence measurements.
4. Identifying bursts with measured redshift.
5. Treating non-positive photon-energy values as invalid.
6. Restricting the primary candidate analysis to short-duration bursts.

The catalogue contains substantial missingness in redshift:

\[
186/231 \approx 80.5\%
\]

while 45 GRBs have measured redshifts.

Because redshift requires successful follow-up observations, its absence is treated as **missing information rather than evidence of proximity**.

---

# Hawking Radiation Calculation

Using Astropy physical constants, the Hawking temperature was calculated for

\[
M_{\rm PBH}=5\times10^{11}\ {\rm kg}.
\]

The result was:

\[
\boxed{T_H \approx 21.15\ {\rm MeV}}
\]

This theoretical value establishes the characteristic energy scale used for comparison with the observed high-energy GRB population.

The calculation is implemented directly in the notebook using SI-consistent physical constants.

---

# Exploratory Data Analysis

Several statistical analyses were performed to characterise the Fermi-LAT GRB population.

## Burst Duration

The observed burst durations range from:

\[
0.128\ {\rm s}
\]

to

\[
478.03\ {\rm s}.
\]

The median duration is approximately:

\[
31.23\ {\rm s}.
\]

Using the conventional observational boundary

\[
T90 < 2\ {\rm s},
\]

21 bursts were classified as short-duration GRBs.

These events form the primary candidate sample because terminal PBH evaporation is expected to occur on very short timescales.

However, **short duration is not unique to PBHs**. Conventional compact-object merger events can also produce short GRBs.

---

## Maximum Photon Energy

The observed maximum photon energies extend from the MeV regime to several GeV and, for some events, tens of GeV.

The theoretical Hawking temperature of approximately 21.15 MeV lies near the lower end of the Fermi-LAT energy range.

This comparison must be interpreted carefully:

> The catalogue records the **maximum detected photon energy**, whereas Hawking radiation describes an underlying emission spectrum.

Therefore, maximum photon energy alone cannot determine whether a GRB originated from PBH evaporation.

---

## Spectral Index

The photon spectral index distribution is concentrated around approximately

\[
\Gamma \sim -2.
\]

This is broadly consistent with the power-law behaviour commonly observed in high-energy GRB emission.

Because spectral index alone does not provide a unique PBH signature, it is used as one component of the multi-parameter candidate analysis.

---

## Detection Significance

The LAT Test Statistic (TS) was used as a measure of detection significance.

Higher TS values correspond to stronger statistical evidence for the gamma-ray detection.

This parameter was incorporated into the candidate ranking to favour events with more statistically significant detections.

---

# Correlation Analysis

Pearson correlations were calculated between key observational parameters.

The strongest relationships identified in the sample were:

| Parameter pair | Pearson correlation |
|---|---:|
| LAT TS vs. Maximum Photon Energy | ~0.47 |
| LAT TS vs. Flux | ~0.33 |

Other parameter pairs showed relatively weak linear correlations.

This indicates that no individual observable provides a sufficient discriminator for identifying a PBH candidate.

A multi-parameter approach is therefore more appropriate.

---

# PBH Candidate Selection

The initial candidate population was defined as:

\[
T90 < 2\ {\rm s}.
\]

This produced **21 short-duration GRBs**.

Candidate properties were then evaluated using:

- Shorter burst duration
- Higher LAT detection significance
- Harder spectral index
- Valid high-energy photon measurement

---

# PBH Consistency Index

A heuristic **PBH Consistency Index (PCI)** was developed to rank short GRBs according to how closely their observed properties resemble the selected PBH-inspired criteria.

The four input observables were:

1. Burst duration
2. LAT detection significance
3. Maximum photon energy
4. Photon spectral index

Before calculating the index:

- Invalid photon energies were removed.
- Duration was transformed as \(1/T90\), so shorter bursts receive larger values.
- Spectral index was sign-inverted so harder spectra receive larger values.
- Features were normalized using Min-Max scaling.

The weighted index was defined as:

\[
PCI =
0.40D +
0.20S +
0.30E +
0.10\Gamma,
\]

where:

- \(D\) = normalized inverse duration
- \(S\) = normalized LAT detection significance
- \(E\) = normalized maximum photon energy
- \(\Gamma\) = normalized hardness score

The weights were chosen as a **heuristic physics-motivated ranking scheme**, rather than being derived from a calibrated probability model.

Therefore:

> **The PBH Consistency Index is a ranking statistic, not a probability of PBH origin.**

---

# Candidate Results

The highest numerical PCI score was obtained by:

### GRB090510016

However, this event has a measured redshift:

\[
z = 0.903,
\]

indicating a distant cosmological source. It is therefore not considered a strong PBH evaporation candidate within the framework of this study.

After accounting for known redshift information, several events remain particularly interesting for further investigation:

| Candidate | T90 (s) | LAT TS | Max Energy (MeV) | Spectral Index | Redshift |
|---|---:|---:|---:|---:|---|
| **GRB170127067** | 0.128 | 35.92 | 510 | -2.93 | — |
| **GRB200415367** | 0.144 | 30.58 | 1700 | -1.65 | — |
| **GRB190606080** | 0.224 | 9.41 | 1600 | -2.57 | — |
| **GRB160702516** | 0.200 | 19.26 | 4800 | -1.38 | — |

These events have combinations of short duration, significant LAT detections, energetic photons, and no measured redshift in the analysed catalogue.

**None of these properties establishes a PBH origin.**

---

# Key Findings

### 1. Hawking temperature

For

\[
M_{\rm PBH}=5\times10^{11}\ {\rm kg},
\]

the calculated Hawking temperature is:

\[
\boxed{21.15\ {\rm MeV}}.
\]

### 2. Short-duration population

21 of the 231 GRBs satisfy:

\[
T90 < 2\ {\rm s}.
\]

These represent approximately:

\[
9.1\%
\]

of the analysed sample.

### 3. High-energy emission

Observed GRBs frequently contain photons with energies substantially above 21 MeV, extending into the GeV range.

This does not by itself contradict Hawking evaporation because the theoretical prediction describes a broad emission spectrum rather than a single photon energy.

### 4. No unique PBH signature

Duration, photon energy, spectral index, detection significance, and redshift individually cannot distinguish PBH evaporation from conventional astrophysical GRBs.

### 5. Candidate events

Several short GRBs exhibit combinations of properties that make them worthy of additional investigation, particularly:

- **GRB170127067**
- **GRB200415367**
- **GRB190606080**
- **GRB160702516**

These should be considered **candidate events for further analysis, not PBH detections**.

---

# Scientific Limitations

This project is an exploratory candidate-search study rather than a detection analysis.

Important limitations include:

### 1. T90 is not a PBH evaporation timescale

The GBM \(T90\) statistic measures the interval containing approximately 90% of the detected burst counts. It is not equivalent to the theoretical lifetime of an evaporating PBH.

### 2. Redshift non-detection is not evidence of local origin

A missing redshift does not imply that a GRB is nearby. It simply means that a reliable redshift measurement was unavailable.

### 3. Maximum photon energy is detector- and sample-dependent

The maximum detected photon energy depends on photon statistics, detector sensitivity, exposure, and the underlying spectrum.

### 4. The PBH Consistency Index is heuristic

The weighting scheme is not statistically calibrated and should not be interpreted as a Bayesian probability or detection significance.

### 5. Conventional astrophysical explanations remain viable

Short-duration GRBs can originate from established astrophysical processes, particularly compact-object mergers and other energetic transient phenomena.

### 6. A full PBH search requires a physical spectral model

A stronger analysis would compare the observed photon spectra and temporal behaviour against detailed PBH evaporation models rather than relying primarily on catalogue-level summary statistics.

---

# Future Work

Several extensions could substantially strengthen the investigation:

- Fit detailed Hawking radiation spectra to individual candidate events.
- Model the expected PBH photon spectrum including secondary particle production.
- Perform unbinned likelihood analysis of Fermi-LAT photon events.
- Examine individual photon arrival times and temporal clustering.
- Analyse GRB localisation and Galactic/extragalactic spatial distributions.
- Incorporate Fermi-GBM data alongside LAT observations.
- Compare candidates against known short-GRB populations.
- Include detector selection effects and sensitivity biases.
- Construct a statistically calibrated likelihood or Bayesian model.
- Perform population-level searches rather than selecting candidates using a fixed threshold.
- Investigate archival events independently of their existing GRB classification.
- Compare candidate events with theoretical PBH evaporation rates and expected local event densities.

---

# Technologies Used

- **Python**
- **Astropy**
- **Astroquery**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**
- **NASA HEASARC**
- **Fermi-LAT Gamma-Ray Burst Catalog**

---
