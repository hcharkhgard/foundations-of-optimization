# Two-Phase Method: ready-to-use examples

All of these are built into the tool. Pick them from the **Example** menu, then press **Next** (or **Run to the end**).
The answers were checked against an independent LP solver. Examples 1–5 and the last two are the same problems as in the
Big M tool, so students can compare the two methods side by side.

| # | Example (menu name) | Model | What it shows | Answer |
|---|---|---|---|---|
| 1 | Equality constraint (lecture style) | max 3x₁ + 5x₂ s.t. x₁ ≤ 4, 2x₂ ≤ 12, 3x₁ + 2x₂ = 18 | One artificial. Phase I row (0) after 0′: −3, −2, RHS −18. Phase II needs a 0′ step | x = (2, 6), z = 36 |
| 2 | Minimization with ≥ and = rows | min 4x₁ + x₂ s.t. 3x₁ + x₂ = 3, 4x₁ + 3x₂ ≥ 6, x₁ + 2x₂ ≤ 4 | min → max, two artificials | x = (2/5, 9/5), min = 17/5 |
| 3 | Radiation therapy (decimals, min) | min 0.4x₁ + 0.5x₂ s.t. 0.3x₁ + 0.1x₂ ≤ 2.7, 0.5x₁ + 0.5x₂ = 6, 0.6x₁ + 0.4x₂ ≥ 6 | Decimal data handled exactly | x = (7.5, 4.5), min = 5.25 |
| 4 | Negative right-hand side | max 2x₁ + x₂ s.t. −x₁ − x₂ ≤ −3, x₁ ≤ 4, x₂ ≤ 5 | Multiply by −1 first; the row becomes “≥”, so it needs an artificial | x = (4, 5), z = 13 |
| 5 | Three variables, ≥ rows (min) | min 2x₁ + 3x₂ + x₃ s.t. x₁ + x₂ + x₃ ≥ 4, 2x₁ + x₂ ≥ 5, x₂ + 2x₃ ≤ 6 | Larger tableau, two artificials | x = (5/2, 0, 3/2), min = 13/2 |
| 6 | “≥” with negative RHS: no Phase I needed | max 2x₁ + x₂ s.t. x₁ + x₂ ≤ 4, x₁ − x₂ ≥ −2, x₁ ≤ 3 | After × (−1) every row is “≤” with right-hand side ≥ 0: no artificial, so the tool goes straight to Phase II | x = (3, 1), z = 7 |
| 7 | Redundant equation (row deleted) | max x₁ + 2x₂ s.t. x₁ + x₂ = 4, 2x₁ + 2x₂ = 8, x₁ ≤ 3 | Phase I ends with an artificial basic at 0 in an all-zero row: the redundant row is deleted | x = (0, 4), z = 8 |
| 8 | Infeasible problem | max 3x₁ + 2x₂ s.t. 2x₁ + x₂ ≤ 2, 3x₁ + 4x₂ ≥ 12 | Phase I optimum z < 0, so Phase II never starts | infeasible |
| 9 | Unbounded problem | max 2x₁ + x₂ s.t. x₁ + x₂ ≥ 2, x₁ − x₂ ≤ 1 | Phase I succeeds, then Phase II finds no leaving variable | unbounded |

Suggested order in class: **1** (both phases end to end), **2** (two artificials and a min problem), **8** and **9** (how
each phase can stop), **7** (the redundant-row case), and **6** (when Phase I is not needed at all).
