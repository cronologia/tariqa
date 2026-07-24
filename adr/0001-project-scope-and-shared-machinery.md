# ADR-0001 — Scope, source of truth, and what this repo takes from core

- **Status:** accepted (2026-07-24)
- **Context repo:** `cronologia/tariqa`
- **Relates to:** `cronologia/core` ADR-0001 (shared renderer contract),
  ADR-0002 (vendored glossary and skills), ADR-0003 (preservation / link-health
  split); `cronologia/archive` ADR-0001 (shared source vault)

## Context

This repo documents a **semi-private initiatic order**, in part through
**living people**, on a subject where sympathetic, critical and apostate
sources all contradict each other. It is also one of two sibling repos on the
Traditionalist School: `cronologia/perennialism` covers the same milieu from
the side of its ideas. Without a written boundary the two drift into
duplicating — and eventually contradicting — each other.

At the same time the repo has accumulated machinery from `cronologia/core`'s
template in several waves (visualizations, glossary cross-links, a preservation
pipeline). What was adopted, and what deliberately was not, needs recording so
later ports do not re-litigate it or assume capabilities that are absent.

## Decision

1. **`data/chronology.json` is the single source of truth. `docs/` is
   generated.** Facts, events, figures, organizations, disambiguation, lineage,
   branchTimeline and references are hand-edited there and nowhere else;
   `node build.js` compiles them into `docs/`, which is committed and served by
   Pages but never hand-edited. CI fails on drift. The same applies to the other
   generated files: `data/archives.json`, `data/glossary-terms.json` and
   `.claude/skills/`.

2. **The build is consumed from core by copy, and stays network-free.** This
   repo has adopted, per core ADR-0001's optional-key contract:
   - the base compiler `build.js` + `scripts/validate-data.js` + `node:test`
     suites + `src/styles.css` + `.github/workflows/deploy.yml` (validate, test,
     build, drift check, Pages);
   - the **genealogy / lineage renderer** (typed edges with a legend, extracted
     originally from the fsspx site) and the **branch-timeline "subway diagram"**
     renderer, both driven by optional top-level keys (`lineage`,
     `branchTimeline`) plus `meta.vizChips`;
   - **glossary cross-links**: `[[term-id]]` markers expanded by `build.js`,
     validated offline against the pinned `data/glossary-terms.json` and
     refreshed by `scripts/sync-glossary-terms.js` (core ADR-0002);
   - the **preservation pipeline**: `scripts/archive-refs.js` +
     `.github/workflows/wayback.yml` writing `data/archives.json`, whose
     snapshots render as "archived" fallback links, and `scripts/check-links.js`
     + `.github/workflows/link-health.yml`, which report rot into a single issue
     and **never edit the data** (core ADR-0003).

   **Not adopted:** the template's `scripts/translate.js` and multi-locale
   routing. This site is single-language (`meta.language: "en"`); adding locales
   is a future decision, not a current capability.

3. **The subject boundary with `cronologia/perennialism` is standing.**
   This repo owns the **order**: initiations and authorizations, muqaddams,
   zawiyas and silsila, branch politics, the 1991 Bloomington affair,
   order-internal ruptures. perennialism owns the **ideas**: works, journals,
   reception, the Evola line and its political readings. An event belongs to
   **exactly one** of the two repos; the other cross-links it. `cronologia/fsspx`
   owns Catholic traditionalism and cross-links here where a figure touches both
   worlds. Shared entities are checked with `core/tools/xref.py`, which flags
   divergence for review and resolves nothing automatically.

4. **The sourcing discipline is stricter here than the family baseline**, and
   is normative for every edit: published scholarship and participants' public
   writings only; membership recorded only on self-disclosure or scholarship;
   **adjacency is not initiation**; public figures only; contested dates
   recorded, not resolved; the 1991 affair never mentioned without its
   resolution. The full list lives in `AGENTS.md` and is enforced by review, not
   by the validator.

## Consequences

- A contributor can change what the site *says* only by changing
  `data/chronology.json` — every claim therefore passes the validator's
  `sources[]` requirement and shows up in the diff as a cited change.
- Visualization and glossary features are **data-driven and optional**: remove
  the `lineage`, `branchTimeline` or `[[term-id]]` inputs and the output is
  byte-identical to a plain chronology. Ports from core must preserve that.
- Preservation and link-checking run **only in CI or out-of-band**, so a
  sandbox that blocks archive.org never becomes a reason to route around an
  egress policy; an inconclusive fetch (403/429/5xx) is never recorded as a dead
  link.
- Because the order/ideas split is written down, a finding that fits
  perennialism better is *moved there and linked*, not copied — at the cost of
  requiring a cross-repo check (`xref.py`) whenever a shared figure changes.
- Sources cited by this project alone stay local; a source cited by two or more
  projects moves to `cronologia/archive` under its ADR-0001, while
  reader-facing citations remain the original URL plus its Wayback snapshot.
