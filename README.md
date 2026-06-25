# Perovskite and BFO Visualizer

This is a small interactive visual companion for section 1.6, focused on the perovskite structure and bismuth ferrite.

Open the visualizer and rotate the unit cell to see how the ideal cubic `ABO3` parent turns into the distorted BFO `R3c` structure. The model deliberately exaggerates some movements so the teaching points are visible: A-site corners, B-site centre, face-centred oxygens, the `FeO6` octahedron, octahedral tilting, polar displacement along `[111]`, and the Goldschmidt tolerance factor.

## What It Shows

- Ideal cubic perovskite, `Pm3m`
- B-site off-centre displacement, like the common titanate ferroelectric route
- Cooperative `BO6` octahedral tilting
- BFO `R3c` with octahedral rotation plus Bi/Fe polar displacement along `[111]`
- Tolerance factor behavior around BFO's approximate `t = 0.96`

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
- Tolerance-factor controls update the displayed value and tilt explanation
- The 3D canvas renders nonblank on desktop and mobile
- No browser console errors were reported
