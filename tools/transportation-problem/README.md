# Transportation problem interactive tool: Transportation Simplex Method

An interactive, step-by-step worksheet for the **transportation problem**: ship goods from sources (supplies) to
destinations (demands) at the smallest total cost. It shows the problem as a **linear program**, writes its **dual**
(the origin of u_i, v_j and the test u_i + v_j − c_ij), and solves it with the **transportation simplex method**.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/transportation-problem/**

---

## What it does

**1 · The data.** Sources (rows) with supplies, destinations (columns) with demands, unit costs (1 to 6 of each; names
can be edited; integers, decimals or fractions). Totals do not have to be equal.
- Type **M** for a route that is **not possible** (big M).
- Add **minimum shipments** (source *i* must ship at least *L* to destination *j*).

**2 · The formulation and its dual**
- The LP: objective, supply and demand constraints (“≤” on the larger side when not balanced), x_ij = 0 for routes that
  are not possible, x_ij ≥ L for minimum shipments, x_ij ≥ 0. Why integrality can be dropped (totally unimodular matrix).
- The dual: max Σ s_i u_i + Σ d_j v_j s.t. u_i + v_j ≤ c_ij for every route, u_i and v_j free, written out for the table.
- **Why u_i + v_j − c_ij is computed**: the reduced cost c_ij − u_i − v_j is the slack of the dual constraint; basic
  cells have reduced cost 0, so u_i + v_j = c_ij (with u₁ = 0 because one constraint is redundant); the solution is
  optimal exactly when the dual values are feasible (u_i + v_j − c_ij ≤ 0); at the optimum Σ s_i u_i + Σ d_j v_j = cost.
- A button solves the LP with the simplex method (exact arithmetic).

**3 · The transportation simplex method** (Next / Back / ▶ Play), drawn as on the slides: costs in corner boxes,
shipments in red, u_i in a right column and v_j in a bottom row.
- **Step 1**: balanced? If not, add a dummy source or destination with cost 0.
- **Step 2 · Northwest rule**, one allocation at a time, with remaining supply/demand and crossed-out rows/columns
  (a tie creates a basic 0 so there are always m + n − 1 basic cells).
- **Step 3 · Dual values**: u₁ = 0, then one value at a time from a basic cell (u_i + v_j = c_ij).
- **Step 4 · Optimality test**: u_i + v_j − c_ij in every non-basic cell, row by row; the most positive enters.
- **Pivot**: the closed loop drawn over the table with +θ/−θ; θ = smallest “−” amount, which leaves; the new solution and
  its total cost.
- **Result**: shipments and minimum total cost; unused supply / unmet demand from the dummy; infeasibility if a route with
  cost M still carries a positive amount.

## Quality checks (November 2026)

- The lecture example reproduces the slides exactly: 1180 → 1120 → 1070 → 1020, with the same entering cells, θ values
  and final shipments. Hillier’s P & T Company example gives 152,535.
- 5,000 random problems (balanced and not, M routes, ties, zero supplies/demands, single rows/columns, up to 6 × 6,
  negative costs, decimals, fractions, several minimum shipments) were checked against SciPy and the exact LP: same
  optimum every time, every infeasible problem detected.
- Every iteration was checked independently: m + n − 1 basic cells, nonnegative flows meeting every supply and demand,
  u₁ = 0 and u_i + v_j = c_ij on basic cells (each dual value derived from a cell whose partner was already known),
  every u_i + v_j − c_ij, the entering cell, the loop (alternating rows/columns through basic cells), θ and the leaving
  cell, a non-increasing cost, every northwest allocation and its crossing-out explanation, and strong duality at the
  optimum.
- Every example was clicked through with Next and Back and played with ▶ Play; inputs, names, minimum shipments,
  decimals and saved examples were tested with no script errors. The layout was checked at phone width and in dark mode.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
