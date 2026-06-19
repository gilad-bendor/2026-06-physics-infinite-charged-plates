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

---

## 2. Where We're Heading (Roadmap)

1. **$N = 2$ sinusoidal base case** *(current focus)* — phase lag $\omega d/c$, in-phase
   vs. anti-phase behavior, energy exchange, and how a neighbor's retarded field modifies
   the effective drag on each plate.
2. **General $N$, prescribed motion** — superposition and interference from multiple
   retarded sources; patterns in the force/work as a function of geometry and drive.
3. **Free (self-consistent) dynamics** — give each plate an areal mass density $\mu_i$ and
   let it respond to the fields: $\mu_i\dot{\mathbf{v}}_i = \mathbf{f}_i + \mathbf{f}_i^{\text{ext}}$.
   This is a system of **delay differential equations** (retarded coupling) — look for
   normal modes, resonances, and instabilities.
4. **Numerical simulation** — a direct time-domain solver to validate the analytics
   (the 1-D-in-$x$, retarded current-sheet array is very clean to simulate).
5. **Extensions** — radiation pressure / momentum along $x$; relaxing assumptions.

---

## 3. Open Questions

The deeper parking lot (the immediate next step lives in §1–§2):

- **Standing-wave / cavity-like effects** between plates arising purely from retardation
  interference, despite there being no reflection.
- **Sign and stability of the inter-plate coupling** as a function of separation $d_{ij}$
  and drive frequency — when does a neighbor's retarded field *assist* versus *oppose* a
  plate's motion?
- **Net momentum / radiation pressure along $x$** from the normal magnetic force
  $\mathbf{K}\times\mathbf{B}$.
- **Mechanical inertia and a driving-agent model**; a clean definition of efficiency
  (energy radiated vs. work supplied).
- **Relaxing assumptions:** conducting sheets (induced currents, reflection, multiple
  scattering), finite conductivity, relativistic speeds.

---

## 4. Decisions & Rationale

Choices already made and why — so we don't relitigate them or re-explore dead ends.

- **Prescribed motion (not free dynamics).** We dictate $\mathbf{v}_i(t)$ and measure the
  force required. This isolates the field/force/work questions from self-consistent
  dynamics. Free dynamics is deferred to roadmap step 3.
- **Non-conducting, "painted" charge.** No induced currents ⇒ no reflection or scattering
  ⇒ the total field is an exact superposition of each plate's independently-emitted waves.
  This is precisely what makes the master-relation single sum exact (`EXPERIMENT-DOCUMENT.md`
  §6).
- **Electromagnetic-only accounting.** Mechanical inertia set aside; an optional areal mass
  density $\mu_i$ may be added later (roadmap step 3).
- **Non-relativistic speeds.** A premise; keeps $\sigma_i$ constant.
- **Versioning by timestamped folders**, not an in-document change log — keeps the spec
  clean.
- **Two-document split.** `EXPERIMENT-DOCUMENT.md` holds only settled physics; this
  notebook holds direction and process. No fact lives in both files.

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
