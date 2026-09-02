# Data-Driven Discovery of Accretion Disk Hydrodynamics

## Overview

This project implements data-driven system identification to extract the continuous partial differential equations (PDEs) governing astrophysical fluid transport in thin accretion disks directly from discrete spatiotemporal data.

Using numerical simulations of the surface mass density field $\Sigma(R, t)$, the framework compares **Standard SINDy (PDE-FIND)** and **Weak SINDy (WSINDy)** to reconstruct the Shakura–Sunyaev transport equation:

$$\frac{\partial \Sigma}{\partial t} = 3\nu \frac{\partial^2 \Sigma}{\partial R^2} + \frac{9\nu}{2R} \frac{\partial \Sigma}{\partial R}$$

---

## Key Features

1. **Hydrodynamic Simulation**: Forward simulation of viscous spreading of a Gaussian ring around compact objects.
2. **Sparse Equation Discovery**: Candidate library construction $\mathbf{\Theta}(\Sigma)$ and sparse regression using Sequentially Thresholded Least Squares (STLSQ).
3. **Weak Formulation (WSINDy)**: Convolving data with smooth test functions $\psi(R, t)$ to transfer derivatives off noisy data via integration by parts.
4. **Pareto Model Selection**: Automated identification of the optimal 2-term physical model at the Pareto knee (minimizing Fraction of Variance Unexplained vs. model complexity).
5. **Noise Benchmark**: Systematic stress-testing against $0\%\text{--}20\%$ Gaussian observational noise, demonstrating WSINDy stability where point-derivative methods fail.

