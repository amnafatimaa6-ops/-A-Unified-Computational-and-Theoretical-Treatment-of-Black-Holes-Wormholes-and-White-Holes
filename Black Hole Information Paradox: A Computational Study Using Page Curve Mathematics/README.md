# Black Hole Information Paradox: A Computational Study Using Page Curve Mathematics

## Overview

The **Black Hole Information Paradox** is one of the deepest unresolved problems at the intersection of General Relativity and quantum mechanics.

General Relativity predicts that matter and information can cross a black hole's event horizon. Hawking's semiclassical calculation later showed that black holes can emit thermal Hawking radiation and gradually evaporate.

This creates a fundamental question:

> If a black hole completely evaporates, what happens to the information contained within it?

If the Hawking radiation is purely thermal, the radiation appears to carry no information about the original quantum state. This conflicts with the principles of quantum mechanics, which require unitary evolution of quantum information.

This project develops a **computational toy model** of the problem using entropy evolution and the **Page Curve**.

The project has two main goals:

1. Illustrate the difference between Hawking's original information-loss picture and the unitary Page Curve picture.
2. Explore whether a machine-learning model can distinguish between the two idealised entropy behaviours.

**Important:** This project does **not** solve the Black Hole Information Paradox. It is a computational and educational exploration of the mathematical ideas behind the paradox.

---

## Scientific Question

The central question investigated is:

> **How does the entropy of Hawking radiation evolve during black hole evaporation under competing information-loss and information-preserving models?**

The project compares two simplified models.

### Hawking Information-Loss Model

Radiation entropy continuously increases as the black hole evaporates.

In the simplified model:

$$
S(t)=t
$$

This represents the idea that information remains inaccessible and the radiation becomes increasingly mixed.

### Page Curve Model

Radiation entropy initially increases, reaches a maximum near the Page Time, and then decreases.

The toy model uses:

$$
S(t)=
\begin{cases}
t, & t \leq t_{\mathrm{Page}},\\
N-t, & t > t_{\mathrm{Page}}.
\end{cases}
$$

This produces the characteristic rise-and-fall shape associated with a unitary evaporation scenario.

---

## Project Structure

The notebook is divided into four main parts:

```text
Part 1 — Black Hole Evaporation Toy Model
Part 2 — Page Curve Simulation
Part 3 — Scientific Analysis
Part 4 — Machine Learning Classification
