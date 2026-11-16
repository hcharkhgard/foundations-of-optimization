# Assignment problem interactive tool: Hungarian Method

An interactive, step-by-step worksheet for the **assignment problem**: assign every assignee to exactly one task (and
every task to exactly one assignee) at the smallest total cost. It shows the problem as a **linear program** and solves
it with the **Hungarian method**.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/assignment-problem/**

---

## What it does

**1 · The cost table.** Rows are assignees, columns are tasks (1 to 8 of each; the table does not have to be square).
Names can be edited. Entries accept integers, decimals and fractions.
- Type **M** for a pair that is **not allowed** (big M).
- Add **required assignments** (assignee *i* must do task *j*).

**2 · The formulation.** The decision variables x_ij, the objective, one “= 1” constraint per row and per column,
x_ij = 0 for not-allowed pairs and x_ij = 1 for required pairs. The integrality condition x_ij ∈ {0, 1} is replaced by
x_ij ≥ 0, with the reason (every variable appears in exactly two constraints with coefficient 1: the matrix is totally
unimodular, so every corner point is integer). A button solves the LP with the simplex method (exact arithmetic), and
every x_ij comes out 0 or 1.

**3 · The Hungarian method** (Next / Back / ▶ Play)
- **Preparation**: required pairs remove their row and column (the cost is added back at the end); a non-square table
  gets dummy rows or columns with cost 0; M minus anything stays M.
- **Step 1 · Row reduction**: row minima in a side column (circled), then subtracted.
- **Step 2 · Column reduction**: column minima in a bottom row, then subtracted.
- **Step 3 · Cover the zeros** with the minimum number of lines, drawn one at a time, and compared with n.
- **Step 4 · Adjust** (fewer than n lines): uncovered entries in yellow, k = the smallest of them; subtract k from the
  uncovered entries, add k where two lines cross; back to Step 3.
- **Step 5 · Make the assignment**: box a zero in a row or column with only one available zero, cross out the other zeros
  in its row and column, repeat.
- **Result**: the assignment and the total cost; dummy pairs are reported as “no task” / “nobody does this task”.
  Tables where forbidden pairs leave no assignment are reported as infeasible.

## Quality checks (November 2026)

- 3,500 random tables (1×1 to 8×8, square and not, negative costs, decimals, fractions, many M entries, all-equal
  tables, several required pairs): every total equals the optimum from an independent solver, every infeasible table is
  detected, and the LP relaxation is always integer with the same value.
- Every step was checked independently: reductions, the lines (they cover every zero and their number equals the maximum
  number of independent zeros), k and the adjustment rule, and every assignment step (its stated reason and the
  crossed-out zeros).
- Every example was clicked through with Next and Back and played with ▶ Play; inputs, names, required pairs, decimals
  and saved examples were tested with no script errors. The layout was checked at phone width and in dark mode.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
