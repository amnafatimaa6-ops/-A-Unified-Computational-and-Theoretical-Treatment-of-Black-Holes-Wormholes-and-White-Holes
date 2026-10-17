# Searching for Primordial Black Hole Evaporation Signatures in Fermi-LAT Gamma-Ray Burst Data

A Python data-analysis project that asks a simple question: **could any gamma-ray bursts seen by NASA's Fermi telescope look like a tiny black hole finishing its life?**

The goal is **not** to prove that primordial black holes (PBHs) exist. It is to rank real bursts by how closely they resemble the theoretical prediction, and to be clear about what that does and does not mean.

---

## The idea in simple words

- Stephen Hawking showed that black holes slowly leak energy (Hawking radiation) and shrink.
- The smaller a black hole gets, the hotter it is and the faster it leaks.
- A primordial black hole of about **5 × 10^11 kg** would be reaching the end of its life around the present age of the Universe, ending with a short burst of gamma rays.
- Fermi-LAT has detected hundreds of gamma-ray bursts (GRBs). This project checks which ones look most like that prediction.

## Data

- **Source:** NASA HEASARC, Fermi-LAT GRB catalog (table `fermilgrb`), loaded with `astroquery`
- **Size:** 231 GRBs, 111 columns
- **Columns used:** burst duration (`gbm_cat_t90`, from Fermi-GBM), fluence, flux, photon spectral index (`like_best_grbindex`), LAT detection test statistic (`like_lat_ts`), maximum photon energy (`ext_emission_max_ene`), redshift
- **Missing data:** only 45 of 231 bursts have a measured redshift; some maximum-energy values are placeholders (such as -670) and were treated as missing

## Method

1. Load the catalog with `astroquery` and convert it to a pandas DataFrame.
2. Clean the data (drop unneeded columns, handle missing values and placeholder values).
3. Calculate the Hawking temperature of a 5 × 10^11 kg black hole:
   `T = ħc³ / (8πGMk_B)`, which gives about **21.15 MeV**.
4. Explore the full sample with histograms (duration, photon energy, spectral index) and a correlation heatmap.
5. Select **short GRBs** (T90 < 2 s): **21 bursts** (about 9% of the sample).
6. Build a **PBH Consistency Index** from four min-max scaled features:

| Feature | Weight | Direction |
|---|---|---|
| Burst duration (T90) | 0.40 | shorter scores higher |
| Maximum photon energy | 0.30 | higher scores higher |
| LAT detection strength (TS) | 0.20 | higher scores higher |
| Photon spectral index | 0.10 | harder (less negative) scores higher |

7. Remove bursts with a measured redshift (a cosmological distance rules out a PBH) and compare the remaining candidates.

The index is a **ranking**, not a probability.

## Key results

- Hawking temperature of a 5 × 10^11 kg PBH: **about 21.15 MeV**
- Most bursts are long: median T90 is about 31 s; only 21 of 231 are shorter than 2 s
- 19 of the 21 short bursts have complete data and were scored (two have placeholder photon energies)
- GRB090510016 scores highest but has a redshift of z = 0.903, so it is excluded
- A few short bursts without redshift score well, but the ranking changes when weights or the spectral-index direction change, so it is **not stable**
- **No burst gives conclusive evidence for primordial black hole evaporation**

## Important notes and caveats

- **21 MeV is the temperature today.** A shrinking black hole gets hotter, so its final burst would reach much higher energies. Seeing GeV photons does not rule PBHs out.
- **Short does not mean PBH.** Neutron-star mergers and magnetar giant flares also produce short bursts and are far more common.
- **GRB200415367 appears to match GRB 200415A**, which published studies interpret as a magnetar giant flare in the galaxy NGC 253 (about 3.5 Mpc away). Such a flare releases around 10^44 to 10^46 erg, while a 5 × 10^11 kg black hole holds only about 4.5 × 10^35 erg in total. (Name match is by date and duration; confirm in the catalog.)
- **Missing redshift is weak evidence.** Most short GRBs lack a redshift because they are faint, not because they are nearby.
- T90 comes from Fermi-GBM, not LAT.

## Limitations

- The weights are chosen by hand, not fitted to data or a physical model
- Small sample (21 short bursts, 19 scored); the top of the ranking reshuffles easily
- Min-max scaling is sensitive to outliers (one very bright burst compresses all other scores)
- The catalog only contains bursts already flagged as GRBs, so a real PBH burst may be missing
- No comparison with a full Hawking-radiation spectrum or the bursts' light curves
- Sky positions and host galaxies were not checked

## Future work

- Test ranking stability with many random weight choices
- Use rank-based or log scaling instead of min-max scaling
- Add an energy and distance check: a PBH burst can only be detected from within roughly tens to a couple of hundred parsecs
- Check sky positions against nearby galaxies to flag magnetar giant flares
- Compare measured spectra with a simulated Hawking-radiation spectrum
- Analyse light curves (a PBH burst should brighten and harden toward the end)
- Extend to the full Fermi-GBM catalog and compare with published PBH limits
- Train a classifier on known mergers and magnetar flares and study what is left over

## Tools

Python, `astroquery`, `astropy`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` (Google Colab)

## How to run

1. Open the notebook in Google Colab (or Jupyter).
2. Run the first cell to install `astroquery`, `astropy` and `pandas`.
3. Run all cells in order. The catalog is downloaded live from HEASARC, so an internet connection is needed.

## Author

Amna
