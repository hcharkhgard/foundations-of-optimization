# Assignment problem: ready-to-use examples

All of these are built into the tool's **Example** menu. Every answer was checked by brute force and by the LP.

| # | Example (menu name) | Cost table (rows = assignees) | What it shows | Optimal total |
|---|---|---|---|---|
| 1 | Four people, four jobs (lines = n right away) | 9 2 7 8 / 6 4 3 7 / 5 8 1 8 / 7 6 9 4 | 4 lines after the reductions | 13 (Ann→Job 2, Ben→Job 1, Cal→Job 3, Dee→Job 4) |
| 2 | One adjustment step | 9 3 9 10 / 6 4 7 10 / 8 3 12 9 / 4 5 4 11 | one Step 4 | 22 |
| 3 | Two adjustment steps (4 × 4) | 12 2 5 9 / 10 12 6 3 / 8 3 6 1 / 10 9 9 12 | two Step 4s | 19 |
| 4 | Two adjustment steps (5 × 5) | 1 12 9 11 10 / 12 7 4 3 11 / 11 11 2 11 12 / 6 3 9 11 2 / 8 10 7 5 11 | two Step 4s on a larger table | 17 |
| 5 | More tasks than people (dummy row) | 3 × 4 | a dummy row with cost 0; one job is left undone | 24 |
| 6 | More people than tasks (dummy column) | 5 × 3 | two dummy columns; two people get no job | 37 |
| 7 | Not allowed pairs (big M) | M on the diagonal | M never gets picked; M − k = M | 23 |
| 8 | A required assignment (row and column removed) | example 1 with Ann → Job 1 required | the row and column are removed; a 3 × 3 problem is solved | 18 |
| 9 | All tricks: dummy, M and a required pair | 4 × 5 with M entries and Dee → Job 4 required | all three tricks together | 21 |
| 10 | Impossible: forbidden pairs leave no assignment | two columns of M for two rows | reported as infeasible (the LP too) | — |

Suggested order in class: **1**, **2**, **3** (the method), **5** and **6** (dummies), **7** (big M), **8** and **9**
(required pairs), then **10**.
