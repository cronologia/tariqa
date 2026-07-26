# KEYWORDS — Tariqa Maryamiyya — Cronologia

**What this file is:** a finding aid for *searching sources* — the strings that
actually retrieve this project's subject in a corpus, a transcript, a vaulted
capture or the dataset itself, together with the obvious searches that fail.
**What it is not:** a dataset, a claim, or an endorsement. Listing a term
asserts nothing about the world. `schism`, `apostate`, `Julius Evola Maçom da
Seita Judaica` and `pedofilia` appear below because hostile and partisan
sources use those words and a researcher must be able to *find* their pages —
not because this project adopts them. Every claim about the subject lives in
`data/chronology.json`, attributed to whoever makes it and cited
(`sourcing-rules` #1, #2); nothing in this file is a source for anything. The
lower half of the page is **generated** from the dataset and is overwritten on
every regeneration; the `## Search traps` section is **hand-curated**, lives
outside the generated markers, and survives.

## Search traps

Everything here was observed — in this repo's dataset, in its tickets, in the
`cronologia/archive` vault, or measured in an agent session (2026-07-25; §9 was
measured 2026-07-26 and carries its own date). Nothing
is invented: an invented variant is a search someone will waste an hour on.
Each entry gives the trap and the term that actually works. Counts are *files
containing the term*, not occurrences, unless stated.

### 1. Terms that return nothing

The subject is present; the obvious word is not.

| You search | Result | Search this instead |
|---|---|---|
| `Sufi master` (dataset) | **0 rows** | `muqaddam` (10), `shaykh`, `khalifa` (4) — the Arabic title is never translated here |
| `spiritual chain` / `lineage chain` (dataset) | **0 rows** | `silsila` (3) |
| `Society of Saint Pius X` (dataset) | **0 rows** | `SSPX` (6) — this repo uses the acronym only |
| `FSSPX` (COF corpus, 7,156,995 words) | **0 files** | `Sociedade de São Pio X` (3 files) — the mirror image of the line above; the initialism that works in one repo fails in the other |
| `muqaddam`, `silsila`, `dhikr`, `zawiya`, `bay'ah`, `khalifa` (COF corpus) | **0 files each** | `tarica`/`tariqa`, `sheikh`, `shake` — five years of Olavo lecturing about his own order and *not one* of the technical terms survives transcription |
| `shaykh` (COF corpus) | **0 files** | `sheikh` (11), `xeque` (2), and the ASR form `shake` (145 — noisy, see §4) |
| `silsila`, `dhikr`, `zikr`, `bay'ah`, `khalifa` (121 vaulted transcripts) | **0 hits each** | nothing works — the concepts are there, the vocabulary is not. `muqaddam` survives exactly once (transcript-58), `zawiya` exactly once (transcript-52) |
| `Maryamiya` (one *y*), `Mariamia` (dataset) | **0 rows** | `Maryamiyya` — but see §2, the vault spells it neither way |
| `Marian order`, `Mary order` (dataset) | **0 rows** | `Maryamiyya` (45 as the stem `Maryami`) |
| `religio perennis` (dataset, spaced) | **0 rows** | `perennialism` (7); `religioperennis` is a *reference id*, not prose |
| `apostate` (dataset) | **0 rows** | the word is in `AGENTS.md`'s source-labelling vocabulary, not in the data — search `critic` (17) or read `references[]` perspective labels |
| `never a formal member` (dataset) | **0 rows** | `formal member` (3) — the dataset writes "never a formal **Maryamiyya** member" and "never (as an Orthodox Christian) a formal member"; the words are split |
| `Guénon`, `Schuon`, `Sufi`, `tradicionalismo` (transcript-64) | **0 each** | nothing — that programme is a *parallel* occultist genealogy (Fabre d'Olivet → Saint-Yves d'Alveydre → Evola) that never mentions Guénon. Recorded in `perennialism#18`. Do not read its absence as evidence about this repo's subject |
| `Fabre`, `Olivet`, `Saint-Yves`, `Alveydre`, `Papus`, `Blavatsky`, `Theosoph*` (transcripts 48 Sedgwick, 119 Teitelbaum) | **0 each** | nothing — the scholarly anchors and the occultist genealogy share no vocabulary at all (`perennialism#18`) |

The 4h44 video titled *"A Tariqa do Schuon: Tudo Sobre a Tariqa Maryamiyya"*
(transcript-57, 28,564 words) contains `tariqa` ×1 and `Maryamiyya` ×1 — **both
in the title line** — and `muqaddam`, `Vâlsan`, `Olavo`, `1991`, `Alawiyya`,
`Mostaganem` ×0 (mining report, `tariqa#10`). **A title is not an index.**

### 2. Naming variants across languages and source families

| Thing | Forms actually observed, and where |
|---|---|
| the order | `Tariqa Maryamiyya` (scholarship, dataset) · `Maryamiyya` alone (standard in scholarship) · full style `Tariqa Shadhiliyya-Darqawiyya-Alawiyya-Maryamiyya` (dataset `disambiguation`) · `Mariamia` / `Mariâia` (PT auto-captions, transcript-121) |
| *tariqa* | `tariqa` (64 occurrences, COF) · `tariqas` (23) · `Tarika` (11) · `Tarikat` (2) · `tariqah` (2) · `tarîqa` (`tariqa#30`) · **`tarica` / `taricas` (257 occurrences across 43 COF files — more files than the correct spelling)** · `Taric`, `Tarik`, `Tarique` (transcripts) |
| Guénon | `Guénon` (95 COF files) · **`Guenon` unaccented (54 COF files)** — you must run both · `Guenom` (1) · `Guenonianos` (adjectival, PT) |
| Schuon | `Schuon` · `Isa Nur ad-Din Ahmad` (his Muslim name, dataset `figures[1]`) · `Sheikh Isa` (member testimony, transcript-57) · **`Schuon's` and `Schuon,` defeat a whole-word grep** |
| Olavo's Muslim name | dataset: `Sidi Muhammad Ibrahim` (1 row) · transcript-58 writes **`Mohamed Ibrahim`** (0 rows in dataset) — search `Ibrahim` alone |
| Olavo's nickname | `Guru de Virgínia` — a Brazilian *press* nickname for Olavo de Carvalho from his 2005–2022 Virginia residence. **It is not a title about Schuon** (dataset `disambiguation`, "Names and nicknames") |
| the school | `Traditionalist School` · `Guénonian Traditionalism` · PT `tradicionalismo` · `perennialism` / PT `perenialismo` (one *n* in PT) / `philosophia perennis` / `religio perennis` |
| Sedgwick's book | `Against the Modern World` (5 rows) · abbreviated `AtMW` in the dataset and in tickets — a distinct string worth its own grep |

### 3. ASR manglings observed in the vaulted transcripts

The vault's transcripts are **cleaned YouTube auto-captions**. Proper names are
mangled systematically and the manglings below were each recorded by a mining
report or read out of the file this session. Rule 5 of `sourcing-rules` still
applies: **verify any name against audio before quoting it.**

**Schuon** — the worst-hit name in the corpus:
`Shuan` (32) · `Chuon` (17) · `Chuan` (6) · `shuwon` (3) · `chon` · `Xuon` ·
`Chuanon` · `Sean` · **`Juan`** · `Freedia of Schwann` (transcript-57) ·
PT re-cuts: `João` · `Chorão` · `Xoom` · `shoham` · `show` · `som` ·
`Forro` · `Sul` · `vento fogo` · `Flor do chá`
(tickets `tariqa#9`, `#10`, `#11`, `#12`, `#13`, `#14`).

**Coomaraswamy** — `Kumarazuami` (9) · `Comaram` (5) · `Kumarau` (2) ·
`Comarasvam` · `Comarasami` · `Comara` · `com Marazvam` · `anandakumara Swami`
(transcript-121, transcript-57). Also `a rama comar` (transcript-54) — that is
*Rama Coomaraswamy*, not a Portuguese noun phrase.

**Others, each recorded in a mining report:**

| Real name | Observed as |
|---|---|
| Guénon | `renegeno` · `gaynon` · `renega` · `o Face` · `Rei ninguém` · `reino` |
| Martin Lings | `Martin links` · `Martins` |
| Marco Pallis | `local Palace` · `Moco Palace` · `Marco` (bare) |
| Seyyed Hossein Nasr | `NASA` · `said Hussain nasser` |
| Titus Burckhardt | `Titus burkhard` · `Burkhart` |
| Joseph Epes Brown | `apps Brown` |
| Benjamin Teitelbaum | `Benjamin tio Val` |
| Steve Bannon | `Belo` · `Banu` · `Gana` · `bebê não` · `estive bem não` · `B nanismo` |
| Julius Evola | `Juliano` · `Júlio Évora` |
| Aleksandr Dugin | `seu dugin` · `Dublin` |
| Sioux | `tribo Sul` |
| Lucy Cherbas (grand jury foreperson, unverified) | `Lucy servos` · `Lucy Jarbas` |
| Idries / Omar Ali-Shah | `Sheik` · `som` — **confusable with the Schuon manglings in the same file**; transcript-61 has passages that cannot be assigned to Schuon or to Shah without re-listening (`tariqa#14`) |
| *compagnonnage* | `companheiragem` |
| the channel *Paz e Bem* | `passe bem` · `posse bem` · `quase bem` · `faz bem` — **source and channel names mangle too, not just people** |

**Word-boundary loss is the subtlest failure.** ASR merges the article into the
noun, so a whole-word search finds nothing:
`na tariqa Maryamiyya` → **`Natarica Mariamia`** / `Natarica Mariâia`
(transcript-121); `muqaddam da tariqa` → **`muqaddam dare Ka`**
(transcript-58); `a tariqa` → **`Itarica`**, `Atarica`, `Matarica`,
`taricatólico` (COF). Search substrings (`taric`, `mariam`, `kumara`), never
only whole words.

### 4. Ambiguous referents and false friends

**Three distinct people and figures are called "Rama". Never conflate them.**

| Referent | Who | Whose repo |
|---|---|---|
| **Rama P. Coomaraswamy** (1929–2006) | the physician — thoracic surgeon, later psychiatrist; taught ecclesiastical history at the SSPX's Ridgefield seminary; sedevacantist priest. Per Sedgwick (*AtMW* p.161) **never a formal Maryamiyya member** but a personal follower of Schuon | **this repo** `figures[3]` **and `cronologia/fsspx`** `figures[18]` (the dossier is fsspx#19) |
| **Ananda K. Coomaraswamy** (1877–1947) | *his father* — Ceylonese-British art historian, Boston MFA curator; one of the school's three founding authors. Died before the Maryamiyya existed under that name | this repo `figures[2]`; the ideas are **`cronologia/perennialism`** `figures[1]` |
| **Rama, the mythical Vedic figure** | of French occultist historiography (Fabre d'Olivet, Saint-Yves d'Alveydre) — the subject of the *Paz e Bem* programme, transcript-64. **A myth, not a person in this dataset**, and unrelated to either Coomaraswamy | `cronologia/perennialism#18`, which flagged this collision |

A dataset search for `Rama` in this repo returns only the Coomaraswamys.
A *corpus* search for `rama` returns mostly none of the three — see below.

**False friends — same string, different subject:**

- **`rama` in Portuguese and Spanish means "branch"**, and it is common.
  Observed: `la rama femenina`, `la primera rama` (ES, transcript-94, about a
  Catholic movement's women's section), `a rama` (transcript-64, mid-sentence
  about the Vedic figure). Searching `rama` in a PT/ES corpus mostly retrieves
  botany and org charts. **Search `Coomaraswamy` (or `kumara`, `comara`) when
  you mean the man**; use `Rama P.` or `Dr. Rama` for the physician.
- **`Burke` is not Burckhardt.** Every `Burke` in the vault is *Cardinal
  Raymond Burke* in the fsspx transcripts (including the ASR `Colonel Burke`).
  Titus Burckhardt appears as `burkhard` / `Burkhart` — search those.
- **`Joe Schmo`** in transcript-56 is the English idiom, not Schuon.
- **`Juan`** appears 57 times in the vault. In transcript-57 (`"but Juan would
  say"`) it is **Schuon**; elsewhere it is the Spanish given name. Check the
  sentence before you count a hit.
- **`guenta`, `guento`, `guentar`, `guentou`** (~20 hits) are the colloquial
  Portuguese verb *aguentar*, **not** Guénon. A prefix search on `guen` is
  poisoned; use `guén` or `Guenon` with a capital.
- **`shake`** (145 COF files) is sometimes *shaykh* and sometimes the English
  word — and `Shakespeare` matches it too. Never take a `shake` count as a
  *shaykh* count.
- **Three different things are called "traditionalism"** and the site exists
  partly to keep them apart (`disambiguation.items[0]`, `[1]`;
  `context.md`): the **Traditionalist School** (this repo), **Catholic
  traditionalism** (`cronologia/fsspx` — Lefebvre, Écône, sedevacantism), and
  **Evola's political Traditionalism** and its Bannon/Dugin-era reception. A
  bare search for `traditionalism` crosses all three.
- **`Sophia`** is both Nasr's journal and part of the publisher name *Sophia
  Perennis* (`organizations[8]`, `[9]`) — two different entities.
- **Nova Resistência / Raphael Machado** (1 row) is Duginist political
  Traditionalism that "flirts with Guénonism" per one attributed 2023 account —
  **not** the Maryamiyya's initiatic line. Do not file its hits here.

### 5. Terms of art — do not translate when searching

These are **not translated** in the sources or in this dataset. Searching the
English gloss finds nothing (§1). Each has a glossary entry in
`cronologia/glossary`; define it there, never re-explain it here.

| Term | Glossary id | Variants to try | Do **not** search |
|---|---|---|---|
| silsila | `[[silsila]]` | `silsilah` | "spiritual chain", "initiatic chain", "lineage" |
| muqaddam | `[[muqaddam]]` | — (also a civil/military title in Arabic — check context) | "Sufi master", "representative", "deputy" |
| khalifa | `[[khalifa]]` | `khalīfa`, `khilafat`, `khalifas` | "caliph" (different sense), "successor" |
| zawiya | `[[zawiya]]` | `zāwiya`, `zaouia`; cf. `khanqah`, `tekke` | "lodge" (0 rows), "Sufi centre" |
| dhikr | `[[dhikr]]` | `zikr` | "remembrance of God", "invocation" |
| bay'ah | `[[bayah]]` | `baya`, `bay'at` | "oath of allegiance", "pledge" — **not yet used in this dataset**; the id exists for when it is |
| tariqa | `[[tariqa]]` | see §2 — the single most-mangled term in the corpus | "Sufi order", "brotherhood" |
| philosophia perennis | `[[philosophia-perennis]]` | `perennial philosophy`, `perennialism`, PT `perenialismo` | — |
| Traditionalist School | `[[traditionalist-school]]` | `Guénonian Traditionalism` | bare "traditionalism" (see §4) |

### 6. Recorded divergences — try both terms

These are **disagreements between sources that the dataset deliberately does
not resolve**. A search for only one term silently drops the other side.

- **`khalifa` vs `muqaddam` for Olavo de Carvalho's role in Brazil.**
  Sedgwick's obituary notice (28 Jan 2022) calls him *"briefly a Maryami and
  the khalifa of Frithjof Schuon in Brazil"*; this dataset and the Brazilian
  sources say **muqaddam**. The two titles are distinct and the divergence is
  recorded, not resolved (`events[19]`). **Search both**, and expect
  `figures[17]` to read `muqaddam/khalifa`.
- **Founding of the Brazilian branch: 1986 (Sedgwick) vs 1987** (Brazilian
  tertiary sources) — `events[19]`, `organizations[6]` (`1986/87`).
- **Olavo's break with Schuon:** 1987 (Bunker) / "late 1980s" (Sedgwick) /
  1987–91 (Jardim das Aflições) — and **Olavo's own tellings are mutually
  inconsistent**, which is itself the durable fact (`events[20]`, `tariqa#11`,
  `#13`, `#14`). Search year-by-year, not for one date.
- **The 1991 indictment date:** the dataset carries `1991-10-15/11-20`
  (verified); a critical video says 11 October (`tariqa#11`). Unresolved
  pending the *Herald-Times* clipping. Try both days.
- **Schuon's 1936 assumption of the shaykhate:** followers' accounts describe a
  divine investiture confirmed by disciples' dreams; Sedgwick treats it as
  self-authorization (`facts[1]`, `events[7]`). The *event* is one; the
  *vocabulary* is two.

### 7. Affiliation vocabulary is load-bearing — these are not synonyms

`AGENTS.md` fixes the vocabulary as **member / initiate / muqaddam / follower /
adjacent / critic**, and `xref.py` reports a mismatch between repos as
`DIFFERS`. Searching one word will not find the others, and substituting one
for another falsifies the record.

- **`follower` ≠ `member`.** Sedgwick documents a category the record keeps
  flattening — the "Christian Schuonians", Christians who followed Schuon
  personally *without ever joining the tariqa*: **"none of these Christians
  were actually members of the Maryamiyya, but they followed Schuon personally
  as a Maryami would"**. That covers Rama Coomaraswamy's American Catholic
  group, probably Jean Borella's French circle, and James Cutsinger — *"never
  (as an Orthodox Christian) a formal member"*
  (`disambiguation`, "Follower ≠ member").
- **`adjacent` ≠ `initiate`.** Charles Upton is `adjacent` by his own 2017
  self-disclosure — never a member (`figures[16]`, `lineage.trees[0]`).
  Reading Guénon, publishing in a perennialist journal or attending a lecture
  makes someone adjacent, not a member.
- **`not a member` / `!member`** is how `lineage.trees[0]` and `xref.py` mark
  the negative. A grep for `member` matches it — read the polarity.
- **Thomas Yellowtail**: what is documented is *the adoption and the
  friendship*, **not membership** (`figures[12]`). Do not let a `Yellowtail`
  hit become a membership claim.
- Membership enters only on **self-disclosure or published scholarship**, with
  the attribution attached. If a search turns up a membership claim without
  one, it is a lead, not a fact.

### 8. Where else to look — you may be in the wrong repo

| If you are searching for… | Go to |
|---|---|
| works, journals, reception, the Evola line and its political readings — **the ideas** | `cronologia/perennialism` (`adr/0001`: this repo owns the **order**, that one owns the **ideas**; an event belongs to exactly one) |
| Lefebvre, Écône, the SSPX, sedevacantism — **Catholic traditionalism** | `cronologia/fsspx`. Note its corpus writes `Sociedade de São Pio X` and `Monsenhor Lefebvre`, **not** `FSSPX` |
| the **Rama P. Coomaraswamy dossier** (the bridge figure) | `cronologia/fsspx` `figures[18]`, ticket fsspx#19 — this repo carries the tariqa-side entry only |
| shared term definitions (`silsila`, `zawiya`, `dhikr`, `muqaddam`, `khalifa`, `bay'ah`, `tariqa`, `sedevacantism`) | `cronologia/glossary` — **define once there**, never re-explain here |
| the Brazilian / Olavo de Carvalho **critical literature** | `cronologia/fsp` |
| transcripts, the **COF corpus** (589 files, 7,156,995 words), web captures | `cronologia/archive` — `transcripts/index.json` and `cof/index.json` are the **index of record**, not the directory listing (archive `adr/0003`) |
| a source that 403s, 406s or is geoblocked | the `net-access` skill; archive `adr/0002` holds the per-site register |

**Two things about the COF corpus specifically.** It is split
`revisadas/` (257 files, human-reviewed) and `revisao_pendente/` (332 files,
not reviewed) — and **the review pass fixes the spelling**. `tariqa` sits in 17
reviewed files but only 5 pending ones, while `tarica` sits in 5 reviewed files
and **47 pending** ones. Search the correct spelling and you will
systematically miss the unreviewed two-thirds of the corpus. And a term's
*file* count says nothing about density: `Lefebvre` appears in both `COF081`
and `COF138`, but once in COF081's 18,310 words versus four times in COF138's
15,787 — the obvious term misranks as well as under-retrieves.

### 9. Two counting traps in the COF corpus — measured, and each large enough to invalidate a whole search

Both were re-measured in this repo on **2026-07-26**, over the vaulted corpus
(`cronologia/archive`, `cof/index.json`, 589 files / 7,156,995 words). They are
the reason the 2012–2015 mining wave exists at all: the first one hid ~90% of
the Guénon material from anyone who trusted the entity index, and the second
inflates every count of Olavo's own presence by about half.

**Trap A — the entity index is not a mention index.** `cof/index.json` gives
each file an `entities[]` list of *distinctive* entities, and `cof-xref.py`
matches this repo's `figures[]`/`organizations[]` against it. For **René
Guénon** that returns **15 aulas** (`cof-xref.py --repos tariqa`, with the
committed alias map: COF005 033 041 043 081 094 131 209 218 223 246 342 344 354
465). The **full text** of the same corpus matches him in **121 files**
(case-insensitive `gu[ée]non`; 114 with the case-sensitive `Gu[ée]non`; the
archive records 121 in `archive#14`). **Treating `cof-xref.py` output as
coverage misses 106 of the 121.** The tool is a *lead generator over entities
the datasets already name* — it is not, and does not claim to be, a
concordance. Grep the full text; use `cof-xref.py` to rank, never to bound.

**Trap B — the `Olavo de Carvalho` byline.** A raw string count returns
**291 of the 589 files**. But **218 of the 257 `revisadas` carry a standalone
line consisting of exactly `Olavo de Carvalho`** — the transcription's credit
header, three lines down from `*Curso Online de Filosofia*` — and in **134 of
them that byline is the only occurrence in the file**: roughly **46% pure
boilerplate**. (Across the 257 reviewed files the string occurs 430 times in
253 files.) His own speech inside a lecture is separately prefixed `Olavo:`,
and student questions are prefixed `*Aluno:*` / `*Aluna:*`. **Strip the
credit block before counting anything** — the standalone byline line, and any
line beginning `>` (82 of the 257 reviewed files open with a blockquoted
header/credit). Counting `Olavo:` finds him speaking; counting
`Olavo de Carvalho` mostly finds the cover page.

**Two more false friends, found while working the 2012–2015 run:**

- **`Alger` is not Algeria.** In `COF158` it is **Alger Hiss**, the US
  espionage case. Search `Argélia`, `argelino`, `Mostaganem`.
- **`Azevedo` is not Mateus Soares de Azevedo.** In `COF208` it is
  **Reinaldo Azevedo**, the Brazilian columnist. This repo's `figures[18]` is
  the perennialist author; search the full `Mateus Soares` or `Soares de
  Azevedo`.
- **`\bsufi` matches `suficiente`.** Re-confirmed here; `archive#13` §2 measured
  ~96% false positives corpus-wide. Never report a bare `sufi` count.

**One term that does survive transcription, and was not previously recorded:**
**`fakir`** — Olavo's word for the disciple in a tariqa (`COF220`,
14 September 2013: the disciple is in the shaykh's hands as a corpse is in the
hands of the one who washes it). It appears **once** in the 35 aulas of the
2012–2015 run, which is once more than `muqaddam`, `silsila`, `dhikr`,
`zawiya`, `bay'ah` or `khalifa` manage anywhere in the corpus (§1). Also worth
trying: `sheik` and `xeique` for the shaykh, and `tariqa móvel` — his phrase in
`COF156` for a multi-confessional order built to operate in the West.

<!-- BEGIN GENERATED build-keywords.py -->
<!-- Generated by core/tools/build-keywords.py from tariqa/data/chronology.json (meta.lastUpdated 2026-07-26).
     Regenerate: python3 core/tools/build-keywords.py tariqa --out KEYWORDS.md
     Edits INSIDE this block are lost on regeneration; everything outside it is kept. -->

## How to use this list

**This block is a finding aid, not a dataset.** It lists strings worth
searching for — names, aliases, acronyms, spellings, and the vocabulary of
sources across the spectrum, hostile ones included. Listing a term asserts
nothing about the world: `schism` appearing in a search list does not claim
anyone is schismatic, and a critical source's word for something is listed so
its pages can be *found*, not endorsed. Every claim about the subject lives in
`data/`, attributed to whoever makes it and cited (`sourcing-rules` #1, #2).

Every string below was read out of this repo's dataset by the generator.
Nothing here is inferred or remembered. Variants seen elsewhere — in a corpus,
a transcript, an auto-caption — and terms that return **zero** hits belong in
the hand-written section outside this block, with a note on where they were
seen or searched.

## Subject names (3)

What the subject is called, from `meta` — plus every name the description puts in parentheses (acronyms, native-language forms, and whatever else it names in passing; the source field is on each line). A corpus may use exactly one of these and none of the others.

- `Tariqa Maryamiyya — Cronologia` — meta.title
- `Tariqa Maryamiyya` — meta.title
- `Guénon–Schuon perennialism` — meta.description (parenthetical)

## People (20)

Every `figures[]` name, with the aliases and both sides of an `A — B` name. An `id` is that figure's own page — a permanent URL and a searchable handle.

- `René Guénon (Abd al-Wahid Yahya)` · figures[0] · also: `René Guénon`, `Abd al-Wahid Yahya`
- `Frithjof Schuon (Isa Nur ad-Din Ahmad)` · figures[1] · also: `Frithjof Schuon`, `Isa Nur ad-Din Ahmad`
- `Ananda K. Coomaraswamy` · figures[2]
- `Rama P. Coomaraswamy` · figures[3]
- `Titus Burckhardt (Ibrahim Izz ad-Din)` · figures[4] · also: `Titus Burckhardt`, `Ibrahim Izz ad-Din`
- `Martin Lings (Abu Bakr Siraj ad-Din)` · figures[5] · also: `Martin Lings`, `Abu Bakr Siraj ad-Din`
- `Seyyed Hossein Nasr` · figures[6]
- `Michel Vâlsan (Mustafa Abd al-Aziz)` · figures[7] · also: `Michel Vâlsan`, `Mustafa Abd al-Aziz`
- `Victor Danner` · figures[8]
- `Whitall Perry` · figures[9]
- `Huston Smith` · figures[10]
- `Marco Pallis` · figures[11]
- `Thomas Yellowtail` · figures[12]
- `Jean Borella` · figures[13]
- `James S. Cutsinger` · figures[14]
- `Wolfgang Smith` · figures[15]
- `Charles Upton` · figures[16]
- `Olavo de Carvalho` · figures[17]
- `Mateus Soares de Azevedo` · figures[18]
- `Alberto Vasconcellos Queiroz` · figures[19]

## Organizations (10)

Every `organizations[]` name and alias. Acronym and full name are listed separately: sources use one or the other, rarely both.

- `Tariqa Alawiyya (parent order)` · organizations[0] · also: `Tariqa Alawiyya`
- `Tariqa Maryamiyya` · organizations[1]
- `The Vâlsan / Paris line` · organizations[2] · also: `The Vâlsan`, `Paris line`
- `Bloomington community` · organizations[3]
- `Washington branch (Nasr line)` · organizations[4] · also: `Washington branch`, `Nasr line`
- `London branch (Lings line)` · organizations[5] · also: `London branch`, `Lings line`
- `Brazilian centers` · organizations[6]
- `World Wisdom (publisher)` · organizations[7] · also: `World Wisdom`
- `Foundation for Traditional Studies / journal Sophia` · organizations[8]
- `Angelico Press / Sophia Perennis (publishers)` · organizations[9] · also: `Angelico Press / Sophia Perennis`, `Angelico Press`, `Sophia Perennis`

## Terms of art (8)

Glossary ids used in this dataset (`[[term-id]]` markers), with the visible text authors actually typed. These are *vocabulary*, including contested vocabulary — see the note at the top.

- `[[dhikr]]` · **Dhikr** · used 1× · variants: zikr; 'remembrance' of God · https://cronologia.github.io/glossary/dhikr/
- `[[khalifa]]` · **Khalifa (Sufi usage)** · used 4× · variants: khalīfa, 'successor, deputy'; khilafat (the office conferred); cf. caliph · as written: `khalifas` · https://cronologia.github.io/glossary/khalifa/
- `[[muqaddam]]` · **Muqaddam** · used 7× · variants: an Arabic title also used for civil and military officials; in Sufism, the shaykh's authorized representative · https://cronologia.github.io/glossary/muqaddam/
- `[[sedevacantism]]` · **Sedevacantism** · used 2× · https://cronologia.github.io/glossary/sedevacantism/
- `[[silsila]]` · **Silsila** · used 3× · variants: silsilah; initiatic chain, spiritual genealogy · https://cronologia.github.io/glossary/silsila/
- `[[tariqa]]` · **Tariqa (and the Maryamiyya)** · used 4× · https://cronologia.github.io/glossary/tariqa/
- `[[traditionalist-school]]` · **Traditionalist School** · used 1× · variants: Guénonian Traditionalism; cf. Catholic traditionalism, Evolian 'Traditionalism' · as written: `Traditionalist School` · https://cronologia.github.io/glossary/traditionalist-school/
- `[[zawiya]]` · **Zawiya** · used 1× · variants: zāwiya, zaouia; cf. khanqah, tekke · https://cronologia.github.io/glossary/zawiya/

## Places (35)

Place strings exactly as the dataset writes them, most-used first. Search a component (`Écône`) as well as the full string.

- `Bloomington, Indiana, USA` — 6× (events.place,organizations.place)
- `Paris, France` — 6× (events.place,organizations.place)
- `USA` — 6× (figures.country)
- `Washington, DC, USA` — 4× (events.place,organizations.place)
- `Mostaganem, Algeria` — 3× (events.place,organizations.place)
- `Brazil` — 2× (figures.country)
- `Cairo, Egypt` — 2× (events.place)
- `England` — 2× (figures.country)
- `Lausanne, Switzerland` — 2× (events.place)
- `London, England` — 2× (events.place,organizations.place)
- `Austria / USA` — 1× (figures.country)
- `Basel → Lausanne → Bloomington` — 1× (organizations.place)
- `Basel, Switzerland` — 1× (events.place)
- `Bloomington (Monroe County), Indiana, USA` — 1× (events.place)
- `Bloomington / São Paulo, Brazil` — 1× (events.place)
- `Brazil / USA` — 1× (figures.country)
- `Brooklyn, New York, USA` — 1× (organizations.place)
- `Ceylon / UK / USA` — 1× (figures.country)
- `Crow Indian Reservation, Montana, USA` — 1× (figures.country)
- `France` — 1× (figures.country)
- `France / Egypt` — 1× (figures.country)
- `Iran / USA` — 1× (figures.country)
- `Lausanne / France` — 1× (events.place)
- `Lausanne / Morocco` — 1× (events.place)
- `Lausanne / United States` — 1× (events.place)
- `Paris / Cairo` — 1× (events.place)
- `Richmond, Virginia, USA` — 1× (events.place)
- `Romania / France` — 1× (figures.country)
- `Switzerland` — 1× (figures.country)
- `Switzerland / USA` — 1× (figures.country)
- `São Paulo state, Brazil` — 1× (organizations.place)
- `São Paulo, Brazil` — 1× (events.place)
- `Tehran / United States` — 1× (events.place)
- `United States` — 1× (events.place)
- `United States / online (traditionalist-Catholic media)` — 1× (events.place)

## Dates coverage

The window this dataset spans. A source outside it is not necessarily irrelevant — it is not yet covered here.

| scope | records | years | note |
|---|---|---|---|
| events | 30 | 1912–2025 | 6 with dateVerified:false |
| figures.dates | 20 | 1877–2024 | years parsed from the field text |
| organizations.founded | 10 | 1914–2011 | years parsed from the field text |
| dataset (all of the above) | - | 1877–2025 | meta.lastUpdated 2026-07-26 |

<!-- END GENERATED build-keywords.py -->
