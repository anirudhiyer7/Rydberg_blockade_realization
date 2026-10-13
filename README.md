# Foundations to Rydberg-Based Quantum Simulation

**Course Project:** PH303: SLP (Autumn Semester 2026–27)  
**Author:** Anirudh Iyer  

---

## Overview

This repository explores the fundamentals of Rydberg-atom interactions and computationally models **Rydberg blockade mechanisms**. By accounting for realistic experimental constraints—such as position uncertainties, thermal velocities, external magnetic fields, and Zeeman state overlaps—this project recreates two-atom blockade dynamics and extends the theoretical framework to ensemble qubits and 1D Ising spin chains.

---

## Key Features & Modules

### 1. Rydberg Interactions & Scaling Laws
* **Förster & van der Waals Regimes:** Calculates dipole-dipole interactions ($V_{dd} \propto 1/R^3$) and van der Waals interactions ($V_{vdw} \propto -C_6/R^6$).
* **Blockade Radius ($R_b$):** Models energy level shifts suppressing double excitation ($|V(R)| \gg \hbar\Omega$).
* **State Scaling:** Implements principal quantum number ($n$) scaling relations for lifetimes ($\propto n^3$) and interaction strengths ($\propto n^{11}$).

### 2. Zeeman Maps & Magnetic Field Effects
* Simulates fine structure state shifts under a **$1.15\text{ mT}$ magnetic field** ($z$-direction).
* Models level shifts and cross-state overlaps to evaluate real-world blockade energy shifts ($B$) and double-excitation probabilities ($P_2$).
<p align="center">
<img width="336" height="176" alt="image" src="https://github.com/user-attachments/assets/6fd69cfa-303b-4329-9bca-97dccaaac731" />
<br>Zeeman map around |79d⟩ states.
</p>
<p align="center">
<img width="517" height="143" alt="image" src="https://github.com/user-attachments/assets/fff5e7df-baee-4a8d-9bf9-9a7034109934" />
<br>Plotting change in potentials with distance between atoms
</p>

### 3. Two-Atom Blockade & Pulse Simulation
* **Realistic Trajectories:** Draws initial positions ($a_y = 5.8 \mu\text{m}$, $\sigma_z \approx 1.5–1.65 \mu\text{m}$) and thermal velocity profiles for control/target atom pairs.
* **Pulse Sequence Simulation:** Implements time-evolution propagators under Rotating Wave Approximation (RWA):
  1. $\pi$-pulse on control atom ($|g_c\rangle \to |r_c\rangle$).
  2. Rabi oscillation pulse of length $t$ on target atom.
  3. $\pi$-pulse restoring control atom ($|r_c\rangle \to |g_c\rangle$).
* Evaluates target ground-state survival probability $P(\text{ground})$ with and without the control atom.
<p align="center">
<img width="388" height="197" alt="image" src="https://github.com/user-attachments/assets/4e551629-eafd-48ab-967d-1ee12d91999b" />
<br>Blockade shift variation
</p>
<p align="center">
<img width="470" height="173" alt="image" src="https://github.com/user-attachments/assets/e624dce5-bb1d-4fa6-bf73-373a0b17963f" />
<br>Monte-carlo Simulations using position error profile
</p>
---

## Core Mathematical Framework

* **System Hamiltonian (RWA):**
  $$\frac{H}{\hbar} = -\Delta_c n_c - \Delta_t n_t - \frac{\Omega_c}{2}\sigma_x^{(c)} - \frac{\Omega_t}{2}\sigma_x^{(t)} + \Delta_{dd}n_c n_t$$

* **Blockade Shift Formula:**
  $$P_2 = \frac{\Omega^2}{\Omega^2 + 2B^2} \implies B = \Omega\sqrt{\frac{1-P_2}{2P_2}}$$
## References
* Developed for PH303 SLP, Autumn Semester 2026–27.
* Experimental parameters adapted from standard Rydberg optical trap setups.
