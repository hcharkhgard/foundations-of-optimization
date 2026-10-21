# Dual simplex method interactive tool

An interactive, step-by-step worksheet for the **dual simplex method** on a simplex tableau. It is meant for problems
where the **optimality condition already holds** (no negative reduced cost in the maximization form) but the starting
basic solution is **not feasible** (some right-hand sides are negative).

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/dual-simplex/**

It uses the same tableau, colours, row-operation player (▶ Play all, Next row, speeds) and controls as the
[Tabular Form](../simplex-tabular-form) tool.

---

## What it does

**Preparation** (one card per step)
1. **Maximization form**: min → max by multiplying the objective by −1.
2. **Any negative reduced cost?** Row (0) is `z − c₁x₁ − … = 0`. If a reduced cost is negative, the tool stops: the
   dual simplex method does not apply, and it links to the primal simplex tools. Otherwise the problem is suitable.
3. **Every constraint as `≤`**: a `≥` row is multiplied by −1. An `=` row is written as a `≤` and a `≥`, and the `≥` is
   multiplied by −1. Changed rows are highlighted.
4. **Standard form**: one slack per row. The slacks are the starting basis, which is optimal (Step 2) but may be infeasible.

**Each iteration**
- **Feasibility test → pivot row**: the negative right-hand sides are circled. The most negative one gives the pivot
  row, and its basic variable leaves. Ties are the student's choice. If none is negative, the tableau is feasible and
  optimal.
- **Ratio test → pivot column**: a ratio row under the tableau shows `|reduced cost ÷ pivot-row entry|` for every
  non-basic column with a negative entry in the pivot row. The smallest ratio (tagged `min`) gives the entering variable.
  If the pivot row has no negative entry, the problem is **infeasible** (its dual is unbounded).
- **Next tableau**: built right below, one row operation at a time, with the operation drawn on the previous tableau.

The primal problem can never be unbounded here: a starting tableau that satisfies the optimality condition bounds the
objective. The method ends either optimal or infeasible.

**Variable letter**: choose `x` or `y` (the lecture example uses `y₁, y₂, y₃`).

## Quality checks (October 2026)

- All 7 built-in examples give the same result as SciPy. The lecture example's tableaus were also checked by hand.
- 600 random problems (min and max; `≤`, `≥`, `=`; right-hand sides of any sign) agree with SciPy. Problems with a
  negative reduced cost are correctly reported as not suitable.
- In every one of the 1,090 tableaus produced: row (0) never has a negative entry, `z` never increases, every pivot
  element is negative, and every basic column is a unit column.
- Every example was clicked through with **Next** and fully undone with **Back**, and played with the row-operation
  player, with no script errors. The layout was checked at phone width and in dark mode.

## Terms of use

Developed by Dr. Hadi Gard (Charkhgard) for teaching the Foundations of Optimization course only. © 2026 Hadi Gard (Charkhgard). All rights reserved. See [LICENSE](../../LICENSE).
