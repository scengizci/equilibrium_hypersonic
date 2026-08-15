# Mesh

Unstructured triangular mesh used in **all four** computations
(M∞ = 2.0, 5.0, 8.0, 12.0).

| Property | Value |
|---|---|
| File | `scengizci_refined.xml` (legacy DOLFIN XML format) |
| Nodes | 23,934 |
| Triangular elements | 47,264 |
| Domain | [0, 2] m × [0, 1] m |
| Cylinder | radius R = 0.05 m, centered at (0.5, 0.5) m |
| Near-wall resolution | layers of constant-thickness elements around the cylinder |

## Loading the mesh in FEniCS

```python
from dolfin import Mesh
mesh = Mesh("mesh/scengizci_refined.xml")
```

## Boundaries

The boundary portions are identified in the solver as follows:

| Boundary | Location | Treatment |
|---|---|---|
| Inflow | x₁ = 0 | Strong Dirichlet, free-stream state |
| Outflow | x₁ = 2 | Do-nothing (consistent Euler normal flux) |
| Top / bottom | x₂ = 0, x₂ = 1 | Do-nothing (consistent Euler normal flux) |
| Cylinder surface | ‖x − (0.5, 0.5)‖ = 0.05 | Penalty-free weak slip (u·n = 0) |

See `figures/mesh_full.png` and `figures/mesh_zoom.png` for visualizations.
