# Simplex method interactive tool: Two-Phase Method

An interactive, step-by-step worksheet for the **two-phase simplex method** (tabular form) for linear programs whose
**origin is not feasible**, because of `≥` or `=` constraints or negative right-hand sides.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/simplex-two-phase/**

It is the companion of the [Big M Method](../simplex-big-m) tool. The preparation is the same, the examples are the same,
and the tableau, colours, pivot player and controls are the same as in [Tabular Form](../simplex-tabular-form). There is
no big penalty `M`, so every number in the tableau stays an ordinary number.

---

## What it does

**Preparation** (one card per step)
1. **Standard form**: a slack for each `≤` row, a surplus for each `≥` row, and `min` turned into `max`.
2. **Right-hand sides ≥ 0**: rows with a negative right-hand side are multiplied by −1 (shown before and after).
3. **Artificial variables**: a row-by-row check. After Step 2, a `≤` constraint (right-hand side ≥ 0) needs no artificial,
   because its slack starts as basic. Every `≥` or `=` constraint gets an artificial `x̄`.
   If no row needs one, Phase I is skipped.
4. **Phase I objective**: maximize `z = −(sum of the artificials)`, with row (0) `z + x̄ + x̄ + … = 0`.

**Phase I**
- **Iteration 0**: the initial tableau. The 1s in row (0) under the artificial columns are circled.
- **Iteration 0′ (pre-processing)**: `new R₀ = R₀ − Rᵢ` for each artificial, animated in place with an arithmetic panel.
- **Iterations 1, 2, …**: the usual pivot column, ratio test and animated row operations.
- **End of Phase I**: optimal `z < 0` means the original problem is **infeasible** and the tool stops. Optimal `z = 0`
  means feasible. An artificial still basic at value 0 is pivoted out on a nonzero entry of its row. If its row has no
  such entry, the constraint is redundant and the row is deleted. The tool explains whichever happens.

**Phase II**
- **Iteration 0**: the artificial columns are deleted, the constraint rows and basis are kept, and row (0) becomes
  `z − (original objective) = 0`. Basic columns with a nonzero entry in row (0) are circled.
- **Iteration 0′ (pre-processing)**: `new R₀ = R₀ − c·Rᵢ` for each such basic variable. This step is skipped if nothing
  needs fixing.
- **Iterations 1, 2, …**: until optimal (solution, value and a check in the original objective) or unbounded.

Controls: **Next / Back** (also `→` / `←`), **Run to the end**, **Fractions / Decimals**, **Restart**, and
Slow / Normal / Fast animation with `Space` to play or pause. **Save as my example** keeps your own problems in the
browser.

---

## Quality checks (October 2026)

- All 9 built-in examples give the same result as an independent LP solver (SciPy HiGHS). The answers are in
  [EXAMPLES.md](EXAMPLES.md).
- 1,000 random problems agree with SciPy on status (optimal / infeasible / unbounded) and optimal value. 400 of them
  include a redundant constraint, so the "artificial still basic at 0" step ran 54 times: 50 rows deleted and 4 pivots.
  In the one disagreement, SciPy's presolve wrongly reported "infeasible". The tool's answer (unbounded) was confirmed
  with SciPy's presolve turned off and by hand.
- Every example was clicked through with **Next** and fully undone with **Back**, with no script errors.
- Layout checked at desktop and phone width (no sideways scrolling), in light and dark mode.

## Running it

A **single self-contained `index.html`**. Open the live link, or double-click `index.html` in this folder; it works offline.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
