# Numerical Geodesics Around a Schwarzschild Black Hole

## Overview

This notebook numerically solves the geodesic equations of General Relativity to simulate the motion of particles around a non-rotating Schwarzschild black hole.

The project starts from the Schwarzschild metric, derives the relevant geodesic equations for equatorial motion, converts the second-order equations into a first-order system, and solves them numerically using the fourth-order Runge–Kutta (RK4) method.

The resulting trajectories are visualised as orbital paths around the black hole.

The purpose of this project is to demonstrate how the geometry of curved spacetime can be translated into a numerical computational model.

---

## Research Question

> How does spacetime curvature around a Schwarzschild black hole affect particle trajectories, and can these trajectories be reproduced by numerically integrating the geodesic equations?

---

## Physics

The Schwarzschild metric describes spacetime outside a non-rotating, uncharged, spherically symmetric mass:

$$
ds^2 =
-\left(1-\frac{2M}{r}\right)dt^2
+
\left(1-\frac{2M}{r}\right)^{-1}dr^2
+
r^2d\theta^2
+
r^2\sin^2\theta\,d\phi^2
$$

The simulation uses geometric units:

$$
G=c=1
$$

and sets

$$
M=1.
$$

Because of spherical symmetry, the particle's trajectory can be restricted to the equatorial plane:

$$
\theta=\frac{\pi}{2}.
$$

This reduces the problem to the coordinates:

$$
(t,r,\phi).
$$

---

## Geodesic Equations

Free-falling particles follow geodesics of spacetime:

$$
\frac{d^2x^\mu}{d\lambda^2}
+
\Gamma^\mu_{\alpha\beta}
\frac{dx^\alpha}{d\lambda}
\frac{dx^\beta}{d\lambda}
=0.
$$

Here:

- $x^\mu$ are spacetime coordinates
- $\lambda$ is an affine parameter
- $\Gamma^\mu_{\alpha\beta}$ are the Christoffel symbols

Only the non-zero terms relevant to equatorial Schwarzschild motion are implemented in the numerical solver.

---

## State Vector

Because RK4 solves first-order differential equations, the second-order geodesic equations are rewritten using:

$$
u^t=\frac{dt}{d\lambda},
\qquad
u^r=\frac{dr}{d\lambda},
\qquad
u^\phi=\frac{d\phi}{d\lambda}.
$$

The numerical state vector is therefore:

$$
\mathbf{y}
=
(t,r,\phi,u^t,u^r,u^\phi).
$$

The RK4 solver updates all six components during each integration step.

---

## Numerical Method

The trajectory is calculated using the fourth-order Runge–Kutta method.

For each step, RK4 evaluates the differential equations at four intermediate points:

$$
k_1,\quad k_2,\quad k_3,\quad k_4
$$

and combines them according to:

$$
y_{n+1}
=
y_n+
\frac{h}{6}
(k_1+2k_2+2k_3+k_4).
$$

RK4 was chosen instead of the simpler Euler method because the latter evaluates the local slope only once per step. RK4 samples the evolution at multiple points within each step, providing substantially better numerical accuracy for curved trajectories.

---

## Initial Conditions

The simulation begins with:

$$
r=8M
$$

which places the particle outside the Schwarzschild event horizon:

$$
r_s=2M.
$$

The initial radial velocity is:

$$
u^r=0
$$

so the particle initially has no inward or outward radial motion.

The initial angular velocity is:

$$
u^\phi=0.05.
$$

Changing these initial conditions can produce different orbital behaviours, including bound trajectories, inward spirals, or escape trajectories.

---

## Numerical Parameters

| Parameter | Value |
|---|---:|
| Black-hole mass | $M=1$ |
| Units | $G=c=1$ |
| Initial radius | $r=8M$ |
| Initial radial velocity | $u^r=0$ |
| Initial angular velocity | $u^\phi=0.05$ |
| Integration step | $h=0.01$ |
| Integration steps | 5000 |
| Numerical method | RK4 |

---

## Visualisation

The numerical solver produces the trajectory in polar coordinates $(r,\phi)$.

These coordinates are converted into Cartesian coordinates:

$$
x=r\cos\phi
$$

$$
y=r\sin\phi.
$$

The resulting plot shows the simulated particle trajectory together with the black hole and its event horizon.

An animation can also be generated to visualise the particle's evolution along the trajectory.

---

## Computational Workflow

```text
Schwarzschild Metric
        ↓
Equatorial-plane simplification
        ↓
Christoffel Symbols
        ↓
Geodesic Equations
        ↓
First-order State Vector
        ↓
RK4 Numerical Integration
        ↓
Particle Trajectory
        ↓
Polar → Cartesian Conversion
        ↓
Orbit Visualisation
