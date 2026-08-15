# PASSC correction network (PyTorch)

**Status: to be uploaded.**

This directory will contain the PyTorch implementation of the PASSC
post-processing stage described in Section 6 of the manuscript, including:

- the Fourier-feature residual network (128-wide, 8 residual blocks,
  SiLU + LayerNorm, free-stream-initialized output),
- the shock-weighted data-consistency loss over the last K = 10 FEM snapshots,
- the derivative-free space–time control-volume physics loss with
  scale-stratified sampling, macro conservation windows, face-sharing tiling
  patches, and the entropy-admissibility hinge penalty,
- the soft boundary-condition losses (inflow free-stream state, cylinder slip),
- the continuously interpolated loss-weight curriculum, AdamW training loop
  (3,000 epochs), and model selection on the unweighted evaluation metric.

Training consumes the FEM snapshots written by `../fem_solver/` and is driven
by the same per-Mach configuration files in `../configs/`.
