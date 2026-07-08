# scholar-positioning

Build evidence-bounded scholar profiles, multi-scholar positioning maps, and optional derived roadmaps from public or raw research materials.

This package is designed for research workflows where you want to:

- deeply deconstruct one scholar
- compare multiple scholars without collapsing them into vague similarity
- identify benchmark roles, bridge scholars, and transfer paths
- keep inference visible through explicit evidence and coverage boundaries

## What this skill does

The skill separates three artifact types:

- `profile`: a single-scholar dossier
- `positioning`: a multi-scholar map
- `roadmap`: an optional derived route hypothesis

The core design principle is:

> allow inference, but never leave it unlabeled

## Why this skill exists

Most scholar-analysis prompts fail in one of four ways:

- they compress a scholar into a short summary too early
- they mix profile-building with map-building
- they infer strong scholar relations from weak evidence
- they produce a “roadmap” that is really unsupported field forecasting

This skill is built to resist those failure modes.

## Package structure

- [SKILL.md](./SKILL.md): main protocol
- [references/source-pack.md](./references/source-pack.md): intermediate artifact logic
- [references/retrieval-protocol.md](./references/retrieval-protocol.md): public-source retrieval order and stop conditions
- [references/source-pack-template.md](./references/source-pack-template.md): working scaffold
- [references/source-pack-eval-checklist.md](./references/source-pack-eval-checklist.md): pre-drafting gate
- [references/seed-taxonomy.md](./references/seed-taxonomy.md): starter label vocabulary
- [references/label-aliases.md](./references/label-aliases.md): label normalization rules
- [references/taxonomy-update-rules.md](./references/taxonomy-update-rules.md): seed maintenance rules
- [references/roadmap-derivation.md](./references/roadmap-derivation.md): roadmap protocol
- [references/roadmap-eval-checklist.md](./references/roadmap-eval-checklist.md): anti-drift roadmap check

## Core ideas

### 1. Build profiles before maps

`positioning` should consume reusable scholar dossiers.
It should not guess missing scholar structure from a name list.

### 2. Keep evidence and coverage explicit

The skill uses:

- evidence levels: `E1` to `E4`
- coverage levels: `C1` to `C3`

This makes it easier to separate:

- strong scholar structure
- plausible but provisional synthesis
- speculative idea generation

### 3. Treat roadmap as downstream

`roadmap` is not the default output.
It is only justified when upstream `positioning` is already stable enough.

### 4. Keep taxonomy seed-like

The included taxonomy is a starter vocabulary, not a closed ontology.
It is meant to be maintained as the scholar corpus grows.

## Typical use cases

### Single scholar

Use `full-profile` when you want:

- research trajectory
- intellectual genealogy
- method stamp
- competitive landscape
- later reuse in multi-scholar comparison

### Multi-scholar comparison

Use `build-map` when you want:

- clusters
- bridge scholars
- benchmark roles
- route differences
- transfer opportunities

### Next-step route planning

Use `roadmap` only after a stable `positioning` exists and only when you explicitly want:

- benchmarking order
- missing-scholar priority
- method-transfer route

## Scope and defaults

- Chinese-first output shape is the default in this package because the original working context used Chinese-first artifacts.
- Proper nouns, technical terms, and stable labels may remain in English.
- The protocol itself is general and does not depend on one domain or one scholar set.

## What this package does not include

- private scholar corpora
- local note templates
- private prompts or project-specific source files
- example outputs based on unpublished or user-specific materials

## Suggested publishing posture

This package is best treated as:

- a reusable protocol
- a high-structure research skill
- a starting point for adaptation

It is not a promise that every scholar can be reconstructed to the same depth from public sources alone.

## License

MIT. See [LICENSE](./LICENSE).
