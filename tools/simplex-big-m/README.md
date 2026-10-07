# Simplex method interactive tool: Big M Method

An interactive, step-by-step worksheet for the **Big M method**: the simplex method (tabular form) for linear programs
whose **origin is not feasible**, because of `≥` or `=` constraints or negative right-hand sides.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/simplex-big-m/**

It continues the [Tabular Form](../simplex-tabular-form) tool. It uses the same tableau, colours, pivoting player and
controls, with four preparation steps and a pre-processing iteration added in front.

---

## What it does

### 1. Enter the problem

- Pick one of the built-in examples (see [EXAMPLES.md](EXAMPLES.md)), or type your own.
- Up to 6 nonnegative variables and 6 constraints; `max` or `min`; each constraint `≤`, `≥` or `=`; right-hand sides can
  be positive, negative or zero.
- Coefficients accept integers, decimals or fractions (`3`, `−1.5`, `2/7`). All arithmetic is exact, and **M is kept as a
  symbol**, so entries look like `−3M − 3` exactly as on the board.
- **Save as my example** keeps your own problems in this browser.

### 2. The worksheet

**Preparation** (one card per step):

1. **Standard form.** The model is shown next to its standard form: a slack for each `≤` row, a surplus for each `≥` row,
   and `min` turned into `max`.
2. **Right-hand sides ≥ 0.** Each row with a negative right-hand side is multiplied by −1 (shown before and after).
3. **Artificial variables.** A table checks every row. After Step 2, a `≤` constraint (right-hand side ≥ 0) needs no
   artificial: its slack starts as basic. Every `≥` or `=` constraint gets an artificial variable `x̄`. In terms of the
   original problem, that means `≥` rows, `=` rows and `≤` rows with a negative right-hand side. A `≥` row with a negative
   right-hand side becomes `≤` in Step 2, so it needs none; one example shows this.
4. **Big M objective.** Maximize *original objective − M x̄ − M x̄ − …*, and row (0) `z − … + M x̄ + … = 0`.

**Iteration 0** is the initial tableau. Artificial columns are marked in the header, and the `M` entries in row (0) are
circled because those columns are not unit columns yet.

**Iteration 0′ (pre-processing)** removes those `M`s with one operation per artificial variable,
`new R₀ = R₀ − M·Rᵢ`. Each operation is animated in place on the tableau: a `× (−M)` chip on row *i*, an arrow into
row (0), and an arithmetic panel showing `(−M) × row (i)`, `+ row (0)` and `= new row (0)`.

**Iterations 1, 2, …** run the ordinary simplex tableau. The pivot column comes from the most negative reduced cost,
comparing `M` parts first, and the student can pick another negative one. The pivot row comes from the ratio-test
column. The next tableau is built row by row with the animated player.

**At the end**
- **Optimal, all artificials 0:** the optimal solution of the original problem, with a check in the original objective.
- **Optimal, an artificial still positive:** the original problem is **infeasible**.
- **Unbounded:** no leaving variable. If an artificial is still positive at that point, the Big M method alone cannot
  tell infeasible from unbounded. The tool says so and settles it with an exact feasibility check (Phase I, minimizing the
  sum of the artificials).

### Controls

- **Next / Back** in the bar at the bottom (also `→` / `←`; `Space` plays or pauses an animation).
- **Run to the end**, **Fractions / Decimals**, **Restart worksheet**, Slow / Normal / Fast animation.

---

## Quality checks (October 2026)

- All 8 built-in examples give the same result as an independent LP solver (SciPy HiGHS).
- 800 random problems (2–4 variables, 2–4 constraints with mixed `≤ / ≥ / =` and negative right-hand sides) give the same
  status (optimal / infeasible / unbounded) and optimal value as SciPy. No mismatches.
- Every example was clicked through step by step with **Next**, then fully undone with **Back**, with no script errors.
- Layout checked at desktop and phone width, in light and dark mode.

## Running it

A **single self-contained `index.html`**: no build step and no dependencies. Open the live link, or download the folder
and double-click `index.html`.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
