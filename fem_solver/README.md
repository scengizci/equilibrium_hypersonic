# SUPG-YZβ stabilized finite element solver (FEniCS)

**Status: to be uploaded.**

This directory will contain the FEniCS implementation of the compressible-flow
SUPG formulation with YZβ shock-capturing described in Sections 3–5 of the
manuscript, including:

- primitive-variable (ρ, u₁, u₂, T) P1 discretization on triangles,
- τ_SUGN1-based stabilization parameter and scaled YZβ shock-capturing
  viscosity (β = 2, C_YZβ = 15), frozen per time step,
- penalty-free weak slip condition on the cylinder via the inviscid wall flux,
- semi-implicit backward Euler time marching with damped Newton–Raphson
  iterations (MUMPS) and CFL-based adaptive time stepping,
- snapshot output of the primitive vertex fields at every accepted step
  (consumed by the PASSC training stage).

One driver script will cover all four Mach numbers through the configuration
files in `../configs/`.
