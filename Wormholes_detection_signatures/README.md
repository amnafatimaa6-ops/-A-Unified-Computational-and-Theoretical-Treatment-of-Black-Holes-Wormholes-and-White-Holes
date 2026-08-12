# Wormhole vs Black Hole Gravitational Lensing

## 🔭 Project Overview

This project investigates a fundamental question in theoretical astrophysics:

**Can gravitational lensing help distinguish a traversable wormhole from a black hole?**

I developed computational simulations of a **Schwarzschild black hole** and a **Morris–Thorne traversable wormhole** to study how their predicted gravitational lensing signatures may differ.

The project combines analytical calculations, numerical photon trajectories, image simulations, and quantitative comparisons to explore possible observational signatures of exotic compact objects.

## 🔬 What I Explored

The project includes:

* Schwarzschild black hole gravitational lensing
* Morris–Thorne wormhole lensing
* Photon deflection calculations
* Numerical integration of Schwarzschild photon geodesics
* Simplified ray-tracing simulations
* Black hole shadow and photon-ring modelling
* Wormhole throat and multiple-ring modelling
* Radial brightness profiles
* Central and ring brightness measurements
* Black hole vs wormhole comparison tables
* A preliminary wormhole-signature scoring framework

## 🧠 What I Found

The simulations showed several qualitative differences between the two models.

### Black Hole

The simulated Schwarzschild black hole produced:

* A dark central region representing the shadow
* A strong photon-ring feature
* Increasing gravitational deflection for smaller impact parameters
* A strong central brightness minimum

### Traversable Wormhole

The simplified wormhole model produced:

* A brighter central region
* A visible throat instead of a completely dark centre
* Additional concentric lensing structures
* A different radial brightness distribution

The simulations therefore suggest that **central brightness, ring structure, and radial intensity profiles** could be useful theoretical discriminants between certain wormhole models and black holes.

These results are **not evidence that wormholes exist**. They are computational predictions that could be tested against more realistic models and future observations.

## 📊 Main Result

The project demonstrates that gravitational lensing contains potentially useful information about the underlying spacetime geometry.

Instead of relying only on whether an object has a "shadow", the analysis suggests looking at several properties together:

* Central intensity
* Shadow morphology
* Photon-ring structure
* Ring multiplicity
* Radial brightness profile
* Possible light transmission through the throat

A combination of these measurements could provide a stronger way to classify exotic compact-object candidates.

## ⚠️ Limitations

The current simulations are simplified and are mainly intended as a theoretical and computational proof of concept.

Important limitations include:

* The initial black-hole lensing model uses the weak-field approximation.
* The wormhole images are phenomenological rather than full relativistic ray-traced solutions.
* The complete Morris–Thorne photon geodesics have not yet been implemented.
* Realistic accretion disks and emission models are not included.
* Plasma and magnetic-field effects are ignored.
* Telescope resolution and observational noise are not simulated.
* The models do not yet include rotating black holes such as Kerr black holes.
* The illustrative detection score is not an established scientific classification method.

Therefore, the current results should be interpreted as **theoretical predictions and a foundation for further research**, rather than observational evidence for wormholes.

## 🚀 Future Work

The next stage of the project will focus on improving the physical realism of the simulations.

Planned improvements include:

1. **Full Schwarzschild ray tracing**
   Integrate null geodesics directly across an observer's image plane.

2. **Morris–Thorne geodesic ray tracing**
   Replace the phenomenological wormhole images with photon trajectories calculated directly from the wormhole metric.

3. **Realistic image formation**
   Include background sources, emission models, and relativistic effects.

4. **Accretion-disk modelling**
   Investigate how an accretion disk changes the observable differences between black holes and wormholes.

5. **Plasma and magnetic-field effects**
   Model astrophysical environments that could imitate or obscure lensing signatures.

6. **Kerr black holes**
   Compare wormhole signatures against rotating black holes rather than only idealized Schwarzschild black holes.

7. **Synthetic telescope observations**
   Add instrumental resolution, noise, and observational uncertainties.

8. **Machine-learning classification**
   Generate large datasets of simulated compact-object images and investigate whether machine-learning models can distinguish different spacetime geometries.

9. **Comparison with real observations**
   Eventually compare the simulations with high-resolution black-hole observations, including Event Horizon Telescope data where appropriate.

## 🌌 Research Goal

The long-term goal is to develop a physically consistent computational framework for testing whether gravitational lensing observations could distinguish **classical black holes from exotic compact objects such as traversable wormholes**.

The project is therefore not an attempt to claim a wormhole detection, but to ask:

> **What observable signatures would we expect if a traversable wormhole existed, and could those signatures be distinguished from those of a black hole?**

This notebook represents the first stage of that investigation and provides a foundation for developing a more rigorous relativistic ray-tracing and observational analysis pipeline.
