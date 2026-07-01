# Perovskite and BFO Visualizer

This is a small interactive visual companion for section 1.6, focused on the perovskite structure and bismuth ferrite.

Open the visualizer and rotate the default `2 x 2 x 2` supercell to see how the ideal cubic `ABO3` parent turns into the distorted BFO `R3c` structure. The eight connected cells make the three-dimensional corner-sharing network and antiphase rotations visible. Pseudocubic, primitive rhombohedral, and conventional hexagonal cell settings are available for direct comparison.

The model deliberately exaggerates some movements so the teaching points are legible: the 12-coordinate A-site cage, the 6-coordinate B-site `FeO6` octahedron, shared oxygen vertices, cooperative tilting, polar displacement along `[111]`, and the Goldschmidt tolerance factor.

## What It Shows

- Ideal cubic perovskite, `Pm3m`
- Default `2 x 2 x 2` supercell with 8 B sites, 8 connected octahedra, 27 visible boundary/shared A positions, and 36 unique oxygen positions
- Pseudocubic 5-atom basis: `1 Bi + 1 Fe + 3 O`
- Primitive rhombohedral `R3c` cell: `2 Bi + 2 Fe + 6 O = 10 atoms`
- Conventional hexagonal `R3c` setting: `6 Bi + 6 Fe + 18 O = 30 atoms`
- Independent Bi/A, Fe/B, and oxygen sublattice visibility
- Isolated BiO12 coordination cage and FeO6 oxygen octahedron views
- B-site off-centre displacement, like the common titanate ferroelectric route
- Cooperative antiphase `BO6` octahedral tilting, with alternating colors for opposite rotation senses
- BFO `R3c` with the `a^-a^-a^-` rotation pattern plus Bi/Fe polar displacement along `[111]`
- Tolerance factor behavior around BFO's approximate `t = 0.96`
- BFO reference details: `a_hex = 5.578 A`, `c_hex = 13.868 A`, `a_pc = 3.965 A`, rhombohedral angle `89.4 deg`, and Bi displacement about `0.6 A`

The 5-atom pseudocubic view is intentionally described as a reference basis. It is excellent for naming sites and pseudocubic directions, but the full antiphase `R3c` rotation pattern requires the 10-atom primitive rhombohedral cell. The 30-atom hexagonal view is the conventional hexagonal setting of the same `R3c` structure, not a separate hexagonal BFO phase.

The room-temperature hexagonal lattice parameters and fractional coordinates follow the synchrotron refinement reported by Palai et al. The two-formula-unit primitive `R3c` description follows the established diffraction structure and first-principles convention.

## Run Locally

From the repository root:

```powershell
python -m http.server 8765 --bind 127.0.0.1 --directory outputs
```

Then open:

```text
http://127.0.0.1:8765/perovskite-bfo-visualizer.html
```

The Three.js runtime files are vendored under `outputs/vendor`, so the page does not depend on a CDN after checkout.

## Verification

The visualizer was checked with automated browser tests on desktop and mobile sizes. The verification confirmed:

- BFO mode reports `R3c`, `3.965 A`, `89.4 deg`, and `[111]`
- The default model contains 8 connected cells and 8 octahedra
- Cell-setting checks confirm exactly 5, 10, and 30 atoms
- The hexagonal setting resolves to exactly 6 Bi, 6 Fe, and 18 O
- Coordination focus resolves exactly 12 oxygen neighbours around Bi and 6 around Fe
- Bi/A, Fe/B, and O sublattices can be independently hidden or shown
- Tolerance-factor controls update the displayed value and tilt explanation
- The 3D canvas renders nonblank on desktop and mobile
- No browser console errors were reported

## Structure Sources

- [Palai et al., Physical Review B 77, 014110 (2008)](https://doi.org/10.1103/PhysRevB.77.014110)
- [Moreau et al., Journal of Physics and Chemistry of Solids 32, 1315-1320 (1971)](https://doi.org/10.1016/S0022-3697(71)80189-0)
- [Young et al., Physical Review Letters 109, 236601 (2012)](https://doi.org/10.1103/PhysRevLett.109.236601)
