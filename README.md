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
