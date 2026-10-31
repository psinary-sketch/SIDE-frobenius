# SIDE-frobenius

SIDE-frobenius compiles, over Mathlib, statements in ℚ, ℤ and 2 × 2 integer matrices. r² + r + 1/4 = (r + 1/2)², so its only root is r = −1/2 (indicial_factor, indicial_root_unique); r ↦ −1 − r fixes only −1/2 (indicial_reflect_fixed_iff); g(a, b) = ab − a − b is 1 at (2, 3) and at least 2 at every other pair 2 ≤ a < b (g_two_three, g_two_three_minimal); and S² = −1, (ST)³ = −1 for S = [[0, −1], [1, 0]], T = [[1, 1], [0, 1]] (S_squared, ST_cubed). Its headline statement, at v0.1.0 = 2efe9f2:

    theorem indicial_forces_half (r : ℚ) (h : r ^ 2 + r + 1 / 4 = 0) : -r = 1 / 2

The polynomial enters as a polynomial: its reading as the indicial equation of H = xp near x = 0 is the Frobenius path's, and the Berry–Keating spectral realization is not asserted.

J. York Seale — https://orcid.org/0009-0008-7993-0310

## What it proves

The Frobenius path (Berry-Keating H = xp; FROBENIUS_23_SPECTRAL_REALIZATION; CRITICAL RESOLVE Path Three) reaches sigma = 1/2 through singular-point analysis. This kernel verifies the algebraic core of that identification:

- `indicial_factor` / `indicial_root_unique` — the indicial polynomial r^2 + r + 1/4 = (r + 1/2)^2 has the unique double root r = -1/2.
- `indicial_reflect_fixed_iff` / `indicial_forces_half` — the indicial reflection r ↦ -1-r has its unique fixed point at r = -1/2, mapping (sigma = -r) to sigma = 1/2.
- `g_two_three` / `g_two_three_minimal` — Sylvester Frobenius number g(2,3) = 2*3-2-3 = 1, unique among pairs 2 ≤ a < b (excluding {2,3}, the value is ≥ 2).
- `S_squared` / `ST_cubed` — the modular {2,3} order signature: S^2 = -I, (ST)^3 = -I in SL2(Z) (orders 2 and 3 in PSL2).

## What it does NOT claim

This is an **identification kernel** — the same status as Voice1 (Euler balance) and Voice6 (spectral self-adjointness) in SIDE-kernel. It verifies that the Frobenius / indicial machinery *points at* sigma = 1/2. It does **not** verify the Berry-Keating spectral realization — that the operator spectrum *equals* the Riemann zeros — which is a conjecture, not a theorem, and is not asserted here.

## Federation context

Checkpoint 1.2-B in the alternative-proof-paths census (`PATHS_TO_THE_CRITICAL_LINE`), filed within the Phase 1.5 wave. Independent federated kernel: own toolchain pin, own Mathlib pin, own deposit. Mathlib-dependent (matching SIDE-grh-transfer pin v4.29.1) because the content is rational / nonlinear algebra where ring / linarith / nlinarith / decide give clean proofs.

## Build
lake exe cache get
lake build
lake env lean AxiomCheck.lean   # each theorem: [propext, Classical.choice, Quot.sound]

Toolchain leanprover/lean4:v4.29.1; Mathlib pinned v4.29.1.

## License

MIT.

## AI disclosure

*Computational workflow assisted by various LLM instances. Mathematical content, strategies of argument, and editorial decisions are the author's.*