# Writing the Dual: ready-to-use examples

All of these are built into the tool's **Example** menu. Optimal values were checked with an exact solver and SciPy.

| # | Example (menu name) | Primal | Dual (what students should get) | Optimal value |
|---|---|---|---|---|
| 1 | Product mix (max, all ≤, x ≥ 0) | max 3x₁ + 5x₂ s.t. x₁ ≤ 4, 2x₂ ≤ 12, 3x₁ + 2x₂ ≤ 18, x ≥ 0 | min 4y₁ + 12y₂ + 18y₃ s.t. y₁ + 3y₃ ≥ 3, 2y₂ + 2y₃ ≥ 5, y ≥ 0 | 36 |
| 2 | Diet problem (min, all ≥, x ≥ 0) | min 2x₁ + 3x₂ s.t. x₁ + x₂ ≥ 6, 2x₁ + x₂ ≥ 8, x₁ + 3x₂ ≥ 9, x ≥ 0 | max 6y₁ + 8y₂ + 9y₃ s.t. y₁ + 2y₂ + y₃ ≤ 2, y₁ + y₂ + 3y₃ ≤ 3, y ≥ 0 | 27/2 |
| 3 | Mixed max: ≤, ≥, = and all three signs | max 2x₁ + 3x₂ + x₃ s.t. x₁ + x₂ + x₃ ≤ 10, x₁ − x₃ ≥ −2, x₂ + x₃ = 3; x₁ ≥ 0, x₂ ≤ 0, x₃ unrestricted | min 10y₁ − 2y₂ + 3y₃ s.t. y₁ + y₂ ≥ 2, y₁ + y₃ ≤ 3, y₁ − y₂ + y₃ = 1; y₁ ≥ 0, y₂ ≤ 0, y₃ unrestricted | 17 |
| 4 | Mixed min: ≥, ≤, = and all three signs | min 4x₁ + 2x₂ − x₃ s.t. x₁ + x₂ + x₃ ≥ 3, x₁ − x₂ ≤ 2, 2x₂ + x₃ = 5; x₁ ≥ 0, x₂ unrestricted, x₃ ≤ 0 | max 3y₁ + 2y₂ + 5y₃ s.t. y₁ + y₂ ≤ 4, y₁ − y₂ + 2y₃ = 2, y₁ + y₃ ≥ −1; y₁ ≥ 0, y₂ ≤ 0, y₃ unrestricted | 7 |
| 5 | Equality constraints, unrestricted variables | max x₁ + 2x₂ − x₃ s.t. x₁ + x₂ + x₃ = 4, x₁ − x₂ + 2x₃ = 1; x₁ unrestricted, x₂, x₃ ≥ 0 | min 4y₁ + y₂ s.t. y₁ + y₂ = 1, y₁ − y₂ ≥ 2, y₁ + 2y₂ ≥ −1; y unrestricted | 11/2 |
| 6 | All right-hand sides 0 (unbounded, so the dual is infeasible) | max x₁ + x₂ s.t. x₁ − 2x₂ ≤ 0, −2x₁ + x₂ ≤ 0, x ≥ 0 | min 0 s.t. y₁ − 2y₂ ≥ 1, −2y₁ + y₂ ≥ 1, y ≥ 0 | primal unbounded, dual infeasible |
| 7 | All objective coefficients 0 (feasibility) | min 0 s.t. x₁ + x₂ ≥ 2, x₁ − x₂ ≤ 1, x ≥ 0 | max 2y₁ + y₂ s.t. y₁ + y₂ ≤ 0, y₁ − y₂ ≤ 0; y₁ ≥ 0, y₂ ≤ 0 | 0 |

Suggested activity: take example 3, split the equation (3), multiply (2) by −1, and replace x₂ and x₃ by nonnegative
variables. Then compare the two duals in section 5 and discuss why they are the same problem.
