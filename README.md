# Maryamiyya / Traditionalist School — Cronologia

A **compiled static website** documenting the chronology of the **Maryamiyya
tariqa** — the Sufi order founded by Frithjof Schuon — and the wider
**Traditionalist School** (Guénon–Schuon perennialism), with special attention
to its documented **connections**: to Catholic traditionalism (Rama
Coomaraswamy and the SSPX milieu) and to Brazil (the 1987 Brazilian branch and
Olavo de Carvalho's years as its muqaddam).

Part of the [Cronologia](https://cronologia.github.io) project family; built
from the [`cronologia/core`](https://github.com/cronologia/core) template.

## How it works

A single JSON file is the source of truth; a zero-dependency Node script
compiles it into plain HTML served by GitHub Pages.

```bash
node scripts/validate-data.js   # schema check
node --test                     # unit tests + docs drift check
node build.js                   # compile data/chronology.json -> docs/
python3 -m http.server -d docs 8000
```

### Publish (GitHub Pages)

Settings → Pages → Source: **GitHub Actions**, plus the Actions variable
**`ENABLE_PAGES=true`** (enable Pages while `main` is the default branch).
The workflow deploys on push to `main` and supports manual dispatch.

## Editing the data

All content lives in `data/chronology.json` (`facts[]`, `events[]`,
`figures[]`, `organizations[]`, `disambiguation.items[]`, `references[]` —
every fact cited via reference ids; the validator enforces it). Edit, rebuild,
and commit the regenerated `docs/` in the same change.

## Data quality

A work in progress about a **semi-private initiatic order and, in part,
living people**. This repo follows the family's sourcing rules with extra
strictness (see `AGENTS.md`): published scholarship and participants' own
public writings only; every contested characterization attributed; the 1991
Bloomington affair always carried together with its resolution; no private
individuals. Corrections against published sources are welcome.

## License

[MIT](LICENSE)
