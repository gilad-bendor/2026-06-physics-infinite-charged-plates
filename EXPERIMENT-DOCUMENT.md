# Infinite Charged Plates — Experiment Document

> *The canonical specification for this project — **settled physics only**. LaTeX math
> renders in any Markdown preview (not in a bare text editor). Project direction, open
> questions, decisions, and session history live in `LAB-NOTEBOOK.md`.*

---

## 1. Purpose

This document is the single source of truth for the **physics** of a thought experiment in
**classical electromagnetism**: a finite array of infinite, parallel, uniformly charged
sheets that we slide within their own planes while monitoring the fields, the forces, and
the work involved. It defines the universe, fixes notation and assumptions, and records
everything we have established.

The core reframing that organizes everything: **a uniform infinite sheet sliding in its
own plane is, by symmetry, indistinguishable from where it started — so the static charge
layout never changes. All dynamics live in the _motion_ of the charge, i.e. in surface
currents and their time derivatives.** This experiment is, in essence, an array of
**radiating current sheets** coupled by the plane waves they emit.

---

## 2. The Universe

- A **finite number** $N$ of **infinite, flat sheets**, indexed $i = 1, \dots, N$.
- All sheets are **parallel**, each with its normal along the $x$-axis.
- Each sheet sits at a **fixed coordinate** $x_i$ (its $x$-position never changes) and
  is **rigid**.
- Each sheet carries a **uniform surface charge density** $\sigma_i$ (signed, in
  $\mathrm{C/m^2}$), fixed and "painted on."
- Each sheet may **translate rigidly within its own plane**: its position in $y$ and $z$
  is a prescribed function of time. Orientation and charge distribution never change.
- The surrounding medium is **vacuum**.

Because each sheet is infinite and uniform, sliding it in $y$ or $z$ maps it onto itself;
its $y, z$ *position* carries no physical information. Only its *velocity* and
*acceleration* matter.

---

## 3. Premises & Assumptions

These are the ground rules. Anything here is fair game to challenge — flag it explicitly
if we relax one.

1. **Non-relativistic speeds.** $|\mathbf{v}_i| \ll c$; surface charge density $\sigma_i$
   is constant (no Lorentz-contraction corrections).
2. **Prescribed motion.** We externally dictate each $\mathbf{v}_i(t)$ and measure the
   force required. Plates do **not** respond freely to incident fields.
   *(Alternative — self-consistent free dynamics — is an open direction; see
   `LAB-NOTEBOOK.md`.)*
3. **Non-conducting, painted charge.** Charge cannot redistribute and there are **no
   induced currents**. Consequence: no reflection or scattering — the total field is an
   exact superposition of the waves each sheet emits from its own prescribed motion. No
   multiple-bounce bookkeeping is ever needed.
4. **Electromagnetic accounting only.** Forces and work are tracked as electromagnetic.
   Mechanical inertia is set aside (an optional areal mass density $\mu_i$ can be added
   later; see `LAB-NOTEBOOK.md`).
5. **No external sources or fields**, no gravity, no boundaries at infinity (fields
   $\to 0$ far away unless emitted by a sheet).
6. **Retardation is fully retained** (see §4.5 and §7.8). No quasi-static approximation.

---

## 4. Coordinate System, Notation & Conventions

### 4.1 Axes

| Axis | Direction | Role |
|------|-----------|------|
| $x$  | left/right | **Normal** to all sheets; the stacking axis. Each $x_i$ is fixed. |
| $y$  | up/down    | In-plane; sheets may move freely. |
| $z$  | near/far   | In-plane; sheets may move freely. |

"In-plane" / "transverse" = the $y$–$z$ plane. "Longitudinal" / "normal" = the $x$ axis.

### 4.2 Symbols

| Symbol | Meaning | Units |
|--------|---------|-------|
| $\sigma_i$ | surface charge density of plate $i$ | $\mathrm{C/m^2}$ |
| $x_i$ | fixed position of plate $i$ along the normal | $\mathrm{m}$ |
| $\mathbf{v}_i(t)$ | in-plane velocity of plate $i$ | $\mathrm{m/s}$ |
| $\mathbf{K}_i(t) = \sigma_i\,\mathbf{v}_i(t)$ | surface current density of plate $i$ | $\mathrm{A/m}$ |
| $d_{ij} = \lvert x_i - x_j\rvert$ | inter-plate separation | $\mathrm{m}$ |
| $\mathbf{E}, \mathbf{B}$ | electric / magnetic field | $\mathrm{V/m}$, $\mathrm{T}$ |
| $f$ | force **per unit area** (a stress) | $\mathrm{N/m^2}$ |
| $\mathcal{P}$ | power **per unit area** | $\mathrm{W/m^2}$ |
| $W$ | work **per unit area** | $\mathrm{J/m^2}$ |

### 4.3 Math conventions

- Vectors: `\mathbf{E}`, `\mathbf{v}`, `\mathbf{K}`. Unit vectors: $\hat{\mathbf{x}}, \hat{\mathbf{y}}, \hat{\mathbf{z}}$.
- Plate indices: subscripts $i, j$. Field components: $E_x, E_y, E_z$ (so $E_{i,y}$ is the
  $y$-component at plate $i$).
- Retarded time: $t_r = t - d_{ij}/c$.
- **SI units throughout.**

### 4.4 The "infinite sheet" remedy

Every extensive quantity (charge, force, energy) is infinite for an infinite sheet, so we
work entirely in **per-unit-area** quantities. The natural per-area power flux is the
**Poynting vector** $\mathbf{S} = \tfrac{1}{\mu_0}\mathbf{E}\times\mathbf{B}$
($\mathrm{W/m^2}$), which does our radiated-energy bookkeeping.

### 4.5 Regime: full electrodynamics, wave zone

Retardation is non-negligible: the light-travel time between plates $\tau_{ij} = d_{ij}/c$
is **not** small compared with the timescale of plate motion. Equivalently, for motion at
frequency $f$ (wavelength $\lambda = c/f$), separations satisfy $d_{ij} \gg \lambda$ — we
are in the **radiation/wave zone**, not the near-field/quasi-static zone. Plate $j$'s
motion reaches plate $i$ only after $\tau_{ij}$, by which time $j$ may have completed many
cycles. We therefore use the full time-dependent Maxwell equations and retarded fields.

---

## 5. Quantities of Interest (what we monitor)

For each plate $i$ and time $t$:

1. **Field experienced** — the total $\mathbf{E}(x_i,t)$ and $\mathbf{B}(x_i,t)$ at the
   plate, split into the field from **other** plates and the plate's **own** (self) field.
   For force purposes we use the **average across the two faces** of the sheet.
2. **Force per unit area** $\mathbf{f}_i$ — and the applied force
   $\mathbf{f}_i^{\text{app}} = -\mathbf{f}_i$ needed to maintain the prescribed motion.
3. **Power / work per unit area** — $\mathcal{P}_i = \mathbf{f}_i^{\text{app}}\cdot\mathbf{v}_i$
   and $W_i = \int \mathcal{P}_i\,dt$ — and the total radiated power flux via $\mathbf{S}$.

---

## 6. The Master Relations (single source for simulation & analysis)

These collect the established results into the equations that fully describe the system
under the assumptions of §3. Derivations and reasoning are in §7.

**Static (longitudinal) field at plate $i$** — purely the Coulomb field of the *other*
plates (a plate's own static field averages to zero at itself):
$$
E_{i,x}^{\text{stat}} = \frac{1}{2\varepsilon_0}\sum_{j \neq i}\sigma_j\,\operatorname{sgn}(x_i - x_j),
\qquad E_{i,y}^{\text{stat}} = E_{i,z}^{\text{stat}} = 0 .
$$

**Dynamic (transverse) field at plate $i$** — superposition of the retarded plane waves
from every plate (the $j = i$ term, at zero delay, is the self / radiation-reaction term):
$$
\boxed{\;\mathbf{E}_{i,\perp}(t) = -\frac{\mu_0 c}{2}\sum_{j}\sigma_j\,\mathbf{v}_j\!\left(t - \frac{d_{ij}}{c}\right)\;}
\qquad d_{ii} = 0 .
$$

**In-plane force per unit area on plate $i$** (the working force; the magnetic force is
normal — see §7.6):
$$
\mathbf{f}_i = \sigma_i\,\mathbf{E}_{i,\perp}(t)
= -\frac{\mu_0 c\,\sigma_i}{2}\sum_{j}\sigma_j\,\mathbf{v}_j\!\left(t - \frac{d_{ij}}{c}\right).
$$

**Applied force, power, and work per unit area:**
$$
\mathbf{f}_i^{\text{app}} = -\mathbf{f}_i, \qquad
\mathcal{P}_i = \mathbf{f}_i^{\text{app}}\cdot\mathbf{v}_i, \qquad
W_i = \int_0^T \mathcal{P}_i\,dt .
$$

> Everything the experiment asks about is contained in these boxed relations plus the
> single-sheet emission formula in §7.5.

---

## 7. Established Results & Key Insights

### 7.1 Everything depends on $x$ and $t$ only (plane waves)

The sources are invariant under translations in $y$ and $z$ at every instant, so the
fields inherit that symmetry: every component is a function of $x$ and $t$ alone, uniform
across each plane $x = \text{const}$. The problem is effectively **1-D in space ($x$) plus
time**, and all radiation is **plane waves** propagating along $\pm x$.

### 7.2 Longitudinal / transverse decomposition

The fields split into two non-interacting families:
- **Longitudinal ($x$):** the static electric field. Sourced by charge.
- **Transverse ($y, z$):** the radiative fields. Sourced by time-varying current.

### 7.3 The magnetic field has no normal component — ever

$$ B_x \equiv 0 . $$
From $\nabla = \hat{\mathbf{x}}\,\partial_x$: Gauss's law for magnetism gives
$\partial_x B_x = 0$ and Faraday's law gives $\partial_t B_x = 0$, so $B_x$ is a global
constant — zero with no imposed background. Physically, only in-plane currents exist, and
they produce only in-plane $\mathbf{B}$.

### 7.4 The electric field's $x$-component is purely static Coulomb

$E_x$ is the only longitudinal component and it is **time-independent**
($\partial_t E_x = 0$, since there is no current along $x$). Radiation never contributes
to $E_x$. The transverse components $E_y, E_z$ are **purely radiative** — nonzero only
when there is in-plane acceleration along that axis. In short: *the time-varying part of
$\mathbf{E}$ is entirely transverse.*

### 7.5 Single-sheet emission (the building block)

For one sheet at $x_0$ with charge $\sigma$ and prescribed in-plane velocity
$\mathbf{v}(t)$ (current $\mathbf{K} = \sigma\mathbf{v}$):

Static Coulomb field:
$$
\mathbf{E}_{\text{stat}}(x) = \frac{\sigma}{2\varepsilon_0}\,\operatorname{sgn}(x - x_0)\,\hat{\mathbf{x}} .
$$
Radiated plane waves (valid both sides; $\mathbf{E}_{\text{rad}}$ is continuous across the
sheet, $\mathbf{B}_{\text{rad}}$ flips sign):
$$
\mathbf{E}_{\text{rad}}(x,t) = -\frac{\mu_0 c}{2}\,\sigma\,\mathbf{v}\!\left(t - \frac{|x-x_0|}{c}\right),
$$
$$
\mathbf{B}_{\text{rad}}(x,t) = -\frac{\mu_0}{2}\,\operatorname{sgn}(x - x_0)\;\hat{\mathbf{x}}\times\Big[\sigma\,\mathbf{v}\!\left(t - \tfrac{|x-x_0|}{c}\right)\Big].
$$
These satisfy Faraday's and Ampère's laws and the surface-current jump condition
$\hat{\mathbf{x}}\times(\mathbf{B}_{\text{above}} - \mathbf{B}_{\text{below}}) = \mu_0\mathbf{K}$.

**Field/motion pairing** (since radiated $\mathbf{E}\parallel\mathbf{K}$ and
$\mathbf{B}\perp$ both): motion along $y \Rightarrow (E_y, B_z)$; motion along
$z \Rightarrow (E_z, B_y)$. If no plate ever moves in $z$, the $(E_z, B_y)$ family stays
identically zero.

### 7.6 Self-field & radiation reaction

A sheet sits symmetrically in its own field, so **almost all of its self-field averages
to zero at its own location**: the static $E_x$ (opposite signs on the two sides), and
both the static and radiated $\mathbf{B}$ (which flip sign). The one surviving self term
is the in-plane radiated electric field:
$$
\mathbf{E}_{\text{self}}(x_0,t) = -\frac{\mu_0 c}{2}\,\sigma\,\mathbf{v}(t),
\qquad
\mathbf{f}_{\text{self}} = \sigma\,\mathbf{E}_{\text{self}} = -\frac{\mu_0 c\,\sigma^2}{2}\,\mathbf{v}(t).
$$
This is a **velocity-proportional drag** — the radiation reaction. Unlike the point-charge
case, it is finite, well-behaved (per unit area), and free of runaway/pre-acceleration
pathologies.

### 7.7 Energy balance

Power per area we must supply against the self-drag:
$$
\mathcal{P}_{\text{rad}} = -\mathbf{f}_{\text{self}}\cdot\mathbf{v} = \frac{\mu_0 c\,\sigma^2}{2}\,|\mathbf{v}|^2 .
$$
This is exactly the Poynting flux carried away by the two emitted waves
($\mathcal{P} = 2\times \tfrac{\mu_0 c}{4}\sigma^2 |\mathbf{v}|^2$). Energy is conserved:
the work done against the drag becomes radiated field energy.

### 7.8 Forces: which one does work

The total force per area on a sheet is
$\mathbf{f} = \sigma\,\mathbf{E}_{\text{avg}} + \mathbf{K}\times\mathbf{B}_{\text{avg}}$.
- The **magnetic** term: $\mathbf{K}$ and the external $\mathbf{B}$ are both in-plane, so
  $\mathbf{K}\times\mathbf{B}$ points along $\hat{\mathbf{x}}$ — **normal** to the sheet.
  It is absorbed by whatever holds $x_i$ fixed and **does no work**.
- The **electric** term (in-plane) is the only force that does work on the moving sheet.

So magnetism never directly drives the $y$/$z$ motion; it appears only as a normal stress
and as the energy carrier of the radiated waves.

---

## 8. Glossary

- **Surface charge density $\sigma$** — charge per unit area on a sheet.
- **Surface current density $\mathbf{K}$** — current per unit length crossing a line in
  the sheet; here $\mathbf{K} = \sigma\mathbf{v}$.
- **Longitudinal / transverse** — along the normal $x$ / within the $y$–$z$ plane.
- **Retardation** — the finite light-travel delay $d_{ij}/c$ in field propagation.
- **Radiation reaction** — the force a sheet's own emitted field exerts back on it; here a
  velocity-proportional drag.
- **Quasi-static** — the (here *invalid*) approximation of instantaneous interaction.
- **Poynting vector $\mathbf{S}$** — electromagnetic power flux per unit area.
