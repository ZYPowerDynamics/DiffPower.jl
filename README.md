# DiffPower.jl

DiffPower.jl is an open-source Julia package that provides a differentiable modeling framework for
simulation, analysis, and parameter optimization of large-scale
power systems. In DiffPower.jl, buses, lines, and dynamic devices
are modeled as modular differentiable components and automatically
composed into a unified nonlinear ordinary-differentialequation
representation. The same assembled model is used
consistently for time-domain simulation, automatic linearization,
modal analysis, participation-factor analysis, parameter sensitivity
analysis, and stability-oriented parameter tuning. By leveraging
the Julia SciML ecosystem, automatic differentiation, sparse
Jacobian construction, graph coloring, and high-performance
sparse linear algebra, DiffPower.jl reduces the need for manually
maintained Jacobians while enabling scalable electromagnetictransient-
level studies. An IEEE 300-bus workflow demonstrates
the package’s capabilities in large-scale differentiable model
construction, equilibrium diagnostics, sparse Jacobian evaluation,
eigenvalue-based stability assessment, sensitivity-guided parameter
optimization, and dynamic simulation.

Please refer to the latest paper that is present in the 2026 EI2 conference for detailed introductions.

[2026 EI2 conference paper](DiffPower.jl_2026EI2.pdf)

## Current code and tested case

This repository contains the DiffPower Julia module for electromagnetic transient (EMT) simulation using averaged inverter models. The tested case is a single inverter connected to an infinite bus, with simulation results consistent with MATLAB/Simulink using the same averaged model. Voltage-command delay is modeled explicitly using delay differential equations (DDEs). We plan to register DiffPower as a Julia package in the near future.
## Contents

- `src/`: network composition, power flow, device models, fault models, and numerical Jacobian utilities.
- `src/ieee_cases/`: IEEE 9-, 14-, 39-, and 118-bus case data.
- `examples/`: single-device and IEEE network simulation scripts.

## Running an example

From the repository directory, install dependencies and run the example:

```julia
using Pkg
Pkg.activate(".")
Pkg.instantiate()
include("examples/single_device_test.jl")
```

The core module imports ModelingToolkit, SciMLBase, JLD2, ForwardDiff, SymbolicIndexingInterface, DifferentiationInterface, ADTypes, and SparseMatrixColorings, plus Julia standard libraries. Examples additionally use solver and plotting packages such as OrdinaryDiffEq, OrdinaryDiffEqSDIRK, CairoMakie, LinearSolve, and DelayDiffEq.

The Julia package is named `DiffPower`; its entry point is `src/DiffPower.jl`. The examples have not been validated in a fresh standalone environment as part of this repository preparation.
