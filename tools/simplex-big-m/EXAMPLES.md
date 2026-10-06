# Big M Method: ready-to-use examples

All of these are built into the tool. Pick them from the **Example** menu, then press **Next** (or **Run to the end**).
The answers were checked against an independent LP solver.

| # | Example (menu name) | Model | What it shows | Answer |
|---|---|---|---|---|
| 1 | Equality constraint (lecture style) | max 3x₁ + 5x₂ s.t. x₁ ≤ 4, 2x₂ ≤ 12, 3x₁ + 2x₂ = 18 | One artificial (on the `=` row). Pre-processing gives row (0): −3M − 3, −2M − 5, RHS −18M | x = (2, 6), z = 36 |
| 2 | Minimization with ≥ and = rows | min 4x₁ + x₂ s.t. 3x₁ + x₂ = 3, 4x₁ + 3x₂ ≥ 6, x₁ + 2x₂ ≤ 4 | min → max, two artificials, two pre-processing operations | x = (2/5, 9/5), min = 17/5 |
| 3 | Radiation therapy (decimals, min) | min 0.4x₁ + 0.5x₂ s.t. 0.3x₁ + 0.1x₂ ≤ 2.7, 0.5x₁ + 0.5x₂ = 6, 0.6x₁ + 0.4x₂ ≥ 6 | Decimal data handled exactly; try the Decimals toggle | x = (7.5, 4.5), min = 5.25 |
| 4 | Negative right-hand side | max 2x₁ + x₂ s.t. −x₁ − x₂ ≤ −3, x₁ ≤ 4, x₂ ≤ 5 | Step 2 multiplies row (1) by −1; its slack then has coefficient −1, so it needs an artificial | x = (4, 5), z = 13 |
| 5 | Three variables, ≥ rows (min) | min 2x₁ + 3x₂ + x₃ s.t. x₁ + x₂ + x₃ ≥ 4, 2x₁ + x₂ ≥ 5, x₂ + 2x₃ ≤ 6 | Larger tableau, two artificials | x = (5/2, 0, 3/2), min = 13/2 |
| 6 | “≥” with negative RHS: no artificial needed | max 2x₁ + x₂ s.t. x₁ + x₂ ≤ 4, x₁ − x₂ ≥ −2, x₁ ≤ 3 | After × (−1) the surplus has coefficient +1, so no artificial is needed and the ordinary simplex runs | x = (3, 1), z = 7 |
| 7 | Infeasible problem | max 3x₁ + 2x₂ s.t. 2x₁ + x₂ ≤ 2, 3x₁ + 4x₂ ≥ 12 | Optimal Big M tableau with an artificial still positive | infeasible |
| 8 | Unbounded problem | max 2x₁ + x₂ s.t. x₁ + x₂ ≥ 2, x₁ − x₂ ≤ 1 | Ratio test finds no leaving variable | unbounded |

Suggested order in class: **1** (the core idea), **2** (two artificials and a min problem), **4** and **6** (what the
right-hand-side rule really does), then **7** and **8** (how the method ends when there is no optimum).
