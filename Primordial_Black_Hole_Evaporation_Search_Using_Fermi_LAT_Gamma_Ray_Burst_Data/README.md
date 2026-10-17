# Searching for Primordial Black Hole Evaporation Signatures in Fermi-LAT Gamma-Ray Burst Data
# Can a Tiny Black Hole Show Up in Fermi's Gamma-Ray Burst Data?

I used real NASA data to check whether any flashes of gamma rays in space could be a tiny black hole running out of life.

**I did not find a black hole.** This project is about asking the question properly and ranking the best "suspects", not proving anything.

---

## The idea (simple version)

- Stephen Hawking found that black holes slowly leak energy and shrink. This is called **Hawking radiation**.
- The smaller a black hole gets, the hotter it is and the faster it leaks, like an ice cube that melts faster as it gets smaller.
- Some tiny black holes (called **primordial black holes**) might have formed right after the Big Bang.
- One with a mass of about **5 × 10^11 kg** would be finishing its life about now, ending with a short flash of gamma rays.
- NASA's **Fermi telescope** has recorded hundreds of gamma-ray flashes (GRBs). So I asked: do any of them look like that final flash?

## The data

- **Where from:** NASA HEASARC, Fermi-LAT GRB catalog (`fermilgrb`), loaded with `astroquery`
- **Size:** 231 gamma-ray bursts and 111 columns
- **What I used:** how long the burst lasted (T90), how strongly it was detected (TS), the highest photon energy, the spectral index, fluence, flux and redshift
- **Missing data:** only 45 of 231 bursts have a redshift (a distance measure). Some photon energies were fake placeholder numbers (like -670), so I treated them as missing.

## What I did

1. Loaded the catalog and turned it into a pandas table.
2. Cleaned it and checked what was missing.
3. Calculated the temperature of a 5 × 10^11 kg black hole with Hawking's formula. The answer is about **21.15 MeV**.
4. Made plots of burst duration, photon energy and spectral index, plus a correlation heatmap.
5. Picked the **short bursts** (shorter than 2 seconds), because a black hole's final flash should be quick. That left **21 bursts**, about 9% of the sample.
6. Made a **PBH Consistency Index**, a score from 0 to 1 that shows how much a burst looks like what I expect from a dying black hole. It mixes four things:

| Thing | Weight | How it is scored in the code |
|---|---|---|
| How short the burst is (T90) | 40% | shorter = higher score |
| Highest photon energy | 30% | higher = higher score |
| How strongly it was detected (TS) | 20% | higher = higher score |
| Spectral index | 10% | the code uses the negative of the index (see the note below) |

7. Threw out any burst with a measured redshift. A burst that far away is far too distant for a black hole this small to be seen.

The score is a **ranking**. It is not a probability that a burst is a black hole.

## What I found

- A 5 × 10^11 kg black hole has a Hawking temperature of about **21.15 MeV**.
- Most bursts are long. The middle burst lasts about 31 seconds, and only 21 of 231 are under 2 seconds.
- Of the 21 short bursts, 19 had complete data and got a score.
- **GRB090510016** got the top score, but it has a redshift of 0.903, so it is billions of light-years away and I ruled it out.
- Among the rest, the top-ranked bursts were **GRB170127067** and **GRB200415367**, followed by GRB190606080 and GRB160702516.
- **None of them is proof of a primordial black hole.**

## Things you should know (honest notes)

- **21 MeV is the temperature right now.** A black hole gets hotter as it shrinks, so its final burst would have much higher energies. So seeing GeV photons does not rule black holes out.
- **Short does not mean black hole.** Two neutron stars crashing together, or a flare from a magnetar (a neutron star with a huge magnetic field), also make short bursts. These are far more common.
- **GRB200415367 looks like GRB 200415A**, which scientists think was a magnetar flare in the galaxy NGC 253. A flare like that releases around 10^44 to 10^46 erg, but a 5 × 10^11 kg black hole only holds about 4.5 × 10^35 erg in total. I matched the name by date and duration, so it is worth double-checking in the catalog.
- **No redshift is weak evidence.** Most short bursts have no redshift because they are faint, not because they are close.
- **Burst duration (T90) comes from Fermi's other instrument (GBM)**, not LAT.
- **Spectral index note:** the code uses `-like_best_grbindex`. Since the index is negative, this gives a *higher* score to *softer* spectra, which is the opposite of what I meant (harder spectra). It only has a 10% weight, but it can change the order a bit. Fixing it would be a good next step.

## Limitations

- I picked the weights myself. They are not fitted to data or to a real black-hole model.
- The sample is small (19 scored bursts), so the ranking can shuffle easily.
- One very bright burst can squash everyone else's scores because of min-max scaling.
- The catalog only has bursts that were already flagged as GRBs. A real black-hole flash might not be in it.
- I did not compare the real spectra or light curves to a full Hawking-radiation model.
- I did not check where in the sky each burst is (for example, whether it sits in a nearby galaxy).

## What I would do next

- Fix the spectral-index sign and re-run the ranking
- Try many different weights to see which bursts stay near the top
- Use a scaling method that is not thrown off by one extreme burst
- Check if each burst has enough energy to be a black hole at its distance
- Check burst positions against nearby galaxies
- Compare real spectra with a simulated Hawking-radiation spectrum
- Look at light curves (a dying black hole should get brighter and harder toward the end)
- Use a bigger catalog (the full Fermi-GBM burst list)
- Try machine learning to separate known mergers and magnetar flares from everything else

## Tools

Python, astroquery, astropy, pandas, numpy, matplotlib, seaborn, scikit-learn (Google Colab)

## How to run

1. Open the notebook in Google Colab.
2. Run the first cell to install the packages.
3. Run the rest of the cells in order. You need internet because the data downloads live from NASA.

## Author

Amna
