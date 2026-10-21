# Dual simplex method: ready-to-use examples

All of these are built into the tool's **Example** menu. Answers were checked with SciPy, and the lecture example by hand.

| # | Example (menu name) | Model | What it shows | Answer |
|---|---|---|---|---|
| 1 | Lecture example (Wyndor dual) | min 4y₁ + 12y₂ + 18y₃ s.t. y₁ + 3y₃ ≥ 3, 2y₂ + 2y₃ ≥ 5, y ≥ 0 | Iteration 0: row (2) (−5) leaves, ratios y₂: 6, y₃: 9 → y₂ enters. Iteration 1: row (1) (−3), ratios y₁: 4, y₃: 2 → y₃ enters | y = (0, 3/2, 1), min = 36 |
| 2 | Two ≥ constraints and a ≤ (min) | min 3x₁ + 2x₂ s.t. 3x₁ + x₂ ≥ 3, 4x₁ + 3x₂ ≥ 6, x₁ + x₂ ≤ 3 | A mix of rows that need × (−1) and one that does not | x = (3/5, 6/5), min = 21/5 |
| 3 | Equality constraint (split into two ≤) | min 2x₁ + 3x₂ + x₃ s.t. x₁ + x₂ + x₃ = 4, 2x₁ − x₂ + x₃ ≥ 2 | The equation becomes a “≤” pair (1′), (1″) | x = (0, 0, 4), min = 4 |
| 4 | Three iterations (min) | min 4x₁ + 4x₂ + 2x₃ s.t. 2x₁ + 2x₂ ≥ 8, 2x₁ + 2x₃ ≥ 3, 2x₂ + 2x₃ ≥ 7 | Three pivots, fractional values | x = (1, 3, 1/2), min = 17 |
| 5 | Already feasible: origin is optimal | min x₁ + 2x₂ s.t. x₁ + x₂ ≤ 4, x₁ − x₂ ≤ 2 | No negative right-hand side, so iteration 0 is optimal | x = (0, 0), min = 0 |
| 6 | Infeasible (the dual is unbounded) | min x₁ + x₂ s.t. x₁ + x₂ ≥ 5, x₁ + x₂ ≤ 2 | Iteration 1: the pivot row has no negative entry | infeasible |
| 7 | Not suitable: a negative reduced cost | max 3x₁ + 5x₂ s.t. x₁ ≤ 4, 2x₂ ≤ 12, 3x₁ + 2x₂ ≤ 18 | Step 2 finds reduced costs −3, −5 and stops | use the primal simplex |

Suggested order in class: **1** (the lecture example), **2** and **3** (how Step 3 rewrites ≥ and = rows), **4**
(a longer run), then **5**, **6** and **7** (how the method can end or refuse to start).
