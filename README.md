# Foundations of Optimization

This is the list of all projects and their deployments that **Dr. Hadi Charkhgard (Gard)** used for his course.

**▶ Course page: https://hcharkhgard.github.io/foundations-of-optimization/**

Every tool is a single self-contained web page — no installation, no build step. Open the live link, or download the folder and double-click `index.html`.

## Tools

| Tool | What it teaches | Live tool | Source |
|---|---|---|---|
| Graphical Solution Method | Solving two-variable LPs graphically: constraints, feasible region, objective line, corner points | [Open](https://hcharkhgard.github.io/foundations-of-optimization/tools/graphical-solution-method/) | [`tools/graphical-solution-method`](tools/graphical-solution-method) |
| Standard Form Worksheet | Converting a general LP to standard form one rule at a time | [Open](https://hcharkhgard.github.io/foundations-of-optimization/tools/standard-form-worksheet/) | [`tools/standard-form-worksheet`](tools/standard-form-worksheet) |
| Simplex Method, Algebraic Form | The simplex method step by step when the origin is feasible: basis, Gaussian elimination, reduced costs, minimum ratio test | [Open](https://hcharkhgard.github.io/foundations-of-optimization/tools/simplex-algebraic-form/) | [`tools/simplex-algebraic-form`](tools/simplex-algebraic-form) |

## Repository layout

```
foundations-of-optimization/
├── index.html                      ← the course page (lists every tool)
├── README.md                       ← this file
├── LICENSE
└── tools/
    ├── graphical-solution-method/
    │   ├── index.html              ← the tool itself
    │   └── README.md
    ├── standard-form-worksheet/
    │   ├── index.html
    │   └── README.md
    └── simplex-algebraic-form/
        ├── index.html
        └── README.md
```

## Adding a new tool

1. Make a new folder under `tools/` with a short lowercase name, e.g. `tools/simplex-method/`.
2. Put the tool's page in that folder as `index.html` (plus a short `README.md`).
3. Open the top-level `index.html`, find the `TOOLS` list near the bottom, and copy one entry for the new tool (folder, title, topic, description, features).
4. Add a row to the **Tools** table above.
5. Commit and push. GitHub Pages republishes automatically; the tool is live at
   `https://hcharkhgard.github.io/foundations-of-optimization/tools/<folder>/`.

## Deployment

Served by GitHub Pages from the `main` branch (root folder). Any push to `main` republishes the site.

## License

MIT — see [LICENSE](LICENSE). Free to use, adapt, and share for teaching.
