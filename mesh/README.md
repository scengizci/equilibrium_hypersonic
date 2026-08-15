# Mesh

Unstructured triangular mesh used in **all four** computations
(M∞ = 2.0, 5.0, 8.0, 12.0).

| Property | Value |
|---|---|
| Nodes | 23,934 |
| Triangular elements | 47,264 |
| Domain | [0, 2] m × [0, 1] m |
| Cylinder | radius R = 0.05 m, centered at (0.5, 0.5) m |
| Near-wall resolution | layers of constant-thickness elements around the cylinder |

The mesh is stored in FEniCS-readable XDMF/HDF5 format:

- `cylinder_mesh.xdmf` / `cylinder_mesh.h5` — mesh geometry and topology
- `cylinder_facets.xdmf` / `cylinder_facets.h5` — boundary facet markers
  (inflow, outflow, top/bottom, cylinder surface)

Boundary marker convention used by the solver:

| Marker | Boundary | Treatment |
|---|---|---|
| 1 | Inflow (x₁ = 0) | Strong Dirichlet, free-stream state |
| 2 | Outflow (x₁ = 2) | Do-nothing (consistent Euler normal flux) |
| 3 | Top / bottom (x₂ = 0, 1) | Do-nothing (consistent Euler normal flux) |
| 4 | Cylinder surface | Penalty-free weak slip (u·n = 0) |
