# Example User Preferences: energy management

This is a minimal example overlay for users mainly working on energy management, optimization, control strategy, and system-level performance tradeoff questions.

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
  - profile summary density: light
  - positioning summary density: dense
  - roadmap route count preference: one primary + one secondary
- evidence_boundary_presentation:
  - put detailed evidence boundary: late / appendix
  - show `Claims intentionally not made` by default: when needed
  - show `Minimal Source Notes` by default: when coverage is thin
- default_task_tendency:
  - most common use: positioning
  - prefer profile-first before map by default: yes
- domain_tendency:
  - main domain pack: energy-management
  - secondary domain pack: automated-driving

## Notes

- Suitable when the user often compares routes by method transfer, optimization logic, and system-level tradeoffs.
- Suitable when the user wants summary-first reading but still needs dense map-level comparison.
- This file should not override core protocol.
