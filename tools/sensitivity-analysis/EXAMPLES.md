# Sensitivity analysis: ready-to-use examples

All of these are built into the tool's **Example** menu (each one sets the problem and the question). Answers were
checked with exact arithmetic and SciPy, and the lecture examples against the slides.

Problem W (lecture): max 3x₁ + 5x₂ s.t. x₁ ≤ 4, 2x₂ ≤ 12, 3x₁ + 2x₂ ≤ 18 — optimal x = (2, 6), z = 36, y\* = (0, 3/2, 1).
Problem C: max 5x₁ + 4x₂ + 3x₃ s.t. 2x₁ + 3x₂ + x₃ ≤ 5, 4x₁ + x₂ + 2x₃ ≤ 11, 3x₁ + 4x₂ + 2x₃ ≤ 8 — optimal x = (2, 0, 1), z = 13.

| # | Example (menu name) | Problem | Question | Answer |
|---|---|---|---|---|
| 1 | New variable: dual constraint satisfied (lecture) | W | x_new with c = 4, column (2, 3, 1) | 2·0 + 3·3/2 + 1·1 = 11/2 ≥ 4: stays optimal, x_new = 0, z = 36 |
| 2 | New variable: dual constraint violated → re-optimize | W | x_new with c = 4, column (1, 1, 1) | 5/2 < 4; one simplex pivot: x = (2, 5), x_new = 2, z = 39 |
| 3 | Question 1: b₂ changes 12 → 24 (dual simplex) | W | b̄ = (4, 24, 18) | S\*b̄ = (6, 12, −2); one dual simplex pivot: x = (0, 9), z = 45 |
| 4 | Question 1: c₂ changes 5 → 1 (simplex) | W | c̄ = (3, 1) | Step 2 makes row (0) negative; one simplex pivot: x = (4, 3), z = 15 |
| 5 | Question 1: x₁’s column changes (Step 2 needed) | W | c₁ = 4, a₃₁ = 2 | Step 2 needs three row operations; then optimal: x = (3, 6), z = 42 |
| 6 | Question 2: allowable range of b₂ (lecture) | W | b₂ = 12 + θ | −6 ≤ θ ≤ 6, so 6 ≤ b₂ ≤ 18 |
| 7 | Question 2: allowable range of c₁ (lecture) | W | c₁ = 3 + θ | −3 ≤ θ ≤ 9/2, so 0 ≤ c₁ ≤ 7.5 |
| 8 | Question 2: range of c₂ (a non-basic variable) | C | c₂ = 4 + θ | θ ≤ 3, so c₂ ≤ 7 (Step 2 skipped) |
| 9 | Question 2: range of b₁ (three variables) | C | b₁ = 5 + θ | 4 ≤ b₁ ≤ 16/3 |
| 10 | Question 1: b₃ changes 8 → 3 (three variables) | C | b̄ = (5, 11, 3) | dual simplex: x = (1, 0, 0), z = 5 |

Suggested order in class: **1** and **2** (the new variable), **6** and **7** (Question 2, as on the slides),
**5** (Step 2 in action), then **3** and **4** (Step 3 with the dual simplex and the simplex method).
