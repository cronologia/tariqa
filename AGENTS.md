# AGENTS.md (template — adapt per project)

Operating guide for AI coding agents (and humans) working in this repository.
Read this and `context.md` before making changes. The shared method lives in
`cronologia/core` (skills: sourcing-rules, bootstrap-project, mine-video,
dossier-research); the architecture rationale in `cronologia/fsp` → `docs/adrs/`.

## What this project is

A compiled static website documenting the chronology of the **Maryamiyya tariqa and the Traditionalist School** (Guénon–Schuon perennialism) and its documented connections to Catholic traditionalism and Brazil.
A single JSON file is the source of truth; a zero-dependency Node script
compiles it into static HTML served by GitHub Pages.

## Repository map

```
data/chronology.json     SOURCE OF TRUTH — facts, events, figures, organizations, references (hand-edited)
src/styles.css           Stylesheet (copied into the build)
scripts/validate-data.js Schema check (runs in CI before the build)
build.js                 Compiler: data/chronology.json -> docs/
test/                    node:test suites (helpers + data invariants + drift check)
.github/workflows/deploy.yml  CI: validate, test, build, drift check, Pages deploy (main + manual dispatch)
docs/                    COMPILED OUTPUT, served by GitHub Pages (committed)
```

## Working agreements

1. **Edit data, not output.** Change `data/chronology.json`, run
   `node build.js`, commit the regenerated `docs/` in the same change.
2. **Keep the build green.** `node scripts/validate-data.js`, `node --test`
   and `node build.js` must all pass; CI fails if `docs/` drifts.
3. **Cite every fact; flag every uncertainty; attribute every contested
   characterization.** The validator enforces non-empty `sources[]`.
4. **A merged PR is finished** — branch fresh from `main` for new work.

## Data quality & sourcing rules

Beyond the family's five core rules (see the sourcing-rules skill in
`cronologia/core`), this subject demands extra strictness:

- **Living people, BLP-grade care.** Several figures are alive. Only
  published, attributable facts; no characterization in the site's own voice.
- **A semi-private initiatic order.** Use published scholarship (Mark
  Sedgwick's *Against the Modern World* and his Traditionalists blog are the
  academic backbone) and participants' own public writings. Never name or
  describe private members.
- **The 1991 Bloomington affair** is never mentioned without its resolution
  (the sought indictment was dismissed). Dated, attributed, complete — or
  absent.
- **Contested internal dates** (the order's founding, the Marian turn,
  authorizations) differ between sources — record the disagreement, don't
  resolve it by preference.
- **Rupture accounts are partisan on all sides** (Schuon–Vâlsan, Schuon–Olavo
  de Carvalho): attribute every version.
- **Keep the three 'traditionalisms' apart**: this school ≠ Catholic
  traditionalism (fsspx) ≠ Evola's political Traditionalism. The site exists
  partly to keep those wires uncrossed.
