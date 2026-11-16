# Sensitivity Analysis interactive tool: Tabular Form

An interactive, step-by-step worksheet for **sensitivity analysis** from the final simplex tableau. Everything comes
from two pieces of the optimal tableau: **y\*** (row (0) under the slack columns) and **S\*** (the constraint rows under
the slack columns). No model is re-solved from scratch.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/sensitivity-analysis/**

It uses the same tableau, colours, row-operation player (▶ Play all, Next, speeds) and controls as the
[Tabular Form](../simplex-tabular-form) and [Dual Simplex](../dual-simplex) tools.

---

## What it does

**Step 0 · solve the problem.** The problem (max or min, all constraints `≤` with nonnegative right-hand sides) is solved
with the simplex method. The optimal tableau is shown with y\* (blue) and S\* (green) shaded, and y\* and S\* are written
out as a vector and a matrix. The simplex iterations are available in a collapsible list.

**New decision variable**
1. Write the dual of the current problem (max ↔ min, one dual variable per constraint, one dual constraint per variable).
2. Add the new variable: one new column in the primal = one new constraint in the dual (highlighted).
3. Plug y\* into the new dual constraint, term by term. If it holds, the current solution stays optimal with
   x_new = 0. If it is violated, the tool continues with Steps 1–3 to re-optimize.

**Question 1 · re-optimize after a change** (edit any entry of c̄, Ā or b̄; changed entries are highlighted)
- **Step 1** computes the four components y\*Ā − c̄, S\*Ā, y\*b̄ and S\*b̄ as matrix products, **one entry at a time**:
  the row on the left and the column on the right are highlighted and the sum is written out
  (for example `0·1 + 3/2·0 + 1·3 − 3 = 0`). Together with y\* and S\* they form the revised final tableau.
- **Step 2** restores the unit vectors of the basic variables with animated row operations (or says “SKIP”).
- **Step 3**: optimal and feasible → done; only a negative reduced cost → **simplex**; only a negative right-hand side →
  **dual simplex**; both → neither method applies (solve from scratch). Each pivot is animated row by row.

**Question 2 · allowable range** of any b_i or c_j
- The parameter becomes (current value) + θ, and Steps 1 and 2 are done with θ (Step 3 is not needed).
- For b_i: every right-hand side ≥ 0. For c_j: every reduced cost ≥ 0. Each condition is solved for θ, combined into a
  range for θ, and translated into a range for the parameter (for example `6 ≤ b₂ ≤ 18`), with the shadow price or the
  new objective value.

Students can type their own problems and questions, and save them as examples in their browser.

## Quality checks (November 2026)

- The lecture examples reproduce the slides: x_new with column (2, 3, 1) stays optimal (2·0 + 3·3/2 + 1·1 = 11/2 ≥ 4),
  `6 ≤ b₂ ≤ 18`, and `0 ≤ c₁ ≤ 7.5`.
- 3,600 random problems (sizes 1×1 to 5×5, max and min, fractions, zeros, degenerate cases) were checked with exact
  arithmetic against an independent solver and SciPy: y\*, S\*, every Step 1 product, the Step 2 tableau, every Step 3
  iteration (simplex keeps feasibility, dual simplex keeps optimality), the final answers (optimal, unbounded,
  infeasible), the new-variable verdicts, and every allowable range (both ends tight). No mismatches.
- Every example was clicked through with **Next**, fully undone with **Back**, and compared with **Run to the end**;
  the player, tie choices, tabs, inputs, decimals and saved examples were tested with no script errors. The layout was
  checked at phone width and in dark mode.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
