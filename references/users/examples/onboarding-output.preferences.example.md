# Example Onboarding Output: balanced

This file shows what a completed `preferences.md` can look like after the first-run onboarding prompt.

Purpose:

- show the target shape after onboarding
- reduce ambiguity when turning user answers into a saved preferences file
- provide a neutral starting point that is not locked to one specific domain

## Example Preferences

- language_defaults:
  - default language: Chinese
  - keep technical terms in English when helpful: yes
  - preferred heading style: Chinese-first
- readability_defaults:
  - primary audience: balanced
  - prefer quick summary at top: yes
  - prefer key differences early in maps: yes
- summary_density_defaults:
  - profile summary density: medium
  - positioning summary density: medium
  - roadmap route count preference: one primary route
- evidence_boundary_presentation:
  - put detailed evidence boundary: late / appendix
  - show `Claims intentionally not made` by default: when needed
  - show `Minimal Source Notes` by default: when coverage is thin
- default_task_tendency:
  - most common use: full-profile
  - prefer profile-first before map by default: yes
- domain_tendency:
  - main domain pack: unspecified
  - secondary domain pack: unspecified

## When to use this example

- when the user has completed onboarding but has not given strong domain-specific preferences yet
- when you need a neutral saved example for documentation
- when you want a baseline before later refinement

## Guardrail

This is a user-overlay example only.
It should not override:

- artifact model
- router logic
- evidence protocol
- coverage protocol
- domain taxonomy definitions
