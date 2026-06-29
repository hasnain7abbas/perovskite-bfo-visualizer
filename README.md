# Perovskite and BFO Visualizer

This is a small interactive visual companion for section 1.6, focused on the perovskite structure and bismuth ferrite.

Open the visualizer and rotate the default `2 x 2 x 2` supercell to see how the ideal cubic `ABO3` parent turns into the distorted BFO `R3c` structure. The eight connected cells make the three-dimensional corner-sharing network and antiphase rotations visible. A one-cell comparison remains available for learning the basic site positions.

The model deliberately exaggerates some movements so the teaching points are legible: the 12-coordinate A-site cage, the 6-coordinate B-site `FeO6` octahedron, shared oxygen vertices, cooperative tilting, polar displacement along `[111]`, and the Goldschmidt tolerance factor.

## What It Shows

- Ideal cubic perovskite, `Pm3m`
- Default `2 x 2 x 2` supercell with 8 B sites, 8 connected octahedra, 27 visible boundary/shared A positions, and 36 unique oxygen positions
- B-site off-centre displacement, like the common titanate ferroelectric route
- Cooperative antiphase `BO6` octahedral tilting, with alternating colors for opposite rotation senses
- BFO `R3c` with the `a^-a^-a^-` rotation pattern plus Bi/Fe polar displacement along `[111]`
- Tolerance factor behavior around BFO's approximate `t = 0.96`
- BFO reference details: `a_hex = 5.578 A`, `c_hex = 13.868 A`, `a_pc = 3.965 A`, rhombohedral angle `89.4 deg`, and Bi displacement about `0.6 A`

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
- The default model contains 8 cells and 8 octahedra, while the one-cell comparison contains 1 of each
- Tolerance-factor controls update the displayed value and tilt explanation
- The 3D canvas renders nonblank on desktop and mobile
- No browser console errors were reported
