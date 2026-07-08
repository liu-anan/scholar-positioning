# Retrieval Protocol

Use this reference when a `full-profile` must be built from public or raw materials.

This is the P0 execution layer.
Its job is to raise retrieval quality before any more structure is added to the profile.

## Order of operations

Run retrieval in this order:

1. stabilize scholar identity
2. gather source families
3. build a work inventory
4. select representative works
5. extract phase clues
6. extract genealogy and context clues
7. extract method clues
8. extract neighbor clues
9. judge coverage and stop conditions

Do not reverse this order by writing prose after step 2 or 3.

If `学术谱系` or `研究轨迹` is still thin after the first pass, run one targeted second sweep before drafting:

- genealogy sweep for missing relation/context clues
- trajectory sweep for phase-defining works and phase transition clues

Do not let a coherent top summary hide an under-retrieved dossier spine.

## 1. Identity stabilization

Before broad retrieval, lock these:

- canonical full name
- likely defining affiliation
- field fit
- homonym risk
- one or two work-title anchors

Use at least two of these anchors when homonym risk is non-trivial:

- institution
- recurring coauthors
- representative work titles
- field-specific keywords

Good query shapes:

- `"{Scholar Name}" official homepage`
- `site:edu "{Scholar Name}" CV`
- `site:org "{Scholar Name}" "{Work Title}"`
- `"{Scholar Name}" OpenAlex`
- `"{Scholar Name}" Google Scholar`

Do not merge multiple people with similar names because one metadata page looks plausible.

## 2. Source-family sweep

Try to gather these source families before drafting:

### Identity sources

- official homepage
- institution page
- CV or bio page

### Author metadata sources

- OpenAlex
- Crossref
- DBLP
- Semantic Scholar
- Google Scholar when accessible

### Work-level sources

- titles
- venues
- years
- citation signal
- abstract or accessible full text

### Context sources

- lab page
- project page
- talk or interview
- award or profile page

Minimum target:

- at least 2 source families when possible
- at least 1 work-metadata source
- at least 1 identity or context source unless the scholar is extremely hard to recover

If one source family is blocked, substitute with another.
Do not stop at a single institution page if work-level evidence is still thin.

## 3. Work inventory

Build a broad inventory before selecting the final representative set.

At minimum, capture:

- year
- venue
- title
- why it matters
- which phase it may belong to

Prefer an inventory large enough to see change over time rather than a top-cited-only list.

## 4. Representative work selection

Target at least 5 representative works when possible.

Prefer a spread across:

- early route-forming work
- middle-phase consolidation work
- flagship framework / theory / measurement work
- later synthesis / review / evaluation work
- one or two highly cited anchors

Selection rules:

- do not choose only the most cited papers if they all come from one phase
- do not choose only recent works if the route formed much earlier
- do not choose only generic summaries if the empirical route is visible

Good question:

- does this set let a reader infer how the scholar changed over time

Bad question:

- are these just the biggest citation counts

## 5. Phase-clue extraction

Reconstruct phases from work patterns, not biography chronology.

Primary signals:

- repeated problem vocabulary
- repeated method combination
- application-scene shift
- collaboration or platform shift that changes the work pattern
- emergence of a framework, review, or flagship concept

Secondary signals:

- title vocabulary shift
- venue shift
- institution shift that coincides with a work shift

Bad phase boundary:

- job title changed but the research pattern did not

Good phase boundary:

- the scholar moved from one problem-method bundle to another

## 6. Genealogy and context clue extraction

For `学术谱系`, retrieve more than advisor lineage whenever possible.

Look for these clue types:

- advisor / mentor
- training path
- institution or lab environment
- recurring collaborators
- theory community or tradition
- cross-field bridge role

Evidence can come from:

- official bio or CV
- dissertation pages
- lab membership pages
- repeated coauthor patterns
- interviews or talks
- framework papers that locate the scholar in a community

When genealogy matters and the public homepage is thin, run a dedicated genealogy sweep before downgrading.

Good genealogy-specific query shapes:

- `"{Scholar Name}" dissertation advisor`
- `"{Scholar Name}" thesis advisor`
- `"{Scholar Name}" CV pdf`
- `site:proquest.com "{Scholar Name}" dissertation`
- `site:edu "{Scholar Name}" lab`
- `site:edu "{Scholar Name}" biography`
- `"{Scholar Name}" award lecture biography`
- `"{Scholar Name}" obituary collaborator`
- `"{Scholar Name}" "{Coauthor Name}" interview`

Extra clue sources worth checking:

- dissertation repositories
- commencement or award bios
- seminar speaker bios
- archived lab pages
- memorial or retrospective pages for likely mentors
- edited-volume contributor bios

Genealogy-specific fallback logic:

- if advisor evidence is missing, try to recover the training environment first
- if training environment is visible, try to recover the dominant theory community second
- if both remain thin, use recurring coauthors and flagship concepts to anchor a mixed genealogy
- only then downgrade the section

Do not treat one early coauthor as a confirmed mentor unless a source explicitly supports that relationship.
Do not infer student lineage from topic similarity alone.

If mentor evidence is missing, do not force a mentor chain.
Use a mixed genealogy instead:

- training environment
- theory background
- problem-awareness origin
- collaboration environment

## 7. Method clue extraction

Before writing `方法论印章`, answer these in note form:

- what method combination recurs
- when that combination becomes visible
- what older limitation it seems to solve
- where its boundary conditions show up

Do not accept a slogan without formation clues.

## 8. Neighbor clue extraction

Separate:

- `Direct neighbors`
- `Adjacent routes`

Use these signals:

- same venue cluster
- same problem, different method
- same method, different application
- explicit comparison or dialogue
- repeated co-citation or conceptual adjacency

If the evidence is weak, mark the landscape provisional.
Do not convert loose similarity into strong competition claims.

## 9. Coverage judgment and stop conditions

Use these practical stop rules:

### Stop and keep searching

- identity is still ambiguous
- representative works are fewer than 3 and the scholar is not genuinely sparse
- all works come from one narrow time slice
- no work-level evidence supports trajectory reconstruction

### Downgrade but continue

- mentor chain unclear
- institution path partial
- neighbor evidence mostly venue/topic adjacency
- late-career positioning visible but early formation thin

### Do not support strong map claims

- only `C3 sparse abstract-only`
- bridge claim depends on indirect similarity only
- competitive claim comes from one or two abstracts only

## Minimal retrieval log

Inside the working `source-pack`, keep a compact trace of:

- which source buckets were actually found
- which buckets were missing
- which claims were intentionally avoided

This is not for user-facing polish.
It is for auditability and later updates.

## Common failure modes

- writing the dossier after one official page and a few titles
- over-weighting citation counts
- inferring phase boundaries from job changes alone
- forcing advisor lineage when only institution context is known
- treating topic neighbors as direct competitors without evidence

If you see one of these, the pack is not ready.
