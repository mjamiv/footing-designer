# footing-designer

Spread Footing Designer Pro — Footing Analysis and Design for structural engineers (preliminary use only).

## What this program does

This is a single-file web application (index.html) that performs preliminary analysis and design of rectangular spread footings using simplified methods and checks per ACI 318-19. Key capabilities:

- Interactive inputs for applied loads and geometry:
  - Axial load (P), moments (Mx, My), and lateral force (H)
  - Footing geometry: length (L), width (B), thickness (h), embedment depth (Df)
  - Column/pedestal sizes (length × width)
  - Load factors (dead/live)
- Material and soil properties:
  - Concrete strength f'c, reinforcing steel fy, clear cover
  - Allowable bearing (qa), soil unit weight, friction coefficient
- Stability and serviceability checks:
  - Bearing capacity (qmax ≤ qa)
  - Uplift/tension (qmin ≥ 0)
  - Overturning safety (FS_OT, simple lever-arm check)
  - Sliding resistance (FS_SL using friction)
- Strength design checks (simplified, ACI 318-19 style):
  - One-way (beam) shear
  - Two-way (punching) shear around the column
- Flexural reinforcement design:
  - Required and provided As for long and short directions
  - Automatic selection of common US rebar sizes and spacing (#5–#9 by default)
  - Estimates for effective depth, minimum steel ratio, and development length (simplified)
- Outputs and quantities:
  - Corner and maximum/minimum bearing pressures
  - Design status summary and pass/fail checks
  - Material quantities (concrete CY, rebar lbs), excavation volume, and a simple cost estimate
- Visualization and UX:
  - 3D soil stress visualization canvas with view controls (3D stress, section, plan, reinforcement)
  - Rotation control for the visualization
  - Auto-size footing button to run a simple sizing routine
  - Print and export buttons for reports

## How to use

1. Open index.html in a modern browser (no build step required).
2. Enter project and engineer information if desired.
3. Change input values (loads, geometry, materials). The app recalculates on input changes.
4. Use "Auto-Size Footing" to attempt an automatic sizing (simple heuristic built into the page).
5. Review the stability checks, strength checks, reinforcement recommendations, visualizations, and quantity estimates.
6. Print or export the results. Always verify final designs with a licensed Professional Engineer.

## Units and assumptions

- Units are mixed but documented in the UI: loads in kips, pressures in ksf, lengths in ft/in, stresses in psi.
- The app uses simplified hand-calculation style formulas and conservative assumptions to provide preliminary results. It does not replace detailed engineering judgment, geotechnical reports, or code-level checks beyond the basic ACI-style equations implemented.

## Implementation notes

- The application is contained in index.html and uses vanilla JavaScript and a Tailwind browser CDN for styling.
- Rebar properties are approximated from US bar sizes; design/sizing logic is intentionally simplified.

## Disclaimer

Calculations are for preliminary design only. Use at your own risk. All designs must be reviewed and stamped by a licensed Professional Engineer before construction.

---

If you want, I can update the README to add example screenshots, a quick start GIF, or expand the description of the auto-sizing algorithm. Please tell me which additions you'd like.
