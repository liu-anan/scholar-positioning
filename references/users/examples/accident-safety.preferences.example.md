# Example User Preferences: accident safety

This is a minimal example overlay for users mainly working on crash causation, safety assessment, accident analysis, and driver-risk related research.

## Resulting Preferences

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
  - put detailed evidence boundary: balanced
  - show `Claims intentionally not made` by default: yes
  - show `Minimal Source Notes` by default: yes
- default_task_tendency:
  - most common use: full-profile
  - prefer profile-first before map by default: yes
- domain_tendency:
  - main domain pack: accident-safety
  - secondary domain pack: automated-driving

## Notes

- Suitable when the user is more sensitive to over-inference and needs evidence limits to stay visible.
- Suitable when the user often cares about causation claims, safety mechanisms, and boundary conditions.
- This file should not override core protocol.
