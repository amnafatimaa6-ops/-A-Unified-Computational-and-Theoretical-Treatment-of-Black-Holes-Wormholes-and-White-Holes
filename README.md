# A-Unified-Computational-and-Theoretical-Treatment-of-Black-Holes-Wormholes-and-White-Holes

# 🌌 Singular Spacetimes
### A Computational Journey Through Black Holes, Wormholes, and the Edges of General Relativity

> *What does spacetime look like when it breaks?*

This repository is a growing collection of independent research notebooks exploring some of the strangest, most unresolved corners of theoretical and observational astrophysics — from the geometry of traversable wormholes to real LIGO gravitational-wave data, from Hawking radiation to the Black Hole Information Paradox.

Each project combines **General Relativity, numerical simulation, and real observational datasets** to ask a single question: *what would we actually see, measure, or compute if these exotic objects were real?*

---

## 🔭 What's Inside

### 🕳️ [Numerical Geodesics Around a Schwarzschild Black Hole](./geodesics)
How does curved spacetime bend the path of a falling particle? This notebook derives the geodesic equations from the Schwarzschild metric and numerically integrates them with a 4th-order Runge-Kutta solver — turning pure differential geometry into a visual orbit around an event horizon.

### 🌀 [Exotic Matter & Stability of a Traversable Wormhole](./wormhole-stability)
Using the Morris–Thorne metric, this project calculates exactly what kind of matter would have to exist to hold a wormhole throat open — and finds that it violates the Null Energy Condition. A perturbation analysis then probes whether such a wormhole, even in principle, could survive being touched.

### 👁️ [Wormhole vs. Black Hole: A Gravitational Lensing Showdown](./lensing-comparison)
If a wormhole were sitting where we think a black hole is, could we tell the difference? This project ray-traces photon paths around both objects and compares their shadows, photon rings, and brightness profiles — searching for an observational fingerprint that could distinguish one exotic object from another.

### 💥 [Hunting Primordial Black Holes in Fermi-LAT Gamma-Ray Data](./pbh-evaporation-search)
Could a primordial black hole be evaporating somewhere in the sky *right now*? This project takes Hawking's evaporation theory, calculates its predicted energy signature, and searches for it inside 231 real gamma-ray bursts from NASA's Fermi-LAT catalog — ranking candidate events with a custom-built consistency index.

### 📖 [The Black Hole Information Paradox & the Page Curve](./information-paradox)
Does information really vanish when a black hole evaporates — or does quantum mechanics demand it comes back out? This notebook builds a toy model comparing Hawking's information-loss entropy curve against the unitary Page Curve, then trains a machine learning classifier to tell the two competing pictures apart.

### 🌊 [GW150914: Reading the First Gravitational Wave Ever Detected](./gw150914-analysis)
The real LIGO strain data from the historic first gravitational-wave detection — cleaned, filtered, and analyzed by hand. This project extracts the chirp of two merging black holes directly from the noise and compares it against the waveform General Relativity predicts.

---

## 🧠 Why This Repository Exists

These are not textbook exercises — each notebook starts from a genuine open question in gravitational physics and tries to *compute* an answer, however partial. None of these results are claims of discovery. They are a computational exploration of ideas at the frontier of what we currently understand about spacetime, gravity, and quantum information.

## 🛠️ Tools & Stack
`Python` · `NumPy` / `SciPy` · `Astropy` / `Astroquery` · `GWpy` · `Matplotlib` · `Scikit-learn` · Google Colab

## 🚧 Status
Actively growing — this is phase one of a longer-term project connecting these notebooks into a single unified paper and public research portfolio.

---

*If a question here makes you curious, open the notebook. That's where the real work is.*
