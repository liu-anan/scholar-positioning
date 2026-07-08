# Preferences Template

Fill this file the first time a new user wants a personalized overlay.

This file is for presentation defaults, not for core protocol changes.

## Onboarding Questions

### 1. Output language

- Default language:
- Keep technical terms in English when helpful?:
- Preferred heading style:

### 2. Readability target

- Primary audience:
  - human-first
  - balanced
  - AI-first
- Prefer quick summary at top?:
- Prefer key differences early in maps?:

### 3. Summary density

- Profile summary density:
  - light
  - medium
  - dense
- Positioning summary density:
  - light
  - medium
  - dense
- Roadmap route count preference:
  - one primary route
  - one primary + one secondary
  - broader exploration

### 4. Evidence-boundary presentation

- Put detailed evidence boundary:
  - early
  - balanced
  - late / appendix
- Show `Claims intentionally not made` by default?:
- Show `Minimal Source Notes` by default?:

### 5. Default task tendency

- Most common use:
  - full-profile
  - positioning
  - roadmap
- Prefer profile-first before map by default?:

### 6. Domain tendency

- Main domain pack:
- Secondary domain pack:

## Resulting Preferences

- language_defaults:
- readability_defaults:
- summary_density_defaults:
- evidence_boundary_presentation:
- default_task_tendency:
- domain_tendency:

## Guardrail

This file should not override:

- artifact model
- router logic
- evidence protocol
- coverage protocol
- domain taxonomy definitions
