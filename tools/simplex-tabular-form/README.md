# Simplex method interactive tool: Tabular Form

An interactive, step-by-step worksheet for the **simplex method in tabular form** (the simplex tableau) when the
**origin is feasible** (every constraint is `≤` and every right-hand side is nonnegative).

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/simplex-tabular-form/**

The companion of the [Algebraic Form](../simplex-algebraic-form) tool: same examples, same steps, same colours, but every
system of equations is shown as a tableau.

---

## What it does

### 1. Enter the problem

- Pick one of the built-in examples (lecture example, three variables, four constraints, minimization, fractional data,
  degenerate tie, multiple optima, unbounded, and two where the origin is **not** feasible), or type your own.
- Up to 6 variables and 6 constraints; `max` or `min`; each constraint `≤`, `≥` or `=`.
- Coefficients accept integers, decimals or fractions (`3`, `−1.5`, `2/7`). All arithmetic is exact.
- **Save as my example** keeps your own problems in this browser.

### 2. The worksheet: one compact tableau per iteration

**Preparation** (one card): original model next to the standard form (a slack for each `≤` row, `min` turned into `max`),
then the origin check (all constraints `≤`, all right-hand sides ≥ 0) and row (0) `z − c₁x₁ − … − cₙxₙ = 0`.
If the origin is not feasible, the tool stops and explains why.

**Iteration 0** is the initial tableau: columns **Basic**, **Eq.**, **z** (1 in row (0), 0 elsewhere), one column per
variable, **RHS**. The slacks are basic. Under the table, one line reads off the solution (basic = RHS of its row,
non-basic = 0, `z` = RHS of row (0)).

Each iteration then works **on the same table**:

1. **Pivot column.** The negative entries of row (0) are circled; the most negative is chosen by default, but the
   student can click any other negative one. Its column turns blue. If none is negative, the tableau is optimal and the
   optimal solution is shown (with a check in the original objective and a note about multiple optima).
2. **Pivot row.** A ratio-test column appears on the right of the same table: `RHS ÷ entry` for strictly positive entries,
   **impossible** when the entry is 0 or negative. The smallest ratio is tagged `min`; its row (amber) is the pivot row and
   the pivot element is circled. Ties are the student's choice. If every row is impossible, the problem is unbounded.
3. **Next tableau, built right below.** The new table starts empty, with the entering variable already in the Basic
   column and its columns lined up under the table above. A player (▶ Play all / ❚❚, Next row, Previous, Start,
   Slow / Normal / Fast) fills it one row at a time. Every row operation is **drawn on the previous tableau**, which is
   never changed: the original pivot row gets a multiplier chip and an arrow with `+` runs into the row being changed
   (whose pivot-column entry is circled), e.g. `× 5/2` from row (2) into row (0); for the pivot row itself a `÷ 2` loop.
   The resulting numbers are then written into that row of the new tableau. The caption gives the rule and the reason,
   e.g. *new row (0) = old row (0) + 5/2 × old pivot row (2), because −5 + (5/2) × 2 = 0*. Rows whose pivot-column entry
   is already 0 are copied unchanged.

Finished tables keep their pivot column, pivot row and ratio column, plus a one-line summary of the row operations that
built them, so the whole run reads as a short stack of tableaus.

### Controls

- **Next / Back** in a bar fixed to the bottom of the screen (also `→` and `←`; `Space` plays/pauses while a table is being built).
- **Run to the end** plays every remaining step with the default choices.
- **Fractions / Decimals** display toggle; **Restart worksheet**.

---

## Running it

A **single self-contained `index.html`** — no build step, no dependencies. Open the live link, or download the folder and
double-click `index.html`. The only external request is Google Fonts; offline, the page falls back to system fonts.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved — see [LICENSE](../../LICENSE).
