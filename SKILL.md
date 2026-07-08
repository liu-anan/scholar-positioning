---
name: scholar-positioning
description: Build evidence-bounded scholar profiles and scholar positioning maps from public or local research materials. Use when the user wants to deconstruct one scholar, connect multiple scholars into a positioning map, compare methods or research routes, identify benchmark roles, explore method transfer, or derive field-direction hypotheses with explicit evidence strength.
---

# Scholar Positioning

Build scholar artifacts with explicit evidence and coverage boundaries. Allow inference, but never leave it unlabeled. Write for humans first.

## Layered Architecture

Treat this skill as one architecture with three layers:

1. `core`
   - stable protocol
   - artifact model
   - evidence / coverage rules
   - source-pack and roadmap workflow
2. `domain pack`
   - seed taxonomy
   - alias rules
   - recurring benchmark patterns for a domain cluster
3. `user profile`
   - language defaults
   - summary density
   - human-facing vs AI-facing reading bias
   - naming and presentation preferences

Current public starter default:

- domain pack: transportation human factors / automated driving / HRI adjacent seed
- user profile: Chinese-first, human-readable-first example overlay

Compatibility rule:

- keep the current top-level reference paths working
- do not force a breaking rewrite while moving toward `core + domains + users`

## Core Protocol

- Keep `profile`, `positioning`, and `roadmap` separate.
- Treat `positioning` as the primary multi-scholar artifact.
- Treat `roadmap` as an optional derived layer, not the default product.
- Build `full-profile` from scratch from public or raw source materials by default.
- Treat `build-map` as consuming `full-profile` artifacts only.
- If required scholar dossiers are missing during `build-map`, build the missing `full-profile` artifacts first, then continue the map.
- Do not infer `profile` from `map`, and do not use `map` to backfill missing scholar dossiers.
- Do not force links to the user's project unless the task explicitly asks for benchmarking, transfer, or roadmap discussion.
- Default to Chinese prose; keep proper nouns, technical terms, and stable labels in English when that improves precision.
- Use Chinese-first section headings in saved artifacts. Add English only in parentheses when it improves precision.

## Core vs Seed Layer

Treat this skill as two layers:

- **Core protocol**: artifact model, execution rules, evidence protocol, coverage rules, naming rules, and output shape
- **Current seed layer**: the current default vocabulary and recurring map habits from transportation human factors, automated driving, HRI, and cognitive-AI work

Do not treat the seed layer as a fixed ontology. Keep the core protocol stable and let the seed layer change with the corpus.

Also distinguish clearly between:

- **instructional gold sources**: the canonical scholar-deconstruction prompt and strong example artifacts that define what good output should look like
- **scholar evidence sources**: public or raw materials about the target scholar

Use instructional gold sources to calibrate output quality, section behavior, and analytic density.
Do not use them as factual evidence about the target scholar.

## Artifact Model

Use exactly these artifact types:

- `profile`: a single-scholar dossier answering "who is this scholar?"
- `positioning`: a multi-scholar structure answering "where do these scholars sit relative to each other?"
- `roadmap`: an action hypothesis answering "what route looks promising next?"

## Execution Modes

### 1. `full-profile`

Use for deep single-scholar deconstruction.

This mode is a standalone deliverable. It does not imply `build-map`.
Treat this as a heavyweight scholar dossier, not a lightweight summary.
Build this dossier from scratch from available public or raw source materials.
Do not treat an existing local `Research Map` as the upstream artifact to rewrite.

Output:

- `{ScholarName}_Research_Map.md`

Required sections:

- 基本信息
- 学术谱系
- 研究轨迹
- 方法论印章
- 核心发现实质分析
- 学者类型定位
- 竞争格局
- Positioning Summary
- 证据边界

Use these saved-artifact headings by default:

- `## 基本信息`
- `## 学术谱系`
- `## 研究轨迹`
- `## 方法论印章`
- `## 核心发现实质分析`
- `## 学者类型定位`
- `## 竞争格局`
- `## Positioning Summary`
- `## 证据边界`

Default reading shape for `full-profile`:

1. **顶部摘要层**: a short quick-read block for human scanning
2. **正文档案层**: the full dossier with the complete scholar-deconstruction content

The summary layer is allowed to compress.
The dossier layer is not allowed to replace depth with summary bullets.

Treat the saved artifact as a **summary-on-top dossier**, not as a normalized map-input brief.
If a human reader can only recover the scholar's structure by reading the quick summary, the artifact is too thin.

### `full-profile` completion standard

Treat `full-profile` as complete only when it can support:

- standalone human reading
- later reuse in `build-map`
- incremental updates without redoing the entire scholar analysis
- stable from-scratch reconstruction of the scholar's route and contributions

At minimum, the dossier must answer these questions:

1. what is this scholar's core research problem
2. what academic path produced this scholar
3. what is the scholar's method stamp
4. how did the research trajectory evolve by phase
5. what are the scholar's most substantive contributions
6. what makes the scholar distinct from adjacent scholars
7. what competitive landscape surrounds the scholar
8. what is this scholar best used for in later positioning work

If the dossier cannot answer one of these clearly, it is not yet a stable `full-profile`.

### Anti-compression rule

Do not turn a scholar dossier into a short normalized brief.

Even when working from scratch, preserve these depth layers whenever the evidence supports them:

- concrete academic path and career trajectory
- theory background at field-entry time
- problem-awareness origin
- phase-level empirical support
- specific representative works or milestone papers when available
- explicit uncertainty notes and source limits

Allowed:

- add a short quick-read summary at the top
- tighten repetitive wording
- normalize top-level section order

Not allowed:

- replacing detailed phase analysis with 1-2 summary bullets per phase
- collapsing genealogy background into only a short diagram explanation
- replacing competitive landscape with only 3 names and one-line labels
- dropping milestone works or uncertainty notes that are supported by the gathered source base

Compression test:

- if the dossier is mostly headings plus short bullets, it failed
- if a reader loses the scholar's phase-to-phase evolution, it failed
- if milestone works disappear despite being supported by the source base, it failed
- if the output feels primarily optimized for downstream map ingestion rather than standalone reading, it failed

### Heavy dossier shape

For `full-profile`, the main body should usually feel closer to a compact monograph note than to a schema dump.

Default shape:

1. `## 快速摘要`
2. `## 基本信息`
3. `## 学术谱系`
4. `## 研究轨迹`
5. `## 方法论印章`
6. `## 核心发现实质分析`
7. `## 学者类型定位`
8. `## 竞争格局`
9. `## Positioning Summary`
10. `## 证据边界`

Within the dossier body, prefer this density pattern:

- `基本信息`: factual inventory with enough path detail to locate the scholar historically and institutionally
- `学术谱系`: diagram plus explanatory background, not diagram alone
- `研究轨迹`: multi-phase narrative with explicit phase logic and attached representative works when available
- `方法论印章`: formation logic, solved problem, and limits, not just a signature phrase
- `核心发现实质分析`: interpreted contribution clusters, not label lists
- `学者类型定位`: type label plus contrasts, not type label alone
- `竞争格局`: direct neighbors, alternative framings, open vs saturated space

If the gathered source base supports appendicial layers such as uncertainty notes, key timeline, milestone works, or source notes, preserve them inside the relevant sections or as a short closing note instead of deleting them for neatness.

### `基本信息` requirement

`基本信息` is not a CV dump.
Use it to establish how this scholar became this scholar.

Minimum contents:

- current or most defining institutional position
- training path that materially shaped the research route
- field or domain identity
- representative works, books, or flagship papers when clearly visible
- major platform roles, lab roles, or institutional roles when they materially explain later influence

Prefer:

- compact factual structure
- path-relevant details over prestige accumulation
- enough specificity that a later reader can understand the scholar's historical and institutional placement

Avoid:

- long honor lists with no later analytic use
- generic bio prose
- padding with weakly relevant administrative detail

Good test:

- after reading `基本信息`, the reader should already understand why this scholar entered this field from this angle
- if the section reads like a public homepage bio and does not help the later phase analysis, it is too weak

### From-scratch build rule

Treat `full-profile` as a from-scratch reconstruction task.

Before drafting the dossier body, first build a compact `source-pack`.
See [references/source-pack.md](references/source-pack.md).
For retrieval order and stop conditions, also read [references/retrieval-protocol.md](references/retrieval-protocol.md).
For the working scaffold, use [references/source-pack-template.md](references/source-pack-template.md).
Before turning the pack into prose, run [references/source-pack-eval-checklist.md](references/source-pack-eval-checklist.md).

Preferred source order:

1. official homepage, institution page, CV
2. Google Scholar, Semantic Scholar, DBLP, ResearchGate metadata
3. paper abstracts and accessible full texts
4. interviews, talks, project pages, books, edited volumes
5. secondary summaries only as supplements

Minimum public-source retrieval loop:

1. resolve canonical scholar identity
2. confirm current or defining institution
3. collect author-level metadata
4. collect representative works
5. infer trajectory, method stamp, and competitive landscape from the source pattern

### Public retrieval protocol

For from-scratch `full-profile`, explicitly try to gather these source buckets before writing:

- `identity sources`
  - official homepage
  - institution profile
  - CV or bio page when available
- `author metadata sources`
  - OpenAlex
  - Crossref
  - DBLP / Semantic Scholar / Google Scholar when accessible
- `work-level sources`
  - title, venue, year, citation signal
  - abstract or accessible full text when available
- `context sources`
  - lab page
  - project page
  - interview / talk / award profile

If one source family is blocked, substitute with another.
Do not stop after one institution page if work-level evidence is still thin.

### Scholar identity rule

Before building the dossier, stabilize scholar identity:

- canonical full name
- likely institution or most defining affiliation
- field fit
- whether there are homonyms that could contaminate the search

If homonym risk is non-trivial:

- anchor by institution
- anchor by coauthors
- anchor by representative work titles

Do not silently merge multiple scholars with the same or similar names.

### Representative works rule

For from-scratch profiles, build the dossier around representative works, not around generic biography prose.

Minimum target:

- at least 5 representative works when available
- spread across the scholar's trajectory when possible
- include year and venue

Prefer:

- a mix of highly cited papers, framework papers, and route-defining works
- papers that visibly explain a phase transition or method formation

Do not rely only on the most cited 2-3 papers if they all come from one phase.

### Trajectory reconstruction rule

Reconstruct `研究轨迹` from source evidence rather than from chronology alone.

Primary signals for phase boundaries:

- change in recurring problem statement
- change in method combination
- change in application scene
- change in collaboration or institutional environment
- emergence of a framework paper, survey, or flagship concept

Secondary signals:

- title vocabulary shift
- venue shift
- project or lab role shift

Do not create phases only from job titles unless the work pattern also changes.

### Competitive landscape reconstruction rule

Infer `竞争格局` from publicly visible neighbor signals:

- repeated co-citation or conceptual adjacency
- same venue clusters
- same problem with different method
- same method transferred to different application
- explicit comparison or dialogue in review / framework papers

If direct competitor evidence is weak:

- say the landscape is provisional
- distinguish `direct neighbors` from `adjacent routes`

Do not overclaim saturation or gap statements from one or two abstracts alone.

Do not use an existing local `Research Map` as the base text to rewrite.
If local scholar notes exist, they may help with scholar discovery or source locating, but they are not the primary artifact to transform.

The target is:

- a standalone dossier that could be produced even without prior local profile files
- a structure strong enough for later `build-map`
- explicit evidence boundaries where source coverage is thin
- a reusable source artifact that makes later updates cheaper and more auditable

Use the original scholar-deconstruction prompt as the primary **instruction source**.
Use strong existing example artifacts as **gold examples for output behavior**, not as text to paraphrase.

This means:

- derive the required questions from the prompt
- derive section density and expected sharpness from the examples
- rebuild the target scholar from source evidence
- do not borrow unsupported judgments from example dossiers

When strong examples exist, distill from them:

- how much detail belongs in `基本信息`
- how phase analysis is paced in `研究轨迹`
- how sharp the causal and field-level judgment should be in `核心发现实质分析`
- how uncertainty is surfaced without flattening the whole dossier

Do not copy example prose patterns mechanically.
Copy the analytic standard, not the surface wording.

Avoid this failure mode:

- rely on prior local dossier prose
- inherit its judgments without rebuilding them from source evidence
- mistake old local synthesis for fresh from-scratch construction
- treat the prompt and examples as if they were optional inspiration instead of the output contract

### Source-pack workflow

For `full-profile`, prefer this execution order:

1. build `source-pack`
2. inspect coverage and identity confidence
3. reconstruct the scholar from the `source-pack`
4. write the dossier
5. mark evidence and coverage limits

Do not jump straight from a few URLs to final prose if the source base is still structurally thin.
The `source-pack` is the minimum intermediate artifact for from-scratch work.

Minimum P0 execution discipline:

1. stabilize scholar identity before broad writing
2. gather at least two source families when possible
3. select representative works across phases rather than by citations alone
4. make phase clues, method clues, and neighbor clues explicit in the pack
5. run a pre-drafting gate on the pack
6. downgrade or stop when the pack cannot support stable claims

### Prompt distillation rule

Before writing a `full-profile`, internally distill the canonical prompt into these required question groups:

1. `学术谱系`
   - who trained or shaped this scholar
   - what paradigm they entered
   - what unresolved tension shaped their entry point
2. `研究轨迹`
   - what phases exist
   - what changed across phases
   - what each phase made possible later
3. `方法论印章`
   - what signature combination formed
   - when it formed
   - what older limitation it solved
4. `核心发现实质分析`
   - what the real contribution was
   - why it mattered
   - what assumption it changed
   - what mistake persisted without it
5. `学者类型定位`
   - what role this scholar plays in the knowledge-production chain
   - what adjacent roles they are not
6. `竞争格局`
   - who the real neighbors are
   - what is saturated
   - what remains genuinely open

If the written dossier does not visibly answer these question groups, it has not actually distilled the prompt.

### Intellectual Genealogy requirements

In `full-profile`, present `Intellectual Genealogy` as **diagram first, explanation second**.

Use this order:

1. short framing sentence
2. a text-based genealogy diagram in a fenced code block
3. a short explanation of the most important links
4. extra context layers that explain how the scholar entered the field

Minimum contents of the genealogy diagram:

- upstream theories or traditions
- advisor / mentor / supervision chain when known
- institution / lab / training path when important
- key collaborators when they materially shaped the scholar's route
- downstream influence, students, or bridge role when visible

Default format:

```text
Upstream theory / tradition
    ↓
Advisor / supervision / training path
    ↓
Institution / lab / project environment
    ↓
Target scholar
    ├─ key collaborators
    ├─ adjacent influences
    └─ downstream students / bridge / impact
```

Rules:

- prefer a text-tree diagram by default
- use Mermaid only when the structure is too complex for a text tree
- if a relationship is uncertain, mark it explicitly instead of pretending certainty
- do not replace the diagram with prose only
- do not collapse all links into a single undifferentiated chain

Treat `Intellectual Genealogy` as a relation map, not just a lineage note.
When evidence supports it, explicitly distinguish these relation types:

- `advisor / mentor`
- `student / academic descendant`
- `core collaborator`
- `institutional or lab environment`
- `theoretical influence`
- `cross-field bridge`

Recommended order inside the section:

1. `师承 / 训练链`
2. `理论背景与学派来源`
3. `问题意识来源`
4. `合作网络与制度环境`
5. `这套关系如何塑造他的研究问题`

If the scholar is not well described by a pure advisor lineage, prefer a mixed genealogy map that shows:

- where the scholar was trained
- who they repeatedly built with
- which theory communities they inherited from
- which field boundary they helped bridge

Minimum acceptable content for `Intellectual Genealogy`:

- it must show at least two relation categories among:
  - `advisor / mentor`
  - `core collaborator`
  - `institutional or lab environment`
  - `theoretical influence`
  - `cross-field bridge`
- it must include extra context beyond the diagram, covering:
  - what the field's dominant paradigm looked like when the scholar entered
  - what unresolved tension, controversy, or gap shaped the scholar's entry point
  - where the scholar's initial problem awareness came from
- it must explicitly explain which links most shaped the scholar's research questions
- it must not collapse into a one-paragraph prose summary without a diagram

### 2. `build-map`

Use for multi-scholar positioning, clustering, benchmarking, transfer, and field-direction discussion.

This mode is downstream of `full-profile`. It is not allowed to invent missing scholar dossiers on the fly.
If needed, it may trigger `full-profile -> build-map` as a controlled two-stage workflow for missing scholars.

Outputs:

- `Scholar_Positioning__{focus}__{scope}.md`
- `Scholar_Positioning__{focus}__{scope}.canvas`

Do not revive `focused-profile`. Use only the two modes above.

## Roadmap Derivation

`roadmap` is not a primary execution mode.
Treat it as a downstream derived artifact built from existing `positioning` and `full-profile` artifacts.

Use it only when the user explicitly asks for route planning, next-step sequencing, or roadmap output.

For trigger conditions, evidence inheritance, output schema, and downgrade rules, read [references/roadmap-derivation.md](references/roadmap-derivation.md).
After drafting, run [references/roadmap-eval-checklist.md](references/roadmap-eval-checklist.md).

## Section Contract for `full-profile`

These six sections are the minimum stability core. Do not write them thinly.

### 1. `Intellectual Genealogy`

This section must answer:

- who trained the scholar, if known
- which collaborators repeatedly shaped the scholar's route
- which theory communities or traditions the scholar inherits from
- what field boundary the scholar bridges

Minimum structure:

- framing sentence
- genealogy diagram
- short explanation of the most important links
- explicit extra context on:
  - `理论背景`
  - `问题意识来源`
  - `合作网络 / 制度环境`

### 2. `Research Trajectory`

This section must answer:

- how the scholar's work divides into phases
- what changed between phases
- what each phase contributed to the later program

Minimum structure:

- at least 3 phases unless the corpus genuinely supports fewer
- each phase should include:
  - core problem
  - method or conceptual move
  - empirical support
  - why this phase matters for what comes later
- prefer the four-field rhythm from the original scholar-deconstruction prompt:
  - `核心问题`
  - `方法贡献`
  - `实证支撑`
  - `铺垫作用`
- when strong source material exists, keep representative works or milestone papers attached to the relevant phase instead of stripping them out
- when strong source material exists, prefer a short paragraph or table-like block per phase over ultra-short bullets
- preserve overlap, transition, or hinge-phase explanations when the scholar's trajectory is not cleanly segmented

For from-scratch profiles, `研究轨迹` is the main dossier spine.
Make it denser than the quick summary.

Preferred per-phase shape:

- phase name with approximate time range
- core problem
- method or conceptual contribution
- empirical support
- why this phase mattered for what came next
- representative works when support is sufficient

When coverage allows, include:

- which institution, project environment, or collaboration context shaped the phase
- whether the phase was a continuation, a pivot, or a bridge phase
- one-sentence overall trajectory judgment after the phases

Avoid this failure mode:

- phase names exist, but all analytic content has been flattened into 2-3 short bullets
- representative papers vanish even though the source search clearly surfaced them
- the reader cannot tell what changed from one phase to the next

Good test:

- a reader should be able to reconstruct the scholar's developmental logic without reading any other section
- if `研究轨迹` cannot stand alone as the main narrative backbone, it is still too thin

Do not reduce this section to a chronology of institutions or paper titles.
Do not reduce a rich phase narrative to two short bullets per phase.

### 3. `Method Stamp`

This section must answer:

- what the scholar's signature method combination is
- when that method stamp formed
- what earlier methods it outperformed or bypassed
- what its boundary conditions or limits are

Minimum structure:

- identify the method combination explicitly
- explain its formation by phase
- explain what problem it solved that previous methods could not
- name its limitations or boundary conditions
- when source material supports it, use explicit subparts such as:
  - `印章描述`
  - `形成过程`
  - `它解决了什么前人方法解决不了的问题`
  - `局限性与边界条件`

Do not reduce this section to a slogan without formation logic.

### 4. `Substantive Analysis of Core Findings`

This section must answer:

- what the scholar's real contribution was beyond the surface label
- why that contribution mattered in the field
- what default assumption it changed, if any
- why the scholar matters for the user's later positioning or benchmarking work

Minimum structure:

- at least 3 substantive findings or contribution clusters
- for each one, explain:
  - the real contribution
  - why it was distinctive
  - what it changed or enabled
- whenever possible, also answer:
  - why it was publishable or field-distinguishing
  - what default assumption it changed
  - what mistake the field would keep making without it
- prefer named finding clusters with short analytical prose over anonymous bullet lists

For from-scratch profiles, this section must do more than restate paper topics.
It should explain why the contribution mattered.

Preferred per-finding prompts:

- what was the real contribution beneath the surface label
- why was it distinctive enough to matter in the field
- why was it publishable or field-distinguishing
- what assumption, practice, or framing it changed
- what error, blind spot, or limitation the field would likely keep repeating without it

If the evidence is thinner, say so explicitly rather than inflating certainty.
But do not retreat into generic wording if the source base already supports a sharper judgment.

Avoid this failure mode:

- listing 3-4 topics as if topic labels were contributions
- describing findings as "important" without saying important in what sense
- skipping the "without this, the field would keep doing X wrong" question

Good test:

- after reading this section, the reader should understand not just what the scholar worked on, but why those contributions actually shifted the local field
- if the section could be swapped with another scholar's topic list and still sound plausible, it is too generic

Do not list findings without interpretation.

### 5. `Researcher Type`

This section must answer:

- what type of scholar this is in the knowledge-production chain
- why that classification fits better than adjacent types
- what this scholar is best used for in later positioning work

Minimum structure:

- explicit type label
- concise rationale
- at least 2 nearby-type contrasts
- one-line placement in the knowledge-production chain
- when source material supports it, preserve:
  - adjacent-type comparison
  - one-line positioning statement
  - why this type label is operationally useful for later map work

Do not stop at a label without explaining what that label helps the reader do.

### 6. `Competitive Landscape`

This section must answer:

- who the closest adjacent scholars or routes are
- where this scholar is distinctive relative to them
- which subdirections are saturated versus still open

Minimum structure:

- at least 3 adjacent scholars, teams, or routes unless the domain is unusually sparse
- explicit distinction between:
  - direct neighbors
  - alternative routes or competing framings
  - remaining gaps or open spaces
- when strong source material exists, also preserve:
  - which directions are already saturated
  - which gaps are genuinely open
  - where uncertainty remains about the gap claim
- if the source dossier has a stronger local structure such as `同方向主要学者/团队`, `已饱和的细分方向`, `尚存的真正空白`, preserve that stronger structure in Chinese-first form

Do not make this section optional in execution, even if evidence is thinner than ideal. Mark uncertainty when needed.

## Quick-read block for `full-profile`

At the top of a saved `full-profile`, before the main dossier sections, include:

```md
## 快速摘要

- 一句话定位：
- 核心问题：
- 最标志性方法：
- 最适合对标的层：
- 主要相邻学者：
- 主提醒：
```

This block exists to improve scanability.
It must not replace the full dossier body below.

## `map-eligible` gate

A `full-profile` is eligible for downstream `build-map` only when all of the following are present:

- complete `domain/topic/method/application` labels
- complete `Positioning Summary`
- `Intellectual Genealogy` with at least a training or mentor chain and a collaborator or influence layer
- `Competitive Landscape` with at least 3 adjacent scholars, teams, or routes when supported
- `Evidence Boundary` clear enough to support benchmark-role judgments

If these conditions are not met, the dossier may still be a draft `full-profile`, but it is not yet a stable map input.

## Router

Choose mode before writing anything. Do not blend modes unless the user explicitly asks for a pipeline.

### Route to `full-profile`

Route to `full-profile` when any of the following is true:

- the user asks to deconstruct one scholar
- the user asks for a scholar dossier, scholar archive, scholar profile, or `Research Map`
- the user names one scholar and does not explicitly ask to connect that scholar to others
- the user gives multiple scholar names but does not explicitly ask to connect, compare, cluster, or map them

In this route:

- produce only `{ScholarName}_Research_Map.md` files
- do not also generate a positioning doc
- do not also generate a canvas
- do not infer that map-building is wanted just because the profile may later be reused

### Route to `build-map`

Route to `build-map` only when the user explicitly asks to:

- connect multiple scholars
- compare multiple scholars
- build a positioning map
- cluster scholars
- identify benchmark roles across multiple scholars
- infer transfer paths or field structure across multiple scholars

In this route:

- reuse existing profiles first
- require reusable `full-profile` artifacts for all scholars in scope
- if any scholar lacks a reusable `full-profile`, build the missing `full-profile` artifacts first, then continue `build-map`
- do not create lightweight placeholder nodes as a substitute for missing scholar dossiers

### Pipeline route

Run `full-profile -> build-map` only when the user explicitly asks for both, or clearly asks for a multi-stage workflow such as:

- first build scholar profiles, then connect them
- generate profiles and then make a map
- do the full pipeline

If the user explicitly asks for `build-map` and some required scholars lack reusable dossiers, you may run an internal `full-profile -> build-map` pipeline for the missing scholars only.
Do not upgrade a standalone `full-profile` request into a pipeline.

## Execution Guardrail

Before producing any artifact, explicitly state the selected mode in one short block.

Use this shape:

```md
Mode selection
- Request type:
- Selected mode:
- Allowed outputs:
- Forbidden outputs:
```

Requirements:

- fill this block before writing the actual artifact
- if `Selected mode` is `full-profile`, `Forbidden outputs` must include any positioning doc and any canvas
- if `Selected mode` is `build-map`, `Allowed outputs` must name the positioning doc and canvas
- if the request is a pipeline, say so explicitly instead of silently switching modes
- do not keep this block inside the saved artifact body; it is an execution-time declaration, not part of the final dossier or positioning document

This guardrail exists to prevent silent router drift.

## Default Behavior

- If the user says `帮我拆解 X`, run `full-profile`.
- If the user says `帮我拆解 X`, do not generate `positioning` or `canvas` unless explicitly asked.
- If the user gives a scholar list without asking to connect them, build separate `full-profile` dossiers only.
- If the user gives a scholar list and explicitly asks for a map, reuse existing `full-profile` dossiers first.
- If the user gives a scholar list and explicitly asks for a map, build missing `full-profile` dossiers first, then continue the map.
- If map intent is unspecified, do not default to `build-map`.
- If the user gives no purpose for a single scholar, default to full-spectrum deconstruction.
- Prefer "先建档，再建图" over trying to infer dossiers from map needs.

## Build-Map Input Boundary

When the user provides a scholar list directly:

1. Normalize scholar identity and aliases.
2. Check for reusable local profiles first.
3. Reuse existing `full-profile` outputs whenever possible.
4. If any scholar is missing a reusable `full-profile`, build the missing dossiers first.
5. Build the map only after the required profiles exist.

Do not treat a scholar list by itself as an instruction to fully deconstruct everyone.
This rule applies when the user has not explicitly asked for `build-map` or a pipeline.

If the request is still fundamentally "tell me about each scholar one by one", stay in `full-profile` mode and do not switch to `build-map` just because multiple names appear.

## When to Stop at Weak Conclusions

Stay at weak conclusions when any of the following is true:

- the node is `C3 sparse abstract-only`
- the relationship depends mainly on indirect similarity
- the node is being used to justify a strong bridge, competitive claim, or field-direction claim without adequate support
- the map is being pushed toward strong benchmarking or roadmap conclusions without enough `E1/E2` evidence

In those cases:

- allow coarse clustering
- allow weak positioning
- allow labeled transfer hypotheses
- do not make strong influence claims
- do not make strong competitive claims
- do not let the node determine the core roadmap

## Evidence Protocol

Use these evidence levels:

- `E1 Confirmed fact`
- `E2 Strong synthesis`
- `E3 Plausible inference`
- `E4 Speculative idea`

Rules:

- Inference is allowed.
- Unlabeled inference is not allowed.
- Similarity is not influence unless explicitly supported.
- Roadmap hypotheses are not field facts.

## Coverage Protocol

Use these coverage levels:

- `C1 full-text-backed`
- `C2 multi-source abstract-backed`
- `C3 sparse abstract-only`

Rules:

- `C1` supports `full-profile` and stronger benchmark judgments.
- `C2` can support `full-profile` when the dossier clearly marks evidence limits.
- `C3` does not qualify as sufficient input for downstream `build-map`.

For lower-coverage `full-profile` dossiers, include:

```md
## Minimal Source Notes
- Coverage level:
- Key sources:
- Coverage limits:
- Claims avoided due to limited access:
```

## Node Schema

Every scholar profile used as map input must include:

- `domain_labels`
- `topic_labels`
- `method_labels`
- `application_labels`
- `researcher_type`
- Positioning Summary
- Evidence Boundary

Use this `Positioning Summary` template:

```md
## Positioning Summary

- Core problem:
- Signature method:
- Typical evidence:
- Main application scene:
- Upstream theories:
- Downstream tasks:
- Best benchmarking use:
- Closest adjacent scholars:
- Transferable value:
```

## Seed Taxonomy Rules

Treat the taxonomy as a seed layer, not a closed ontology.

For the current starter vocabulary, read [references/seed-taxonomy.md](references/seed-taxonomy.md).
For normalization and legacy-label handling, read [references/label-aliases.md](references/label-aliases.md).

- Keep the four buckets: `domain/topic/method/application`.
- Reuse existing labels when they fit cleanly.
- Add new labels only when needed.
- Use `kebab-case`.
- Assign each label to exactly one bucket.
- Promote new labels into the seed vocabulary only when they recur across multiple scholars.
- Do not force scholars into the current seed vocabulary if it distorts the field.

## Seed Layer Maintenance

Keep the seed layer **profile-driven** and **positioning-derived**.

For maintenance rules, promotion thresholds, and delayed aggregation discipline, read [references/taxonomy-update-rules.md](references/taxonomy-update-rules.md).

Source of truth:

- scholar profile labels are primary
- positioning outputs summarize recurring patterns from those labels

Maintain three parts:

1. **Derived vocabulary**: recurring labels from profiles
2. **Derived patterns**: recurring clusters, benchmark roles, and transfer routes from multiple positioning maps
3. **Manual guardrails**: alias handling, deprecated labels, and anti-duplication cleanup

Update rules:

- if a profile label changes, the seed layer may need refresh
- do not auto-rewrite cluster names or benchmark roles after a single profile edit
- promote labels only after recurrence across multiple profiles
- promote patterns only after recurrence across multiple maps
- prefer delayed aggregation over immediate auto-rewrite

## Search Protocol

Search openly, then tighten conclusions to the evidence quality.

When doing from-scratch public retrieval for `full-profile`, read [references/retrieval-protocol.md](references/retrieval-protocol.md) first.

Search priority:

1. official homepage, institution page, CV
2. Google Scholar, Semantic Scholar, DBLP, ResearchGate metadata
3. paper abstracts and accessible full texts
4. reviews, talks, interviews, project pages
5. local `Research Map` files and local scholar notes
6. blogs, news, and secondary summaries only as supplements

Do not let inaccessible full texts justify stronger claims than the available evidence supports.

If the user explicitly asks for a roadmap after `positioning`, do not improvise it from memory of the map.
Read [references/roadmap-derivation.md](references/roadmap-derivation.md) and inherit evidence limits from the upstream artifacts.

## Map Semantics

Use explicit edge meanings:

- `influence`
- `methodological-adjacency`
- `application-transfer`
- `benchmarking-link`

Confidence encoding:

- solid = `E1/E2`
- dashed = `E3`
- dotted = `E4`

Default to `methodological-adjacency` or `benchmarking-link` unless influence is directly supported.

## Build-Map Output Requirements

Every positioning map should help answer:

- how the scholars cluster
- how the scholars differ before they cluster
- what benchmark role each scholar plays
- how methods and routes align or diverge
- what shared progress exists
- what field-direction hypotheses are plausible
- what transfer or idea-reconstruction opportunities exist
- which adjacent scholars outside the current scope should be added next as new `full-profile` candidates
- which links are evidence-backed versus hypothesis-only

Required section order for `Scholar_Positioning__{focus}__{scope}.md`:

1. 快速摘要
2. 一句话总览
3. 关注点与范围
4. 关键差异与分工
5. 主簇
6. 关系速写
7. 关键桥梁
8. 当前局面
9. 对标定位
10. 方法与路线比较
11. 共同进展与方向假设
12. 迁移与 idea 重构
13. 补档建议
14. 附录：证据边界与备注

At the top, include:

```md
## 快速摘要

- Current core pattern:
- Best benchmark chain:
- Most important difference:
- Most useful transfer opportunity:
- Main caution:
```

And also include:

```md
## 当前局面

- Core clusters:
- Key bridge scholars:
- What is already strong:
- What is still missing:
- Whether roadmap discussion is justified:
```

Use this reading rhythm:

1. tell the reader the current pattern
2. give a one-line overview
3. state the key differences between scholars early
4. show the major clusters
5. show the relationship sketch
6. explain bridges and benchmark roles
7. move evidence boundaries to the appendix layer

For `关键差异与分工`, do not wait until later sections to reveal how the scholars differ.
This section should let a human reader immediately answer:

- this scholar is best for what
- this scholar is not best for what
- this scholar differs from the others mainly on which layer

Preferred compact format:

```md
## 关键差异与分工

- Scholar A:
  - 最适合：
  - 不最适合：
  - 相对 Scholar B / C 的关键差异：
```

## Canvas Constraints

Use canvas only for:

- clusters
- scholar roles
- bridge links
- route hypotheses

Do not overload the canvas with prose analysis.

## Naming Rules

Use these filenames:

- scholar profile: `{ScholarName}_Research_Map.md`
- positioning doc: `Scholar_Positioning__{focus}__{scope}.md`
- positioning canvas: `Scholar_Positioning__{focus}__{scope}.canvas`
- roadmap doc: `Scholar_Roadmap__{focus}__{scope}.md`

Avoid generic names such as:

- `Scholar_Relation_Map.md`
- `Scholar_Relation_Map.canvas`

## Guardrails

- Separate `field-positioning` from `benchmark-positioning`.
- Separate `positioning` from `roadmap`.
- Separate `profile construction` from `map construction`.
- Preserve evidence and coverage on every node and link.
- Use canonical scholar names and stable aliases.
- Allow bridge scholars to carry multiple labels when needed.
- Treat benchmark roles as layered, not absolute.
- Include `Claims intentionally not made`, `Not best for`, or `Alternative interpretations` when needed.
- Do not let missing profiles be silently replaced by weak placeholders.
- Treat `full-profile` as the required upstream artifact for any stable map.

## Portability

If the user changes goals or moves into a different field, keep:

- artifact model
- execution modes
- evidence protocol
- coverage protocol
- build-map output shape

Re-evaluate only:

- seed taxonomy
- calibration examples
- default cluster names
- common benchmark roles
- common transfer routes
