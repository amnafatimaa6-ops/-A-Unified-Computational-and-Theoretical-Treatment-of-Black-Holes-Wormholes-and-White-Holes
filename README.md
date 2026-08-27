# 🌌 **Singular Spacetimes**

### *A Computational Journey Through Black Holes, Wormholes, and the Edges of General Relativity*

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:050014,50:16003B,100:3B1B78&height=220&section=header&text=SINGULAR%20SPACETIMES&fontSize=42&fontColor=FFFFFF&animation=fadeIn&fontAlignY=38&desc=Black%20Holes%20%E2%80%A2%20Wormholes%20%E2%80%A2%20White%20Holes&descAlignY=58&descSize=18" width="100%"/>
</p>

<p align="center">
  <em>“What does spacetime look like when it breaks?”</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/General%20Relativity-6C3BFF?style=for-the-badge&logoColor=white"/>
  <img src="https://img.shields.io/badge/Computational%20Astrophysics-24104F?style=for-the-badge&logoColor=white"/>
  <img src="https://img.shields.io/badge/Black%20Holes-090014?style=for-the-badge&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-0B3D91?style=for-the-badge&logo=python&logoColor=white"/>
</p>

---

## 🌌 **About the Project**

**Singular Spacetimes** is a growing computational research portfolio exploring some of the strangest and most unresolved problems in theoretical and observational astrophysics.

From the geometry of traversable wormholes to real **LIGO gravitational-wave data**, from **Hawking radiation** to the **Black Hole Information Paradox**, each project combines:

> **General Relativity + Numerical Methods + Computational Physics + Observational Data**

The central question connecting the repository is simple:

### *What would we actually see, measure, or compute if these exotic objects were real?*

---

# 🛰️ **What's Inside**

## 🕳️ Numerical Geodesics Around a Schwarzschild Black Hole

**[→ Explore the project](./geodesics)**

How does curved spacetime bend the path of a falling particle?

This notebook derives the geodesic equations from the **Schwarzschild metric** and numerically integrates them using a **4th-order Runge–Kutta solver**.

The result is a computational journey from differential geometry to numerical orbital dynamics around an event horizon.

**Core concepts**

`Schwarzschild Metric` · `Geodesics` · `Differential Equations` · `RK4` · `Numerical Relativity`

---

## 🌀 Exotic Matter & Stability of a Traversable Wormhole

**[→ Explore the project](./wormhole-stability)**

Using the **Morris–Thorne metric**, this project investigates the matter required to maintain a traversable wormhole throat.

The calculations reveal violation of the **Null Energy Condition**, while a perturbation analysis explores whether such a geometry could remain dynamically stable.

**Core concepts**

`Morris–Thorne Metric` · `Exotic Matter` · `Energy Conditions` · `Perturbation Theory` · `Stability`

---

## 👁️ Wormhole vs. Black Hole — A Gravitational Lensing Showdown

**[→ Explore the project](./lensing-comparison)**

If a wormhole occupied the region where we expect a black hole, could observations distinguish the two?

This project ray-traces photon trajectories around both geometries and compares their:

* Shadow structure
* Photon rings
* Central brightness
* Lensing signatures
* Observable differences

The goal is to search for computationally identifiable fingerprints that could distinguish exotic spacetime geometries.

**Core concepts**

`Ray Tracing` · `Gravitational Lensing` · `Photon Orbits` · `Black Holes` · `Wormholes`

---

## 💥 Hunting Primordial Black Holes in Fermi-LAT Gamma-Ray Data

**[→ Explore the project](./pbh-evaporation-search)**

Could a primordial black hole be evaporating somewhere in the Universe *right now*?

This project connects **Hawking evaporation theory** with real gamma-ray observations from the **NASA Fermi-LAT catalogue**.

The analysis calculates the expected energetic signature of primordial black-hole evaporation and searches through **231 real gamma-ray bursts**, ranking potential candidates using a custom consistency index.

**Core concepts**

`Hawking Radiation` · `Primordial Black Holes` · `Gamma Rays` · `Fermi-LAT` · `Astroquery` · `Statistical Analysis`

---

## 📖 The Black Hole Information Paradox & the Page Curve

**[→ Explore the project](./information-paradox)**

Does information disappear when a black hole evaporates — or does quantum mechanics require it to remain recoverable?

This notebook constructs a toy computational model comparing:

**Hawking Information-Loss Curve**

vs.

**Unitary Page Curve**

A machine-learning classifier is then used to distinguish the two competing entropy behaviours.

**Core concepts**

`Black Hole Information Paradox` · `Page Curve` · `Entropy` · `Quantum Information` · `Machine Learning`

---

## 🌊 GW150914 — Reading the First Gravitational Wave Detection

**[→ Explore the project](./gw150914-analysis)**

Real gravitational-wave data from **GW150914**, the historic first direct detection of gravitational waves.

The project processes detector strain data, applies filtering techniques, extracts the characteristic **chirp**, and compares the observed signal with the waveform expected from General Relativity.

**Core concepts**

`LIGO` · `GW150914` · `Gravitational Waves` · `GWpy` · `Signal Processing` · `General Relativity`

---

# 🔭 **The Computational Pipeline**

```text
                    🌌 SINGULAR SPACETIMES
                            │
          ┌─────────────────┴─────────────────┐
          │                                   │
     THEORETICAL PHYSICS               OBSERVATIONAL DATA
          │                                   │
   ┌──────┼──────┐                    ┌───────┼────────┐
   │      │      │                    │       │        │
  GR   Metrics  QM                  LIGO   Fermi-LAT  Catalogues
   │      │      │                    │       │        │
   └──────┼──────┘                    └───────┼────────┘
          │                                   │
          └──────────────┬────────────────────┘
                         ↓
                 COMPUTATIONAL MODELS
                         ↓
              NUMERICAL SIMULATIONS
                         ↓
                  DATA ANALYSIS
                         ↓
               PHYSICAL INTERPRETATION
```

---

# 🧠 **Why This Repository Exists**

These are not intended to be simple textbook exercises.

Each notebook begins with a genuine question from gravitational physics and attempts to investigate it computationally.

The projects sit at the intersection of:

**Theoretical Physics**

**Computational Astrophysics**

**Numerical Methods**

**Machine Learning**

**Observational Astronomy**

None of the projects claim a discovery.

Instead, they represent computational explorations of ideas at the frontier of our understanding of **gravity, spacetime, black holes, and quantum information**.

---

# 🛠️ **Technology Stack**

<p align="center">

<img src="https://img.shields.io/badge/Python-0B3D91?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/NumPy-4B2E83?style=for-the-badge&logo=numpy&logoColor=white"/>
<img src="https://img.shields.io/badge/SciPy-5C3AAE?style=for-the-badge&logo=scipy&logoColor=white"/>
<img src="https://img.shields.io/badge/Astropy-2B1B5A?style=for-the-badge&logoColor=white"/>
<img src="https://img.shields.io/badge/Astroquery-170B3B?style=for-the-badge&logoColor=white"/>

<br>

<img src="https://img.shields.io/badge/GWpy-351A63?style=for-the-badge&logoColor=white"/>
<img src="https://img.shields.io/badge/Scikit--learn-45278A?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
<img src="https://img.shields.io/badge/Matplotlib-24104F?style=for-the-badge&logoColor=white"/>
<img src="https://img.shields.io/badge/Google%20Colab-3B1B78?style=for-the-badge&logo=googlecolab&logoColor=white"/>

</p>

---

# 🌑 **Research Philosophy**

> **Theory tells us what might exist.**
>
> **Computation tells us what it would look like.**
>
> **Observation tells us whether nature agrees.**

This repository lives somewhere between all three.

---

# 🚧 **Project Status**

**Phase I — Active Development**

The current projects form the first layer of a larger computational programme.

Future work aims to connect these individual investigations into a unified research framework combining:

* General Relativity
* Numerical Relativity
* Computational astrophysics
* Gravitational-wave astronomy
* High-energy astrophysics
* Machine learning
* Quantum information

---

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:3B1B78,50:16003B,100:050014&height=120&section=footer"/>
</p>

<p align="center">
  <strong>🌌 Explore the notebooks. Follow the equations. Question the singularity.</strong>
</p>

<p align="center">
  <em>If a question here makes you curious, open the notebook.<br>
  That's where the real work is.</em>
</p>
