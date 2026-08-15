# ✈️ Aerodynamic & CFD Analysis of Wings and Airfoils

Comparative aerodynamic study of wing geometry effects using lifting-line theory (XFLR5), validated against 2D CFD simulation (ANSYS Fluent).

---

## Part A — Aspect Ratio Study

Three rectangular wings (NACA 2415 airfoil, no twist/dihedral, 1 m chord) were modeled in XFLR5 at 50 m/s using lifting-line theory, sweeping angle of attack from −5° to 15°:

| Wing | Aspect Ratio | Planform |
|---|---|---|
| 1a | 5 | Rectangular |
| 2a | 10 | Rectangular |
| 3a | 15 | Rectangular |

**Generated for each wing:** Cl vs. α, Cl/Cd vs. α, Cd vs. α, Oswald efficiency (e) vs. α, and spanwise distributions (local Cl, induced/effective angle of attack, downwash velocity, induced Cd) at α = 5°.

![Cl vs Alpha - AR Comparison](images/cl-alpha-AR.png)
![Oswald Efficiency - AR Comparison](images/oswald-AR.png)
*Add: comparison plots for AR 5/10/15*

**Lift curve slope** was tabulated from XFLR5 results and compared against the theoretical finite-wing lift curve slope equation from lecture.

---

## Part B — Taper Ratio Study

Three tapered wings (AR = 10, NACA 2415, 1 m root chord) were analyzed the same way:

| Wing | Taper Ratio |
|---|---|
| 1b | 0.2 |
| 2b | 0.6 |
| 3b | 1.0 (rectangular baseline) |

![Cl vs Alpha - Taper Comparison](images/cl-alpha-taper.png)
*Add: comparison plots for TR 0.2/0.6/1.0*

---

## Part C — Discussion

**Aspect ratio effects:** Higher AR wings showed reduced induced drag and higher Oswald efficiency, at the cost of increased structural bending moment for a fixed span-loading — a classic long/thin vs. short/stiff tradeoff.

**Taper ratio effects:** Moderate taper (TR ≈ 0.4–0.6) approximates the elliptical lift distribution most closely, minimizing induced drag without the manufacturing complexity of a true elliptical planform.

**Design recommendation:** For a low-speed application, AR 10 with TR ≈ 0.6 was identified as the best balance of induced-drag performance, structural practicality, and manufacturability.

---

## 🔬 CFD Validation (ANSYS Fluent)

**NACA 2415 airfoil**, Re = 1,000,000, α from −3° to +21° (3° increments):
- Cl, Cd, and Cl/Cd vs. α plotted and compared directly against XFLR5 results
- Velocity and pressure contours captured at 0° and 10° AoA

![Fluent vs XFLR5 Cl Comparison](images/fluent-xflr5-cl.png)
![Velocity Contour 10deg](images/velocity-contour-10deg.png)
*Add: Cl/Cd comparison plots and contour screenshots*

**2D flat plate boundary layer** (L = 100 cm, U∞ = 2 m/s, laminar, viscous):
- Velocity/pressure contours, boundary layer profiles at x = 25/50/75 cm compared to Blasius theory
- Wall shear stress, skin friction coefficient, and drag coefficient vs. theoretical predictions

**2D cylinder flow** (D = 1 m, inviscid / laminar / turbulent):
- Velocity contours with streamlines, pressure contours, surface velocity and Cp distributions, and drag coefficients across all three flow regimes, compared against experimental drag data

![Cylinder Wake Comparison](images/cylinder-wake.png)
*Add: streamline/wake comparison across inviscid, laminar, turbulent cases*

---

## 🎥 Videos
- [Wing 2a geometry + XFLR5 workflow](#) — *add YouTube link*
- [Wing 2b geometry + XFLR5 workflow](#) — *add YouTube link*
- [NACA 2415 Fluent workflow, Re = 1,000,000](#) — *add YouTube link*

---

## 🛠️ Tools Used
`XFLR5` `ANSYS Fluent` `Microsoft Excel`

## 📁 Repo Contents
- `XFLR5_Wing_Analysis.pdf` — full Part A/B/C writeup
- `Fluent_Airfoil_Bonus.pdf` — NACA 2415 Fluent vs. XFLR5 comparison
- `Fluent_FlatPlate_Cylinder.pdf` — boundary layer and bluff-body simulations
- `Wing_Analysis_Data.xlsx` — raw data and generated plots
- `images/` — contour screenshots and comparison plots
