# Taxonomy Update Rules

Use this reference when the seed taxonomy needs maintenance.

The goal is to keep the taxonomy:

- profile-driven
- positioning-derived
- stable enough for map reuse
- flexible enough for corpus growth

## Source of truth

Priority order:

1. current scholar profile labels
2. repeated patterns in positioning outputs
3. manual cleanup rules

Do not let one map or one profile rewrite the whole seed layer automatically.

## What can change

Three things evolve at different speeds:

### 1. Derived vocabulary

These are recurring labels from individual profiles.

Examples:

- `human-factors`
- `shared-control`
- `eye-tracking`

These may change relatively often.

### 2. Derived patterns

These are repeated map-level structures.

Examples:

- theory -> behavior evidence -> interaction
- construct -> measurement -> design bridge

These should change slowly.

### 3. Manual guardrails

These are alias tables, deprecated labels, and anti-duplication cleanup.

These should change only when confusion is already visible.

## Promotion rules

Promote a new label into `seed-taxonomy.md` only when one of these is true:

- it recurs across at least 2 scholars
- it is required to represent a major scholar cleanly and no current seed label fits
- it is likely to recur because it names a recognizable method or topic family in the corpus

Do not promote a label just because:

- it sounds precise
- it appears in one paper title
- it is temporarily useful for one scholar only

## Merge rules

Merge labels when:

- they name the same idea with casing or formatting differences
- one label is a more stable canonical form
- the distinction does not matter for later positioning

Examples:

- `driver distraction` and `driver-distraction`
- `Human factors` and `human-factors`

Do not merge labels when the distinction is operationally useful.

Example:

- `automation-supervision` and `automation-safety`

## Split rules

Split a label only when the unsplit label is harming later map work.

Good reason to split:

- one label is hiding two benchmark roles
- a field label is being used to mean both a topic and a method

Bad reason to split:

- stylistic preference
- one-off desire for finer granularity

## Delayed aggregation rule

When one profile changes:

- update the profile labels
- consider whether the alias table needs a note
- do not immediately rename map-level patterns

When multiple profiles converge on the same new label:

- update the seed vocabulary
- then consider whether recurring map language should also change

This delay prevents taxonomy churn.

## Bucket discipline

When adding or changing a label:

1. decide the bucket first
2. decide whether the label already exists in that bucket
3. normalize through `label-aliases.md`
4. only then add or promote a new label

Never let the same canonical label live in two buckets.

## Legacy migration rule

When ingesting older artifacts with legacy metadata:

- treat legacy labels as locators
- normalize before writing new saved artifacts
- do not rewrite the original source file unless the task explicitly asks for migration

This preserves upstream artifacts while keeping the skill output stable.

## Review cadence

Review the seed layer when one of these happens:

- 5 or more new profiles were added
- a new field cluster appears
- positioning maps repeatedly invent similar custom labels
- alias confusion shows up in outputs

Do not review after every single profile unless something broke.

## What not to auto-update

Do not auto-rewrite these after one profile edit:

- cluster names
- benchmark-role phrases
- transfer-route phrases
- roadmap language

These are map-level patterns, not raw labels.

## Practical maintenance workflow

1. inspect new profile labels
2. normalize with `label-aliases.md`
3. check whether the seed already covers them
4. if not, hold as provisional unless promotion threshold is met
5. update `seed-taxonomy.md` only after recurrence or clear corpus need
6. update derived map language only after recurrence across multiple maps

## Failure modes

- promoting every interesting phrase into the seed
- mixing buckets because a label sounds useful
- letting one scholar redefine the map language
- rewriting cluster names too quickly
- forcing the seed vocabulary onto a scholar when it distorts the scholar

If one of these happens, slow down and keep the change provisional.
