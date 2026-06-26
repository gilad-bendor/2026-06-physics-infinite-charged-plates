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
own plane is, by symmetry, indistinguishable from where it started — so the in-plane motion
leaves the static charge layout unchanged, and all radiative dynamics live in the _motion_
of the charge, i.e. in surface currents and their time derivatives.** This experiment is,
in essence, an array of **radiating current sheets** coupled by the plane waves they emit.
The one motion that *does* relocate the charge is the **common normal drift** $u\hat{\mathbf{x}}$
(§2) — but it does so rigidly, as a Galilean boost; it carries the Coulomb layout along
without radiating, and its sole new effect is to make the normal forces do work (§7.9).

---

## 2. The Universe

- A **finite number** $N$ of **infinite, flat sheets**, indexed $i = 1, \dots, N$.
- All sheets are **parallel**, each with its normal along the $x$-axis.
- The **whole stack drifts** along its normal at a **common, constant velocity**
  $u\,\hat{\mathbf{x}}$: sheet $i$ sits at $x_i(t) = x_i^0 + u\,t$. Because the drift is
  shared, every separation $d_{ij} = |x_i - x_j|$ stays **constant** and the stack never
  changes shape. Each sheet remains **rigid**.
- Each sheet carries a **uniform surface charge density** $\sigma_i$ (signed, in
  $\mathrm{C/m^2}$), fixed and "painted on."
- Each sheet may **translate rigidly within its own plane** as well: its position in $y$
  and $z$ is a prescribed function of time. Orientation and charge distribution never
  change.
- The surrounding medium is **vacuum**.

Because each sheet is infinite and uniform, sliding it in $y$ or $z$ maps it onto itself;
its $y, z$ *position* carries no physical information. Only its *velocity* and
*acceleration* matter.

Sliding along the normal $x$ is **different**: it relocates the sheet, so a sheet's $x$
*position* does carry physical information (it sets the Coulomb geometry). But because the
stack drifts **rigidly** at one shared $u$, only the **common drift** and the **fixed
separations** $d_{ij}$ enter — the absolute $x$-origin remains free. A common rigid drift
is just a **Galilean boost** of the static-$x_i$ universe; its new physical content is what
that boost exposes in the **lab frame** (§7.9): the normal forces now act through a
displacement, and therefore do work.

---

## 3. Premises & Assumptions

These are the ground rules. Anything here is fair game to challenge — flag it explicitly
if we relax one.

1. **Non-relativistic speeds.** $|\mathbf{v}_i| \ll c$; surface charge density $\sigma_i$
   is constant (no Lorentz-contraction corrections).
2. **Prescribed motion.** We externally dictate each plate's velocity and measure the
   force required; plates do **not** respond freely to incident fields. The velocity has
   two prescribed parts — a **common constant normal drift** $u\,\hat{\mathbf{x}}$ shared
   by all plates, and the per-plate **in-plane** motion $\mathbf{v}_{i,\perp}(t)$:
   $$\mathbf{v}_i(t) = u\,\hat{\mathbf{x}} + \mathbf{v}_{i,\perp}(t).$$
3. **Non-conducting, painted charge.** Charge cannot redistribute and there are **no
   induced currents**. Consequence: no reflection or scattering — the total field is an
   exact superposition of the waves each sheet emits from its own prescribed motion. No
   multiple-bounce bookkeeping is ever needed.
4. **Massless sheets — electromagnetic accounting only.** The sheets carry **no
   mechanical inertia** (no mass). Consequently there is no kinetic-energy term for the
   sheets; all forces and work are purely electromagnetic, and every energy quantity we
   track is field energy. Because they are massless, the normal drift $u$ is **prescribed
   and constant**, not free: a massless sheet cannot undergo a finite radiation-*driven*
   normal acceleration (free dynamics would force the degenerate $f_x = 0$). So the applied
   force maintains the constant $u$, and we read off the **normal power** it must supply.
   Letting radiation genuinely accelerate the plates along $x$ would require giving them
   mass — a different universe (see the notebook).
5. **No external sources or fields**, no gravity, no boundaries at infinity (fields
   $\to 0$ far away unless emitted by a sheet).
6. **Retardation is fully retained** (see §4.5 and §7.8). No quasi-static approximation.

---

## 4. Coordinate System, Notation & Conventions

### 4.1 Axes

| Axis | Direction | Role |
|------|-----------|------|
| $x$  | left/right | **Normal** to all sheets; the stacking axis. The stack drifts along $x$ at common constant $u$ (separations $d_{ij}$ fixed). |
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

- Vectors: $\mathbf{E}$, $\mathbf{v}$, $\mathbf{K}$. Unit vectors: $\hat{\mathbf{x}}, \hat{\mathbf{y}}, \hat{\mathbf{z}}$.
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
The common normal drift leaves every $d_{ij}$ constant, so the retarded delays
$\tau_{ij}$ are themselves unchanged (no time-dependent geometry, no Doppler at leading
order).

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
   With the drift switched on, $\mathbf{v}_i = u\hat{\mathbf{x}} + \mathbf{v}_{i,\perp}$, so
   the power splits into an **in-plane** part $\mathcal{P}_{i,\perp} =
   \mathbf{f}_{i,\perp}^{\text{app}}\cdot\mathbf{v}_{i,\perp}$ and the **new normal part**
   $\mathcal{P}_{i,x} = f_{i,x}^{\text{app}}\,u$ (zero when $u = 0$).

---

## 6. The Master Relations (single source for simulation & analysis)

These collect the established results into the equations that fully describe the system
under the assumptions of §3. Derivations and reasoning are in §7.

**Longitudinal (convected-Coulomb) field at plate $i$** — purely the Coulomb field of the
*other* plates (a plate's own static field averages to zero at itself). The drift makes
this pattern *translate* rigidly at $u$, but because every separation is fixed its **value
at each plate is unchanged**:
$$
E_{i,x}^{\text{stat}} = \frac{1}{2\varepsilon_0}\sum_{j \neq i}\sigma_j\,\operatorname{sgn}(x_i - x_j),
\qquad E_{i,y}^{\text{stat}} = E_{i,z}^{\text{stat}} = 0 .
$$

**Dynamic (transverse) field at plate $i$** — superposition of the retarded plane waves
from every plate (the $j = i$ term, at zero delay, is the self / radiation-reaction term).
Only the **in-plane** velocity radiates; the normal drift carries no transverse current:
$$
\boxed{\;\mathbf{E}_{i,\perp}(t) = -\frac{\mu_0 c}{2}\sum_{j}\sigma_j\,\mathbf{v}_{j,\perp}\!\left(t - \frac{d_{ij}}{c}\right)\;}
\qquad d_{ii} = 0 .
$$

**In-plane force per unit area on plate $i$** (the leading working force):
$$
\mathbf{f}_{i,\perp} = \sigma_i\,\mathbf{E}_{i,\perp}(t)
= -\frac{\mu_0 c\,\sigma_i}{2}\sum_{j}\sigma_j\,\mathbf{v}_{j,\perp}\!\left(t - \frac{d_{ij}}{c}\right)
\;\;(+\,\text{an } O(u/c)\text{ magnetic term, §7.8}).
$$

**Normal ($x$) force per unit area on plate $i$** — the Coulomb force plus the magnetic
radiation-pressure force; both point along $\hat{\mathbf{x}}$ (self terms average to zero,
$\mathbf{K}_{i,\perp} = \sigma_i\mathbf{v}_{i,\perp}$):
$$
f_{i,x} = \sigma_i\,E_{i,x}^{\text{stat}} + \big(\mathbf{K}_{i,\perp}\times\mathbf{B}_{i,\perp}\big)_x .
$$

**Applied force, power, and work per unit area** ($\mathbf{v}_i = u\hat{\mathbf{x}} + \mathbf{v}_{i,\perp}$):
$$
\mathbf{f}_i^{\text{app}} = -\mathbf{f}_i, \qquad
\mathcal{P}_i = \underbrace{\mathbf{f}_{i,\perp}^{\text{app}}\cdot\mathbf{v}_{i,\perp}}_{\text{in-plane}}
            + \underbrace{(-u\,f_{i,x})}_{\text{normal (new)}}, \qquad
W_i = \int_0^T \mathcal{P}_i\,dt .
$$

**Net normal power** — summed over all plates the Coulomb terms cancel in action–reaction
pairs ($\sum_i \sigma_i E_{i,x}^{\text{stat}} = 0$), leaving only the radiation-pressure
recoil:
$$
\sum_i \mathcal{P}_{i,x} = -u\,F_x^{\text{tot}}, \qquad
F_x^{\text{tot}} = \sum_i \big(\mathbf{K}_{i,\perp}\times\mathbf{B}_{i,\perp}\big)_x .
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

### 7.4 The electric field's $x$-component is the convected Coulomb field — non-radiative

$E_x$ is the only longitudinal component. With the stack drifting it is **no longer
static**: each moving charged sheet carries a normal current $J_x = \sigma_i u$ at its
location, and the $x$-component of Ampère's law gives $\partial_t E_x = -J_x/\varepsilon_0$
there. But this is nothing more than the rigid **translation** of the Coulomb step pattern
at speed $u$ — the *boosted* electrostatic field, **not radiation**. For a single sheet,
$$
E_x(x,t) = \frac{\sigma}{2\varepsilon_0}\,\operatorname{sgn}\!\big(x - x_i(t)\big),
\qquad
\partial_t E_x = -\frac{\sigma u}{\varepsilon_0}\,\delta\big(x - x_i(t)\big),
$$
which is exactly $-J_x/\varepsilon_0$. Because the common drift keeps every separation
fixed, the **value of $E_x$ sampled at each plate is unchanged** from the static-$x_i$ case
(§6). Radiation still never contributes to $E_x$. The transverse components $E_y, E_z$
remain **purely radiative** — nonzero only with in-plane acceleration. In short: *the
time-varying part of $\mathbf{E}$ splits into a non-radiative convected-Coulomb piece
(longitudinal) and the radiative transverse piece.*

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
identically zero. The **normal drift** $u\hat{\mathbf{x}}$ adds a longitudinal current
$\sigma u$ but no transverse current, and at constant velocity no acceleration: it sources
**no radiated wave** (only the convected Coulomb field of §7.4). So $\mathbf{v}$ here means
the in-plane velocity $\mathbf{v}_\perp$.

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
pathologies. The constant normal drift contributes **nothing** here: it neither radiates
(§7.5) nor breaks the self-field's symmetry ($E_x^{\text{self}}$ and $\mathbf{B}^{\text{self}}$
still average to zero at the sheet), so there is no self-force along $x$. The drag stays
purely in-plane, set by $\mathbf{v}_\perp$ alone.

### 7.7 Energy balance

Power per area we must supply against the self-drag:
$$
\mathcal{P}_{\text{rad}} = -\mathbf{f}_{\text{self}}\cdot\mathbf{v} = \frac{\mu_0 c\,\sigma^2}{2}\,|\mathbf{v}|^2 .
$$
This is exactly the Poynting flux carried away by the two emitted waves
($\mathcal{P} = 2\times \tfrac{\mu_0 c}{4}\sigma^2 |\mathbf{v}|^2$). Energy is conserved:
the work done against the drag becomes radiated field energy.

### 7.8 Forces: which ones do work (now both channels)

The total force per area on a sheet is
$\mathbf{f} = \sigma\,\mathbf{E}_{\text{avg}} + \mathbf{K}\times\mathbf{B}_{\text{avg}}$,
with $\mathbf{K} = \sigma\,(u\hat{\mathbf{x}} + \mathbf{v}_\perp)$ and $\mathbf{B}$ in-plane
($B_x \equiv 0$ still — the normal current sources no $\mathbf{B}$). Resolving into normal
and in-plane parts:

- **In-plane forces.** The transverse electric force $\sigma\mathbf{E}_\perp$ — the leading
  driver of the $y/z$ motion — **plus** a smaller magnetic term
  $\sigma\,u\,\hat{\mathbf{x}}\times\mathbf{B}_\perp$ that the drift newly switches on
  (in-plane $\times$ normal-velocity), of relative size $O(u/c)$.
- **Normal ($x$) forces.** The Coulomb force $\sigma E_x^{\text{stat}}$ **plus** the
  magnetic radiation-pressure force $\sigma\,\mathbf{v}_\perp\times\mathbf{B}_\perp$ (both
  along $\hat{\mathbf{x}}$).

**What changed.** With $x_i$ pinned, the normal forces did no work (they were absorbed by
the constraint). Now the sheet drifts at $u$, so the normal forces act through a real
displacement and **do work** — the new $x$-power channel (§7.9). In particular **magnetism
now does work**: the radiation-pressure force, moving at $u$, transfers energy. It still
never *drives the $y/z$ motion* directly (its in-plane piece is only the $O(u/c)$ term
above), but it is no longer work-free.

### 7.9 The normal power channel and its frame dependence

Because the stack drifts at $u$, each normal force delivers power $\mathcal{P}_{i,x} =
-u\,f_{i,x}$ (§6), in two pieces:

- **Coulomb part** $-u\,\sigma_i E_{i,x}^{\text{stat}}$. Summed over all plates these
  cancel in action–reaction pairs ($\sum_i \sigma_i E_{i,x}^{\text{stat}} = 0$): **no net**
  power, only a reshuffling of energy *between* plates as the rigid Coulomb pattern drifts.
- **Radiation-pressure part** $-u\,(\mathbf{K}_{i,\perp}\times\mathbf{B}_{i,\perp})_x$.
  These need **not** cancel: the emitted waves carry net $x$-momentum, the stack feels a
  net normal force $F_x^{\text{tot}}$, and holding the drift against it costs (or yields)
  net power $-u\,F_x^{\text{tot}}$.

**Frame dependence (important).** A common rigid drift is a Galilean boost of the
static-$x_i$ universe, so this normal power is **not a new source of energy**. In the
**comoving frame** the plates have no normal motion, the normal power is identically zero,
and the only energy leaving the system is the transverse radiation of §7.7. The lab-frame
$x$-power is the boost's bookkeeping: force $\times$ velocity is frame dependent, and the
net piece $-u\,F_x^{\text{tot}}$ is precisely the radiated **momentum** flux
$F_x^{\text{tot}}$ carried along by the drift $u$. Energy and momentum are conserved in
both frames; only their split into "work along $x$" versus "radiated energy" differs.

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
- **Drift velocity $u$** — the common, constant speed at which the whole stack translates
  along its normal $x$; a shared Galilean boost that leaves all separations $d_{ij}$ fixed.
- **Convected Coulomb field** — the ordinary electrostatic field of the charges, rigidly
  carried along by the drift; time-dependent in the lab frame but non-radiative.
- **Radiation pressure** — the net normal ($x$) force from the magnetic
  $\mathbf{K}\times\mathbf{B}$ term, equal to the $x$-momentum flux carried by the emitted
  waves; its work is the net normal power once $u \neq 0$.
