# OpenFOAM v14 — Rectangular Tube Bubble Rise Simulation

Two-phase (water–air) VOF simulation of a single spherical air bubble rising under
buoyancy inside a closed rectangular tube, solved using OpenFOAM-14's
`incompressibleVoF` solver via `foamRun`.

## Domain

* Container size: **12 mm × 12 mm × 120 mm** (width × depth × height)
* Mesh: hex mesh, **20 × 200 × 20** cells, uniform grading (`blockMesh`)
* Gravity: `(0 -9.81 0)` m/s² → acts along **−y**, so y is the vertical axis
* Boundary patches:
  * `leftWall`, `rightWall`, `lowerWall` — no-slip solid walls
  * `atmosphere` — top face, vented to atmospheric pressure
* Phases: water (ρ = 1000 kg/m³, ν = 1e-06 m²/s) and air (ρ = 1 kg/m³, ν = 1.48e-05 m²/s)
* Surface tension (water–air): σ = 0.07 N/m
* Flow regime: laminar
* Initial bubble: sphere, centre **(0, 4, 6) mm**, radius **2 mm**, defined in `0/alpha.water`
* Simulation time: 0 → 6 s, adjustable time step (`maxCo = 1`, `maxAlphaCo = 1`)

## Solver

`foamRun` (incompressibleVoF module)

## Prerequisites

* OpenFOAM (v14 or compatible, with `foamRun` support)

## Clone and Run

```bash
git clone https://github.com/IRONOK0/rect-bubble-rise.git
cd rect-bubble-rise

blockMesh      # generate the mesh
foamRun        # run the incompressibleVoF solver
```

## Post-processing

Results can be viewed in ParaView (`paraFoam`).
