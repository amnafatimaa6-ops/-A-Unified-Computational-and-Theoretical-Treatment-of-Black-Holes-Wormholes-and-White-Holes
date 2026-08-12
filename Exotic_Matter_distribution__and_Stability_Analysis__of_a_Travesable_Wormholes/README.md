# Exotic Matter Distribution and Stability Analysis of a Traversable Wormhole

## 🌌 Project Overview

This project investigates the physical requirements for maintaining a **traversable wormhole** within General Relativity.

Using the **Morris–Thorne wormhole model**, I studied how the geometry of the wormhole determines the properties of the matter required to support it. The analysis focuses on the energy density, radial and tangential pressures, violation of the **Null Energy Condition (NEC)**, and the stability of the wormhole throat under small perturbations.

The project combines analytical General Relativity with Python-based numerical calculations and visualisation.

## 🔬 What I Investigated

The notebook includes:

* Morris–Thorne traversable wormhole geometry
* Wormhole shape function and its derivative
* Energy density distribution
* Radial pressure and radial tension
* Tangential pressure
* Null Energy Condition (NEC)
* Exotic matter distribution
* Effective potential for throat dynamics
* Numerical second-derivative stability analysis
* Visualisation of energy and pressure profiles

## 🧠 What I Found

The chosen wormhole model requires **negative energy density**, particularly near the wormhole throat.

The simulations showed that:

* Energy density remains negative throughout the modelled region.
* Radial pressure is negative, corresponding to radial tension.
* Tangential pressure is positive.
* The NEC quantity `ρ + pᵣ` remains below zero.
* NEC violation is strongest near the throat and decreases with distance.
* The exotic-matter contribution becomes weaker farther from the throat.

These results demonstrate the connection between the wormhole geometry and the unusual stress-energy required to keep the throat open.

### ⚠️ Stability Result

I also introduced a simplified effective potential to investigate the response of the wormhole throat to small radial perturbations.

For the particular effective potential used in this notebook, the calculated curvature at the throat was negative:

`V''(r₀) < 0`

This corresponds to an unstable equilibrium in **this specific simplified model**.

Therefore, the result should not be interpreted as proving that all Morris–Thorne wormholes are unstable. Wormhole stability depends on the chosen geometry, matter model, perturbation equations, and underlying gravitational theory.

## 📊 Main Scientific Insight

The project highlights two major physical challenges associated with traversable wormholes:

**1. Exotic matter**

Classical General Relativity requires violations of the Null Energy Condition for the chosen traversable wormhole geometry.

**2. Dynamical stability**

Even when a wormhole geometry is mathematically traversable, maintaining it as a stable physical configuration is a separate problem.

The results therefore show that **constructing a traversable geometry and demonstrating its dynamical stability are two different challenges.**

## ⚠️ Limitations

This study is based on an idealised theoretical model.

Important limitations include:

* The wormhole is static and spherically symmetric.
* A zero-tidal-force redshift function is assumed.
* The shape function is a specific analytical choice rather than a general solution.
* The exotic matter is described through an idealised stress-energy distribution.
* The stability analysis uses a simplified effective potential.
* The perturbation dynamics are not derived from the full Einstein field equations.
* Backreaction and realistic matter dynamics are not included.
* Quantum effects and semiclassical gravity are not modelled.
* The analysis does not establish that physically real wormholes can exist.

The results should therefore be considered a **computational exploration of a theoretical wormhole model**, rather than a realistic prediction of an astrophysical object.

## 🚀 Future Work

The next stage of the project could make the stability analysis substantially more rigorous.

### General Relativistic Stability

Derive the throat perturbation equations directly from the Einstein field equations instead of using a simplified potential.

### Different Wormhole Geometries

Test different shape functions and redshift functions to determine how the matter requirements and stability behaviour change.

### Exotic Matter Quantification

Calculate integrated measures of the NEC violation to estimate how much exotic matter is required to support the wormhole.

### Dynamic Simulations

Numerically evolve the wormhole throat after a small perturbation and study whether it collapses, expands, or returns towards equilibrium.

### Alternative Gravity Theories

Investigate whether modified theories of gravity can produce traversable wormhole solutions with reduced or different energy-condition violations.

### Quantum Effects

Explore whether semiclassical or quantum-field effects could provide mechanisms for producing the negative-energy contributions required by the geometry.

### Connection to Lensing

Combine this project with gravitational-lensing simulations to investigate whether the exotic matter distribution and wormhole stability influence observable lensing signatures.

### Machine Learning

Generate simulated wormhole and black-hole datasets and investigate whether machine-learning methods can identify differences in their gravitational signatures.

## 🌠 Research Goal

The broader goal of this project is to understand the relationship between **spacetime geometry, exotic matter, and stability** in traversable wormhole models.

The central question is:

> **What physical conditions would be required for a traversable wormhole to exist and remain stable?**

This project provides a computational starting point for investigating that question using General Relativity, numerical modelling, and eventually observational simulations.
