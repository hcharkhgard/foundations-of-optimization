# Duality interactive tool: Writing the Dual

An interactive, step-by-step worksheet for **writing the dual of a linear program**. The primal can be a max or a min
problem, with `≤`, `≥` and `=` constraints and variables that are nonnegative, nonpositive or unrestricted in sign.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/duality/**

---

## What it does

1. **Duality cheat sheet**: a two-column table, maximization problem ↔ minimization problem. It covers the objective
   sense, constraint type ↔ dual variable sign, variable sign ↔ dual constraint direction, and how the data moves
   (right-hand sides ↔ objective coefficients, `A` ↔ `Aᵀ`). Read it left → right for a max primal and right → left for a
   min primal.
2. **The primal problem**: up to 6 variables and 6 constraints, each with its own relation, and each variable with its own
   sign. Any coefficient may be 0, including all objective coefficients or all right-hand sides.
3. **Rewrite the primal (optional)**: apply valid operations as often as you like, with undo:
   objective × (−1) (max ↔ min), constraint × (−1), split an equation into `≤` and `≥`, add a slack or surplus,
   replace `x ≤ 0` by `−x′`, and replace an unrestricted `x` by `x⁺ − x⁻`.
4. **Write the dual, step by step** (tabs for the original and the rewritten primal). The primal is shown with an
   empty dual area below it, which fills in one piece at a time with **▶ Play** or **Next / Previous** (also `→` / `←`):
   max ↔ min; a dual variable tag `yᵢ` beside each constraint; the right-hand sides circled and multiplied by `y₁, y₂, …`
   for the dual objective; for each primal variable, its column circled and its objective coefficient boxed, written out as
   `a₁ⱼ·y₁ + a₂ⱼ·y₂ + …` with right-hand side `cⱼ`; then each variable's sign circled to fix that constraint's direction,
   and each constraint's relation circled to fix the sign of its `y`. A one-line rule from the cheat sheet goes with every
   step.
5. **Compare and check**: both duals side by side, the optimal values from an exact solver (strong duality), and a note
   for each operation explaining why the two duals are equivalent.

## Quality checks (October 2026)

- The built-in exact solver matches SciPy on 500 random problems with mixed constraint types and variable signs.
- Strong duality holds on all 500: an optimal primal has an optimal dual with the same value, and an unbounded primal
  has an infeasible dual. The dual of the dual is the original primal in every case.
- 1,500 random rewrite sequences all give a dual with the same optimal value.
- Every example, operation and step was clicked through with no errors. The layout was checked at phone width and in
  dark mode.

## Running it

A **single self-contained `index.html`**. Open the live link, or double-click `index.html` in this folder.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
