# Transportation problem: ready-to-use examples

All of these are built into the tool's **Example** menu. Answers were checked with SciPy and the exact LP.

| # | Example (menu name) | What it shows | Northwest cost → … → optimal |
|---|---|---|---|
| 1 | Lecture example: 3 plants, 4 cities | the slides, step for step | 1180 → 1120 → 1070 → **1020** |
| 2 | P & T Company (canneries → warehouses) | Hillier’s textbook example | 165,595 → 152,835 → **152,535** |
| 3 | Supply > demand (dummy destination) | dummy destination with cost 0 = unused supply | 430 → 370 → **340** |
| 4 | Demand > supply (dummy source) | dummy source with cost 0 = unmet demand | 375 → 340 → **335** |
| 5 | Routes that are not possible (big M) | M in the corner boxes; values like −M + 12 in the test | 1180 → 1120 → **1070** |
| 6 | A minimum shipment on a route | Plant 3 → City 1 at least 10: shipped first, added back | **1070** in all |
| 7 | Degenerate start (a basic cell with 0) | a northwest tie creates a basic 0 | **195** (already optimal) |
| 8 | Impossible: the routes left cannot meet demand | a positive amount stays on an M route | infeasible |

Lecture example data: costs 8 6 10 9 / 9 12 13 7 / 14 9 16 5, supplies 35, 50, 40, demands 45, 20, 30, 30.

Suggested order in class: **1** (the method and the dual values), **2**, **3** and **4** (balancing), **5** (big M),
**6** (minimum shipments), **7** (degeneracy), **8**.
