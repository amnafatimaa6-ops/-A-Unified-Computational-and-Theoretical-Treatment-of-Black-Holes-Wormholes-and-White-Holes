# GW150914: Gravitational-Wave Data Analysis with Python

## Overview

This project explores gravitational-wave data from GW150914, a binary black-hole merger observed by the LIGO detectors on 14 September 2015.

Using Python in a Jupyter Notebook, I analyse publicly available data from the Hanford (H1) and Livingston (L1) detectors. The notebook includes signal visualisation, bandpass filtering, strain measurements, exploratory frequency analysis, and a comparison between the observed signal and a theoretically generated waveform.

The goal is to explore how computational methods can help investigate real gravitational-wave observations.

## Objectives

- Retrieve and examine gravitational-wave data from both LIGO detectors.
- Visualise the signals and inspect the interval surrounding the merger.
- Apply a bandpass filter to examine a selected frequency range.
- Calculate the maximum absolute filtered strain within the selected interval.
- Explore the signal envelope using the Hilbert transform.
- Estimate frequency behaviour using detected peak spacing.
- Generate a theoretical binary-black-hole waveform and compare its shape with the observed signal.

## Methodology

### 1. Data Retrieval

The notebook uses GWpy to retrieve publicly available LIGO data for H1 and L1 over a 32-second interval surrounding GW150914.

The data are sampled at 4096 Hz, giving a sampling interval of approximately 0.000244 seconds and 131,072 samples per detector over the selected interval.

### 2. Signal Processing

The detector time series are visualised, and a bandpass filter from 30 to 400 Hz is applied to focus on the selected frequency range.

The notebook then examines an approximately 0.4-second interval around the merger to investigate the signal's behaviour over a shorter timescale.

### 3. Strain Analysis

The notebook calculates the maximum absolute filtered-strain value within the selected interval.

The reported values are approximately:

- **Hanford (H1):** \(2.480 \times 10^{-21}\)
- **Livingston (L1):** \(2.243 \times 10^{-21}\)

These values describe the processed time series within the chosen interval. They are not presented as official peak-strain measurements or as a direct measure of the detectors' relative sensitivity.

### 4. Signal Envelope and Frequency Exploration

The Hilbert transform is used to examine the signal's amplitude envelope. Detected peaks are also used to explore frequency behaviour through their spacing.

These calculations provide an exploratory view of the signal rather than a precision measurement of its instantaneous frequency.

### 5. Theoretical Waveform Generation

The notebook uses PyCBC to generate an `IMRPhenomD` binary-black-hole waveform with component masses of 36 and 29 solar masses and a lower frequency cutoff of 20 Hz.

The generated waveform is normalised and peak-aligned for visual comparison with the observed signal.

The masses are specified model inputs; the notebook does not estimate them from the detector data. The comparison is qualitative and does not constitute a formal statistical fit or an independent test of general relativity.

The notebook also includes a \(t^{1.5}\) curve constructed from selected frequency values. This is an illustrative mathematical curve rather than a theoretical prediction from general relativity.

## Results

The notebook demonstrates an exploratory workflow for investigating real gravitational-wave observations.

The analysis produces visualisations of the two detector time series, filtered signals, a short merger interval, strain measurements, a signal envelope, a peak-based frequency estimate, and a generated theoretical waveform for visual comparison.

Together, these steps demonstrate how scientific Python libraries can be used to retrieve, process, visualise, and explore gravitational-wave data.

The results are exploratory and do not represent a new detection, a formal waveform fit, or an independent confirmation of general relativity.

## Limitations

- **Noise and filtering:** Bandpass filtering restricts the analysed frequency range but does not remove all detector noise. Filtering can also introduce edge effects.
- **Frequency estimation:** Peak-based estimates can be affected by noise, peak detection, and the spacing of the selected peaks.
- **Qualitative waveform comparison:** Normalising and peak-aligning the waveforms supports visual comparison but does not preserve all original amplitude and timing information. No formal statistical fit is performed.
- **Specified model parameters:** The component masses are inputs to the theoretical waveform rather than estimates obtained from the observed data.
- **Illustrative curve:** The \(t^{1.5}\) curve is a mathematical illustration and should not be interpreted as a general-relativity prediction.
- **Detector differences:** The H1 and L1 measurements can differ because of detector orientation, response, calibration, and noise.
- **Scope of analysis:** The notebook investigates an already identified gravitational-wave event. It does not independently establish the event's astrophysical significance or perform a complete source-parameter estimation.

## Future Work

Possible extensions of this project include:

1. **Time-frequency analysis:** Investigate the signal's evolving frequency using time-frequency visualisations and more robust phase-based methods.
2. **Noise investigation:** Examine raw and filtered data, assess filtering effects, and test the sensitivity of the results to different filter settings.
3. **Improved waveform comparison:** Explore more systematic alignment methods, detector-response modelling, and quantitative goodness-of-fit measures.
4. **Parameter estimation:** Study established gravitational-wave inference techniques to investigate how source properties can be estimated from detector observations.
5. **Detector comparison:** Examine the consistency of the two detector signals while accounting for their different responses and noise characteristics.
6. **Reproducibility:** Document software versions, analysis settings, and selected time intervals to make the workflow easier to reproduce.

These are proposed extensions and are not claimed as completed features of the current notebook.

## Technologies Used

- Python
- Jupyter Notebook
- GWpy
- NumPy
- SciPy
- Matplotlib
- PyCBC
- Publicly available LIGO data

## References

1. Abbott et al. (2016). *Observation of Gravitational Waves from a Binary Black Hole Merger*. Physical Review Letters. https://doi.org/10.1103/PhysRevLett.116.061102
2. Gravitational Wave Open Science Center (GWOSC): https://gwosc.org/
3. GWpy documentation: https://gwpy.github.io/docs/
4. PyCBC waveform documentation: https://pycbc.org/pycbc/latest/html/waveform.html

## Author

Amna Fatima

*An exploratory computational physics project investigating gravitational-wave observations through scientific programming, signal processing, and waveform visualisation.*
