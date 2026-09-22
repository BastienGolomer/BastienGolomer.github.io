---
layout: page
title: "Differentiable Influence Matrix Calculation Using Automatic Differentiation"
description: Internship project, AMAS Lab / Center for Proton Therapy, PSI (2022–2023)
importance: 1
category: research
---

**Internship project, AMAS Lab / Center for Proton Therapy, Paul Scherrer Institut (2022–2023).**

FIonA's (CPT's in-house treatment planning system) dose-influence-matrix calculation relies on look-ups and indexing operations that are not differentiable, which blocks gradient-based optimization of spot positions, energies, and field angles for treatment planning.

This project rewrote the core of that pipeline — water-equivalent depth (WED) calculation and influence-matrix (D<sub>ij</sub>) elements — as a fully differentiable pipeline in [Julia](https://julialang.org/), using [Enzyme.jl](https://enzyme.mit.edu/) for reverse-mode automatic differentiation of GPU kernels via [KernelAbstractions.jl](https://github.com/JuliaGPU/KernelAbstractions.jl). Key steps:

- **Water-equivalent depth**: trilinear interpolation of the density matrix for a continuous, differentiable representation along the beam trajectory.
- **Influence-matrix elements**: preprocessing of look-up tables (initial phase-space spreads via linear interpolation, multiple Coulomb scattering curves via 4th-order polynomial fits) to remove non-differentiable indexing, followed by differentiable interpolation for the dose calculation itself.

Validated against FIonA's reference dose distributions across multiple patients: mean difference of 0.001%, with 98.5%+ of voxels within ±1%. This became the foundation for the beam-angle-selection work in the [MSc thesis]({{ '/projects/1_proton_therapy_planning/' | relative_url }}).
