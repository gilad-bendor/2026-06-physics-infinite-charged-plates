# Infinite Charged Plates — Lab Notebook

> *The working document: **where we are and where we're going**. Current focus, roadmap,
> open questions, decisions, and session history. The **settled physics** lives in
> `EXPERIMENT-DOCUMENT.md` — when something here becomes settled, it moves there and is
> deleted from this file.*

---

## 1. Current Focus

The foundational framework is complete (`EXPERIMENT-DOCUMENT.md` §§1–7) and the master
relations are derived. The immediate next target is the **two-plate sinusoidal base
case**: $N = 2$, each plate driven sinusoidally in-plane. We want to work out the retarded
coupling, the phase lag $\omega d/c$ between the plates, the difference between in-phase
and anti-phase drive, and the energy exchanged between the two plates versus radiated to
infinity.

**New ingredient (2026-06-19): a common normal drift.** The whole stack now drifts along
its normal $x$ at a shared constant velocity $u\hat{\mathbf{x}}$ (spec §2). This is a
Galilean boost of the old static-$x_i$ universe, so it leaves the separations and the
transverse master relation untouched — but it opens a **normal power channel**: the
Coulomb and magnetic forces along $x$ now act through a displacement and do work (spec
§7.9). For the $N = 2$ case this means we additionally track $\mathcal{P}_{i,x} = -u f_{i,x}$,
whose net is the radiation-pressure recoil $-u F_x^{\text{tot}}$.

---

## 2. Where We're Heading (Roadmap)

1. **$N = 2$ sinusoidal base case** *(current focus)* — phase lag $\omega d/c$, in-phase
   vs. anti-phase behavior, energy exchange, and how a neighbor's retarded field modifies
   the effective drag on each plate.
2. **General $N$, prescribed motion** — superposition and interference from multiple
   retarded sources; patterns in the force/work as a function of geometry and drive.
3. **Numerical simulation** — a direct time-domain solver to validate the analytics
   (the 1-D-in-$x$, retarded current-sheet array is very clean to simulate).
4. **Extensions** — radiation pressure / momentum along $x$; relaxing assumptions.

---

## 3. Open Questions

The deeper parking lot (the immediate next step lives in §1–§2):

- **Standing-wave / cavity-like effects** between plates arising purely from retardation
  interference, despite there being no reflection.
- **Sign and stability of the inter-plate coupling** as a function of separation $d_{ij}$
  and drive frequency — when does a neighbor's retarded field *assist* versus *oppose* a
  plate's motion?
- **Net momentum / radiation pressure along $x$** from the normal magnetic force
  $\mathbf{K}\times\mathbf{B}$ — now *activated* by the drift: its work is the net normal
  power $-u F_x^{\text{tot}}$ (spec §7.9). Open: compute $F_x^{\text{tot}}$ for the $N = 2$
  sinusoidal case and check it against the $x$-momentum flux of the emitted waves.
- **The $O(u/c)$ in-plane magnetic cross-force** $\sigma u\,\hat{\mathbf{x}}\times\mathbf{B}_\perp$
  (spec §7.8): a small drift-induced correction to the in-plane force/power. Worth a clean
  derivation — is it a genuine aberration/Doppler effect, and does it survive a careful
  non-relativistic accounting?
- **Massless-vs-free-drift tension.** The drift is *prescribed* constant because massless
  sheets cannot accelerate freely along $x$ ($f_x = 0$ degeneracy). If we ever want
  radiation to genuinely accelerate the plates along $x$, we must reintroduce mass for the
  normal degree of freedom — a separate universe to branch, not patch.
- **A clean definition of efficiency** — energy radiated to infinity vs. work supplied by
  the applied force.
- **Relaxing assumptions:** conducting sheets (induced currents, reflection, multiple
  scattering), finite conductivity, relativistic speeds.

---

## 4. Decisions & Rationale

Choices already made and why — so we don't relitigate them or re-explore dead ends.

- **Prescribed motion.** We dictate $\mathbf{v}_i(t)$ and measure the force required. This
  isolates the field/force/work questions. Free self-consistent dynamics is not on the
  table: with massless sheets there is no inertial term ($\mu_i\dot{\mathbf{v}}_i = \mathbf{f}_i$
  degenerates to the constraint $\mathbf{f}_i = 0$), so free dynamics would require
  reintroducing mass — a different universe.
- **Non-conducting, "painted" charge.** No induced currents ⇒ no reflection or scattering
  ⇒ the total field is an exact superposition of each plate's independently-emitted waves.
  This is precisely what makes the master-relation single sum exact (`EXPERIMENT-DOCUMENT.md`
  §6).
- **Massless sheets (no mechanical inertia).** A firm premise, not a deferral. It keeps the
  accounting purely electromagnetic and isolates the field/force/work questions; with no
  kinetic-energy term, every energy quantity is field energy.
- **Non-relativistic speeds.** A premise; keeps $\sigma_i$ constant.
- **Versioning by timestamped folders**, not an in-document change log — keeps the spec
  clean.
- **Two-document split.** `EXPERIMENT-DOCUMENT.md` holds only settled physics; this
  notebook holds direction and process. No fact lives in both files.
- **Common constant normal drift $u\hat{\mathbf{x}}$** (2026-06-19). Chosen over per-plate
  normal velocities because a *shared* drift keeps all $d_{ij}$ fixed — it is a Galilean
  boost, so the retarded master relations survive intact (the "small" change) while still
  exposing the new $x$-power channel (the "fundamental" change). Per-plate velocities would
  make the geometry time-dependent (Doppler, possible collisions / sgn flips) and rewrite
  §6 wholesale — deferred.
- **Drift is prescribed and constant, not radiation-driven.** The user's instinct was that
  "the only acceleration along $x$ is from radiation." Taken literally that is *free*
  normal dynamics, which is incompatible with massless sheets ($f_x = 0$ degeneracy). We
  resolved it the consistent way: $u$ is a prescribed constant, the applied force maintains
  it, and radiation pressure is simply the net normal force whose *work* we now book as the
  $x$-power. Genuine radiation-driven $x$-acceleration is parked under Open Questions.
- **The $x$-power is frame-dependent, not free energy.** Because the drift is a boost, the
  normal power vanishes in the comoving frame; the invariant content is the radiated energy
  ($\S$7.7) and momentum ($F_x^{\text{tot}}$). We keep the lab-frame accounting but state
  the frame-dependence explicitly (spec §7.9) so we never mistake it for energy creation.

---

## 5. Session Log

Short, dated entries — "what we just did." Keep it lean; deep history is preserved in
`versions/`.

- **2026-06-19 — Framework established & project set up.**
  - Defined the universe (finite set of infinite parallel charged sheets, normals along
    $x$, fixed $x_i$, free in-plane motion) and the premises.
  - Established the core physics: $y$–$z$ symmetry ⇒ all fields depend on $x, t$ only
    (plane waves); the longitudinal/transverse split; $B_x \equiv 0$; $E_x$ is purely the
    static Coulomb field; $E_y, E_z$ are purely radiative; the field/motion pairing.
  - Derived the single-sheet emission formula; showed the self-field reduces to a
    velocity-proportional radiation-reaction drag; verified energy balance against the
    Poynting flux.
  - Assembled the master relations for $N$ plates (the boxed retarded sum, whose $j = i$
    term recovers the radiation reaction).
  - Created the project scaffolding: `EXPERIMENT-DOCUMENT.md`, `CLAUDE.md`, this notebook,
    and the `versions/` workflow.

- **2026-06-19 — Committed to the massless, prescribed-motion universe.**
  - Dropped the "self-consistent free dynamics" alternative from the spec's prescribed-motion
    premise.
  - Made **massless sheets** a firm, uncontested premise (spec §3.4) and purged mass /
    areal-mass-density $\mu_i$ from everywhere. Removed free dynamics from the roadmap (it
    requires an inertial term and is therefore a different universe).

- **2026-06-19 — Added a common normal drift $u\hat{\mathbf{x}}$ (the $x$-power channel).**
  - Changed the universe (spec §2): the whole stack now drifts along its normal at one
    shared constant velocity $u$, so $x_i(t) = x_i^0 + ut$ with all $d_{ij}$ fixed.
  - Worked out the consequences: $E_x$ becomes a **convected** (non-radiative) Coulomb
    field (§7.4); $B_x \equiv 0$ and the transverse master relation survive unchanged (the
    drift carries no transverse current); the **normal forces now do work**, opening the
    $x$-power channel $\mathcal{P}_{i,x} = -u f_{i,x}$, whose net is the radiation-pressure
    recoil $-u F_x^{\text{tot}}$ (§§7.8–7.9).
  - Flagged two subtleties in the spec/notebook: the $x$-power is **frame-dependent** (a
    Galilean boost — not new energy), and a new **$O(u/c)$ in-plane magnetic cross-force**
    appears.
  - Resolved the "acceleration only from radiation" wish as prescribed-constant drift
    (masslessness forbids free $x$-acceleration); parked true radiation-driven drift under
    Open Questions.
