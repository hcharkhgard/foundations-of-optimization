# General Form → Standard Form

An interactive teaching worksheet for the **general-to-standard-form reduction** in linear programming.

**▶ Live tool: https://hcharkhgard.github.io/foundations-of-optimization/tools/standard-form-worksheet/**

Built for classroom use: students enter a linear program, then convert it to standard form
one deliberate move at a time — choosing *which rule* to apply to *which* constraint,
variable, or objective, and seeing the bookkeeping that comes with each move.

---

## What it does

### 1. Enter the problem

A grid editor for any linear program:

- `min` or `max`, objective coefficients, and a constant term `c₀`
- one row per constraint, each with its own `≤ / = / ≥` relation and right-hand side
- a sign restriction per variable: `xⱼ ≥ 0`, `xⱼ ≤ 0`, or unrestricted in sign
- up to 8 variables and 8 constraints

Coefficients accept integers, decimals, or fractions (`3`, `−1.5`, `2/7`). All arithmetic is
carried out in **exact rationals**, so fractional data never drifts into rounding error.

Three quick loads are provided: *mixed signs*, *already a max*, and *clear*.

### 2. Transform it, one move at a time

The program is displayed as an aligned tableau, and every part of it is a click target:

| You click | You are offered |
|---|---|
| a **constraint** (row label, relation, RHS, or any term) | multiply the row by −1 · add slack `sᵢ` |
| a **variable** (its name in the header, or its sign cell) | substitute `xⱼ = −x′ⱼ` · split into `x′ⱼ − x″ⱼ` |
| the **objective** (its label cell) | convert min → max · drop the constant |

Moves that are not legal for the thing you picked are **disabled with the reason spelled out** —
for example, the slack button on a `≥` row says *"a slack only goes on a ≤ row; multiply this row
by −1 first."* Hovering or tab-focusing any action **previews the result** before you commit to it.

Small dots on the tableau mark exactly what still breaks standard form.

### 3. Keep track

A side rail carries, live:

- **Still to fix** — a checklist of every remaining violation; click one to jump to and flash that element
- **Size of the problem** — current `n` and `m` against the target `n′ = n₊ + n₋ + 2n_f + m₁ + m₃`
- **Reading the answer back** — the accumulated dictionary (`z* = −w′* + 5`, `x₂ = −x′₂`, `x₃ = x′₃ − x″₃`, discard the slacks)
- **Moves made** — a numbered log; click any entry to rewind to just before it

Plus *Suggest a move*, *Undo*, *Start over*, and **Run to the end**, which animates the whole
reduction move by move — useful for demonstrating from the front of a room.

### Reference material

Below the worksheet the page carries the full statement of the general and standard forms,
the four transformation rules with their sub-cases, the `n′` accounting table, the solution
read-back table, and seven notes of fine print — including that standard form does **not**
require `b̄ ≥ 0` (that belongs to Phase I), and that flip-then-slack and subtract-a-surplus
are two names for one move.

---

## The four rules

1. **R1 — Make the objective a maximization.** `min f(x) = −max(−f(x))`. The optimal solution is
   untouched; only the optimal value flips sign.
2. **R2 — Drop the constant.** A shift of every objective value cannot change which point wins;
   add `c₀` back at the end.
3. **R3 — Turn every constraint into an equation.** A `≤` row takes a slack `sᵢ ≥ 0`. An `=` row is
   left alone. A `≥` row is first multiplied by −1 to become `≤`, then takes a slack. Rows are never
   added or removed, so `m′ = m`.
4. **R4 — Make every variable nonnegative.** `xⱼ ≥ 0` is kept; `xⱼ ≤ 0` becomes `xⱼ = −x′ⱼ`; a free
   `xⱼ` splits into `x′ⱼ − x″ⱼ`. Slack variables from R3 are already nonnegative.

Rules 1 and 2 touch only the objective. Rules 3 and 4 commute — the worksheet lets students verify
this by applying them in any order and landing on the same standard form.

---

## Running it

The tool is a **single self-contained `index.html`**. No build step, no dependencies, no server code.

```bash
git clone https://github.com/hcharkhgard/foundations-of-optimization.git
cd foundations-of-optimization/tools/standard-form-worksheet
open index.html          # or just double-click it
```

The only external request is a Google Fonts stylesheet (STIX Two Text for the mathematics,
IBM Plex Sans for the interface). Offline, the page falls back to system serif and sans faces and
remains fully usable.

Works in any modern browser, adapts to light and dark themes, and is usable down to phone width.

## Deployment

Part of the [Foundations of Optimization](../../) course repo, served by GitHub Pages from its `main` branch.

## License

MIT — see [LICENSE](../../LICENSE). Free to use, adapt, and share for teaching.
