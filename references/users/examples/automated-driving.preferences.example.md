# Example User Preferences: automated driving

This is a minimal example overlay for users mainly working on automated driving, transport human factors, and human-in-the-loop control questions.

## Resulting Preferences

- language_defaults:
  - default language: Chinese
  - keep technical terms in English when helpful: yes
  - preferred heading style: Chinese-first
- readability_defaults:
  - primary audience: human-first
  - prefer quick summary at top: yes
  - prefer key differences early in maps: yes
- summary_density_defaults:
  - profile summary density: medium
  - positioning summary density: dense
  - roadmap route count preference: one primary + one secondary
- evidence_boundary_presentation:
  - put detailed evidence boundary: late / appendix
  - show `Claims intentionally not made` by default: yes
  - show `Minimal Source Notes` by default: when coverage is thin
- default_task_tendency:
  - most common use: positioning
  - prefer profile-first before map by default: yes
- domain_tendency:
  - main domain pack: automated-driving
  - secondary domain pack: accident-safety

## Notes

- Suitable when the user often compares scholars by control layer, supervision layer, trust / safety layer, or transfer route.
- Suitable when the user wants maps to surface benchmark roles and bridge scholars early.
- This file should not override core protocol.
