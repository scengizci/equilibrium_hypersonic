# Configuration files

**Status: to be uploaded.**

One configuration file per free-stream Mach number, covering both stages
(FEM solver + PASSC training):

- `M2.0.yaml`  — supersonic case (C_Δt = 0.5)
- `M5.0.yaml`  — hypersonic case (C_Δt = 0.5)
- `M8.0.yaml`  — hypersonic case (C_Δt = 0.4)
- `M12.0.yaml` — hypersonic case (C_Δt = 0.4)

Common settings: ρ∞ = 1.165 kg/m³, T∞ = 300 K, N₂ (R = 296.8 J/(kg·K),
γ = 1.4), t_f = 1.0 × 10⁻³ s, β = 2, C_YZβ = 15.
