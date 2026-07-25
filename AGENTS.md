# AGENTS.md — cronologia/tariqa

Operating guide for AI coding agents (and humans) working in this repository.
Read this and [`context.md`](context.md) before making changes. The shared
method lives in `cronologia/core` and is **vendored into this repo** at
`.claude/skills/` — start with `sourcing-rules`. The decisions that govern this
repo are in [`adr/`](adr/); the family map is
[`cronologia/core/DEPENDENCIES.md`](https://github.com/cronologia/core/blob/main/DEPENDENCIES.md).

## What this project is

A compiled static website documenting the chronology of the **Maryamiyya tariqa
and the Traditionalist School** (Guénon–Schuon perennialism) and its documented
connections to Catholic traditionalism and Brazil. A single JSON file is the
source of truth; a zero-dependency Node script compiles it into static HTML
served by GitHub Pages.

## Repository map

```
data/chronology.json          SOURCE OF TRUTH — facts, events, figures, organizations,
                              disambiguation, lineage, branchTimeline, references (hand-edited)
data/glossary-terms.json      GENERATED — pinned copy of cronologia/glossary term ids,
                              refreshed by scripts/sync-glossary-terms.js (never hand-edited)
data/i18n/{pt,es}.json        GENERATED — committed machine-translation caches keyed by the
                              English source string, managed by scripts/translate.js
                              (never hand-edited; English is authoritative)
data/archives.json            GENERATED — Wayback snapshot cache written by
                              scripts/archive-refs.js in CI (never hand-edited)
src/styles.css                Stylesheet (copied into the build)
scripts/validate-data.js      Schema check (runs in CI before the build)
scripts/sync-glossary-terms.js  Refresh the vendored glossary term ids (out-of-band)
scripts/translate.js          Translation-cache manager: `--stats` reports pt/es coverage,
                              normalizes data/i18n/*.json (offline-safe, no backend needed)
scripts/archive-refs.js       Wayback availability + Save Page Now (CI only, writes archives.json)
scripts/check-links.js        Link-rot report (CI only; NEVER edits data)
build.js                      Compiler: data/chronology.json -> docs/{en,pt,es}/ + root
                              redirect stub + sitemap.xml/robots.txt (see adr/0002)
test/                         node:test suites (helpers + data invariants + glossary links +
                              viz renderers + docs drift check)
adr/                          Decisions that govern this repo
.claude/skills/               GENERATED — vendored copy of cronologia/core skills/
                              (manifest: .claude/skills/_synced.json)
.github/workflows/deploy.yml      CI: validate, test, build, drift check, Pages deploy
.github/workflows/wayback.yml     Weekly preservation: archive-refs.js -> archives.json + docs/
.github/workflows/link-health.yml Weekly link-rot issue (report only)
docs/                         COMPILED OUTPUT, served by GitHub Pages (committed).
                              docs/index.html is a redirect stub; the real pages live at
                              docs/{en,pt,es}/index.html — one file per (page x locale)
```

## Working agreements

1. **Edit data, not output.** Change `data/chronology.json`, run
   `node build.js`, commit the regenerated `docs/` in the same change.
2. **Keep the build green.** `node scripts/validate-data.js`, `node --test`
   and `node build.js` must all pass; CI fails if `docs/` drifts.
3. **Cite every fact; flag every uncertainty; attribute every contested
   characterization.** The validator enforces non-empty `sources[]`.
4. **A merged PR is finished** — branch fresh from `main` for new work.
5. **One repo, one committer per wave.** Exactly one agent owns this dataset at
   a time; `git status` stays empty in repos you were not assigned.
6. **Never hand-edit generated files:** `docs/`, `data/archives.json`,
   `data/glossary-terms.json`, `.claude/skills/`.

## Sourcing rules

The family's five core rules are the `sourcing-rules` skill, vendored at
[`.claude/skills/sourcing-rules/SKILL.md`](.claude/skills/sourcing-rules/SKILL.md)
(canonical copy: `cronologia/core/skills/sourcing-rules/`). Load it before
touching any data file, site copy or source mining.

## Data quality & sourcing rules (this repo is the family's strictest)

Beyond the five core rules, this subject demands extra strictness:

- **Living people, BLP-grade care.** Several figures are alive. Only
  published, attributable facts; no characterization in the site's own voice.
- **A semi-private initiatic order.** Use published scholarship (Mark
  Sedgwick's *Against the Modern World* and his Traditionalists blog are the
  academic backbone) and participants' own public writings. Never name or
  describe private members.
- **Membership requires self-disclosure or scholarship.** A person is recorded
  as a member, initiate or muqaddam only when they said so publicly or a
  published scholarly source says so — and the claim carries that attribution.
- **Adjacency is not initiation.** Reading Guénon, publishing in a
  perennialist journal, attending a lecture or knowing a member makes someone
  *adjacent*, not a member; the vocabulary must stay exact
  (member / initiate / muqaddam / follower / adjacent / critic).
- **Public figures only.** Private individuals do not enter the dataset at all,
  however well documented.
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

## Which skills apply here, and when

All ten are vendored under `.claude/skills/`. In practice:

| Skill | Load it when |
|---|---|
| `sourcing-rules` | **Always, first.** Any data edit, any site copy, any mining. |
| `data-edit` | Editing `data/chronology.json`: query first, then validate → test → build → commit data + `docs/` together. |
| `ingest-report` | Turning a research report or dossier into dataset entries — verified-with-a-source items only; conflicts recorded, not resolved. |
| `net-access` | A source 403s, 406s, or is geoblocked. Vault first, desktop UA retry, INCONCLUSIVE ≠ dead, never route around the proxy. |
| `preserve-sources` | Reference hygiene: unarchived refs, `archives.json`, link-health output, deciding local vault vs `cronologia/archive`. |
| `adopt-template` | Porting a renderer, validator rule, test or style from `cronologia/core/template/` — additions stay optional and data-driven. |
| `release-work` | Branching, fast-forwarding, committing and pushing a wave; reporting what shipped and what was deferred. |
| `dossier-research` | Building a person dossier (this is a research-heavy repo — Schuon, Nasr, Lings, Rama Coomaraswamy, Olavo de Carvalho). |
| `mine-video` | Interviews, podcasts and testimony: transcript → ticket → verified data. Testimony is a perspective, not a fact source. |
| `bootstrap-project` | Standing up a new sibling repo (not needed for routine work here). |

The vendored copies are **generated**. Fix a skill in `cronologia/core/skills/`
and re-sync; never edit `.claude/skills/` in place:

```bash
python3 ../core/tools/sync-skills.py tariqa            # refresh the vendored copies
python3 ../core/tools/sync-skills.py tariqa --check    # writes nothing; exit 1 if stale
```

## Agent-side tooling (`cronologia/core/tools`, Python 3 stdlib, read-only)

These never run in CI and never write to `data/`. Use them instead of reading
whole files — `data/chronology.json` is ~66 KB and a full read costs more than
the answer is worth.

```bash
python3 ../core/tools/dataset-query.py tariqa stats            # collection counts, year span, gaps
python3 ../core/tools/dataset-query.py tariqa event 1965-1975  # events in a year range
python3 ../core/tools/dataset-query.py tariqa figure Schuon    # one figure, with locator
python3 ../core/tools/dataset-query.py tariqa find muqaddam    # keyword hits with locators
python3 ../core/tools/dataset-query.py tariqa refs --unarchived  # references lacking a snapshot
python3 ../core/tools/unverified-report.py tariqa --markdown   # every unverified flag, as a checklist
python3 ../core/tools/xref.py --repos tariqa,perennialism,fsspx  # shared entities, side by side
python3 ../core/tools/mine-prep.py <transcript>                # transcript -> candidate sheet
```

`dataset-query.py` prints **locators** (`figures[6]`, `events[21]`) — read that
slice, edit it, move on. Run `xref.py` whenever you touch a figure or
organization that another repo also carries; it flags `CONTRADICTION` and
`DIFFERS` for review and resolves nothing automatically.

## The operational loop

```bash
node scripts/validate-data.js   # schema + sources[] + glossary markers + viz shapes
node --test                     # unit tests, data invariants, docs drift check
node build.js                   # compile data/chronology.json -> docs/
git add data docs && git commit  # data + regenerated docs in ONE commit
```

Documentation-only changes must leave `docs/` byte-identical — check with
`git diff --stat -- docs/` before committing.

## Where this repo sits in the family

The canonical map is
[`cronologia/core/DEPENDENCIES.md`](https://github.com/cronologia/core/blob/main/DEPENDENCIES.md).
This repo's own edges:

- **`core`** — consumed **by copy**, never fetched: the template's `build.js`
  renderers, validator, tests, styles and workflows; the skills at
  `.claude/skills/`; the Python tools above. The build is network-free.
- **`glossary`** — shared terms are linked from prose with `[[term-id]]`
  markers (`[[tariqa]]`, `[[zawiya]]`, `[[dhikr]]`, `[[muqaddam]]`,
  `[[silsila]]`, `[[sedevacantism]]`), validated offline against the pinned
  `data/glossary-terms.json`. **Define a shared term once, in the glossary —
  never re-explain it here.**
- **`perennialism`** — the standing boundary: **this repo owns the order**
  (initiations, zawiyas, silsila, branch politics, the 1991 Bloomington affair,
  order-internal ruptures); **perennialism owns the ideas** (works, journals,
  reception, the Evola line and its political readings). An event belongs to
  exactly one of the two; the other cross-links it. See `adr/0001`.
- **`fsspx`** — Catholic traditionalism. It cross-links this repo where a
  figure touches both worlds (Rama Coomaraswamy above all); the three
  "traditionalisms" stay apart.
- **`archive`** — the private shared vault: a source cited by 2+ projects goes
  there (its ADR-0001), single-project sources stay local. Reader-facing
  citations are always the original URL plus its Wayback snapshot, never a raw
  archive URL. Its ADR-0002 is the standing networking policy behind
  `net-access`.
- **`fsp`** — out of this wave's scope, but the Brazilian/Olavo de Carvalho
  critical literature it vaults is the counterpart to this repo's Brazil
  material.
