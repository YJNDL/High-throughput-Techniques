---
layout: post
title: "exfoliating crystallographic plane (ECP) v1.0"
date: 2025-05-19
author: "Yongle Zhong"
image: ""
---

# Bond Density Evaluation and Crystallographic Plane Exfoliation

This repository provides computational methods to identify crystallographic planes suitable for exfoliation from non-van der Waals (non-vdW) bulk materials by evaluating bond density and performing systematic structural exfoliation simulations.


## Bond Density Evaluation and Plane Selection

Efficiently screen and identify exfoliable crystallographic planes through the following workflow:

### 1. Acquiring XRD Patterns

> **Note:** Combine experimental data from the Materials Project or ICSD database with calculated peak positions to identify matches for selection. 

```bash
python simulate_xrd.py
```

### 2. Identify Crystallographic Planes

```bash
python identify_planes.py
```

### 3. Bond Density Analysis

```bash
python bond_density_scan.py
```

Planes exhibiting relatively low bond density are promising for exfoliation.

### 4. Calculating Anisotropic Binding Strength

For those crystallographic plane with low bond density. Use common density functional theory (DFT) software to calculate bonding strengths and determine the differences between out-of-plane and in-plane bonding. 

The definition of Anisotropic Binding Strength is as follows: The Binding Strength calculated by DFT software is used to assess the in-plane and out-of-plane bonds of the respective crystal plane. The difference between the Binding Strength of the out-of-plane bonds and in-plane bonds is then divided by the surface area to obtain the Anisotropic Binding Strength.

---

## Step-wise Exfoliation Procedure

> **Note:** DFT-D3 van der Waals corrections are integrated into all exfoliation simulations.

Follow these detailed steps to simulate the exfoliation process:

### 1. Align Structure

Rotate the crystal structure to align the targeted exfoliation plane perpendicular to the c-axis.

### 2. Stretch and Relax Structure

Incrementally stretch the lattice normal to the exfoliation plane, moving the outermost atomic layer approximately Δd = 0.1~0.2 Å per step, followed by structural relaxation at each increment.

---

## Dependencies

* Python version: 3.9–3.12
* Required Python libraries: `numpy`, `scipy`, `matplotlib`, `pymatgen`, `ase`

Install dependencies via:

```bash
pip install numpy scipy matplotlib pymatgen ase
```

---

## References

The methodologies used incorporate established computational techniques, including DFT-D3 for energy calculations. Please ensure proper referencing when using these methodologies in your publications.

---

## License

This project is licensed under the MIT License.