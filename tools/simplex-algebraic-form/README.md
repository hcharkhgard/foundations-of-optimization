# Simplex method interactive tool: Algebraic Form

An interactive, step-by-step worksheet for the **simplex method in algebraic form** when the **origin is feasible**
(every constraint is `≤` and every right-hand side is nonnegative).

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/simplex-algebraic-form/**

Built to mirror the lecture slides move for move, so students can apply the same steps to any legitimate LP of this kind.

---

## What it does

### 1. Enter the problem

- Pick one of the built-in examples (the lecture example, three-variable, four-constraint, minimization, fractional data,
  degenerate tie, multiple optima, unbounded, and two where the origin is **not** feasible), or type your own.
- Up to 6 variables and 6 constraints; `max` or `min`; each constraint `≤`, `≥` or `=`.
- Coefficients accept integers, decimals or fractions (`3`, `−1.5`, `2/7`). All arithmetic is exact.
- **Save as my example** keeps your own problems in this browser.

### 2. Preparing to run the simplex method

| Step | What the tool shows |
|---|---|
| **1. Standardize** | Original model next to the standard form, with a slack for each `≤` row (numbered `x₍ₙ₊₁₎, …`) and a `min` turned into `max`. |
| **2. Is the origin feasible?** | Two checks on the original constraints: all `≤`, all right-hand sides ≥ 0. If either fails, the tool stops and explains why. |
| **3. Start the simplex** | Row (0): `z − c₁x₁ − … − cₙxₙ = 0`. Goal: maximize `z`. |

### 3. Each iteration (Iteration 0, 1, 2, …)

**Step 1 — Initialization and Gaussian elimination**
1. *Which variables are basic?* The basic / non-basic table **without values**, with the reason (slacks at the start;
   later, the entering variable replaces the leaving one).
2. *Gaussian elimination*, as an animated player. Each elementary row operation plays in three beats:
   **Multiply** (the row to be multiplied is highlighted with its multiplier chip, e.g. `× 5`, and the row to be changed
   is highlighted in yellow with the coefficient that must become 0 circled), **Add** (an arrow with a `+` runs from the
   multiplied row into the target row, and the sum is worked out line by line with the reason for the multiplier), and
   **Replace row** (the target row takes the new values). Controls: ▶ Play all / ❚❚ Pause, Next operation, Previous,
   Start, and Slow / Normal / Fast speed. Click any operation in the list to jump to the system after it.
3. *Read off the basic feasible solution*: non-basic = 0, each basic variable = its right-hand side, `z` = RHS of row (0).

**Step 2 — Is there any non-basic variable with negative reduced cost?**
Reduced costs are read from row (0). If none is negative, the solution is optimal (with a check in the original objective
and a note when multiple optima are possible). Otherwise the student picks the entering variable: the most negative is
pre-selected, but any negative one can be chosen.

**Step 3 — Create the next basic feasible solution**
Other non-basic variables stay at 0; the reduced system is shown and each row gives
*“if x₄ = 0 then x₂ = 6”* or *“impossible”*. The minimum ratio test picks the leaving variable (ties are the student's
choice), and the next basic / non-basic table is shown with values and the new `z`. Unboundedness is detected here.

### Controls

- **Next / Back** in a bar fixed to the bottom of the screen (also the `→` and `←` keys).
- **Run to the end** plays every remaining step with the default choices — handy at the front of the room.
- **Fractions / Decimals** display toggle; **Restart worksheet**.
- Colour key follows the slides: row (0) in red, basic variables in green; entering variable blue, leaving variable amber.

---

## Running it

A **single self-contained `index.html`** — no build step, no dependencies. Open the live link, or download the folder and
double-click `index.html`. The only external request is Google Fonts; offline, the page falls back to system fonts.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Charkhgard. All rights reserved — see [LICENSE](../../LICENSE).
