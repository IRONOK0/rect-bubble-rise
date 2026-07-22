# OpenFOAM Axisymmetric Bubble Rise Simulation

Axisymmetric wedge case simulating a single buoyancy-driven air bubble rising in water, solved using `foamRun` with the incompressible VoF (Volume of Fluid) solver module.

## Domain

- Axisymmetric wedge geometry
- Radius: 12 mm
- Height: 120 mm
- Bubble: centered at (0, 4mm, 0), radius 2mm
- Boundaries: all closed (domain not exposed to atmosphere)

## Solver

`foamRun` (incompressibleVoF module)

## Prerequisites

- OpenFOAM (v14 or compatible, with `foamRun` support)

## Clone and Run
git clone https://github.com/IRONOK0/rect-bubble-rise.git
cd rect-bubble-rise
blockMesh
foamRun

## Post-processing

Results can be viewed in ParaView (`paraFoam`). 
