# Seed Taxonomy

Use this reference when assigning the four label buckets:

- `domain_labels`
- `topic_labels`
- `method_labels`
- `application_labels`

This is a seed vocabulary, not a closed ontology.
It should be wide enough to support the current scholar corpus without forcing poor fits.

## How to use this seed

- prefer these labels first when they fit cleanly
- add a new label only when these would distort the scholar
- keep labels in `kebab-case`
- assign each label to exactly one bucket
- use 2-5 labels per bucket only when they genuinely help later map work

## Bucket intent

### `domain_labels`

Use for the scholar's larger field or knowledge community.

Examples:

- `human-factors`
- `automated-driving`
- `hri`
- `driver-behavior`

Do not use `domain_labels` for:

- specific research problems
- methods
- concrete application scenes

### `topic_labels`

Use for recurring research problems or thematic objects.

Examples:

- `driver-distraction`
- `shared-control`
- `situation-awareness`
- `meaningful-human-control`

Do not use `topic_labels` for:

- whole disciplines
- specific algorithms or instruments
- deployment scenes

### `method_labels`

Use for the scholar's recurring analytic, experimental, or design route.

Examples:

- `eye-tracking`
- `naturalistic-driving-analysis`
- `haptic-interface-design`
- `computational-modeling`

Do not use `method_labels` for:

- broad field names
- topic names
- application scenes

### `application_labels`

Use for concrete deployment scenes, operational domains, or use environments.

Examples:

- `driving`
- `teleoperation`
- `aviation`
- `workplace-automation`

For cross-application automation scholars:

- prefer the most concrete recurring scene first
- keep `automated-systems` only as a broad catch-all when a scholar repeatedly spans multiple automation scenes
- do not let `automated-systems` erase stable cross-scene distinctions such as maritime, UAV, or space operations when those distinctions matter for later positioning

Do not use `application_labels` for:

- disciplines
- abstract problem categories
- methods

## Current seed vocabulary

These labels are calibrated to the current scholar corpus across:

- transportation human factors
- automated driving
- human-robot interaction
- cognitive modeling
- cognitive / embodied AI

### Domain labels

- `human-factors`
- `automated-driving`
- `automation`
- `hri`
- `driver-behavior`
- `cognitive-modeling`
- `cognitive-engineering`
- `engineering-psychology`
- `neuroergonomics`
- `transport-safety`
- `traffic-psychology`
- `transport-engineering`
- `computer-vision`
- `robot-learning`
- `ai-alignment`
- `cognitive-ai`
- `social-robotics`
- `choice-modeling`

### Topic labels

- `attention`
- `workload`
- `human-ai-teaming`
- `supervisory-control`
- `driver-distraction`
- `driver-inattention`
- `glance-behavior`
- `situation-awareness`
- `automation-supervision`
- `automation-safety`
- `out-of-the-loop`
- `trust-in-automation`
- `takeover`
- `shared-control`
- `meaningful-human-control`
- `hazard-perception`
- `evidence-accumulation`
- `risk-field`
- `collision-risk`
- `reward-learning`
- `legible-motion`
- `commonsense-reasoning`

### Method labels

- `eye-tracking`
- `naturalistic-driving-analysis`
- `human-in-the-loop-experiments`
- `framework-synthesis`
- `haptic-interface-design`
- `control-modeling`
- `sa-measurement`
- `task-analysis`
- `behavioral-experiments`
- `driving-simulation`
- `simulation`
- `behavioral-modeling`
- `computational-modeling`
- `risk-modeling`
- `deep-learning`
- `machine-learning`
- `preference-learning`
- `discrete-choice-modeling`
- `safety-evaluation`
- `safety-validation`

### Application labels

- `driving`
- `adas`
- `automated-vehicles`
- `highly-automated-vehicles`
- `driving-safety`
- `traffic-safety`
- `robotics`
- `teleoperation`
- `aviation`
- `air-traffic-control`
- `uavs`
- `maritime-operations`
- `space-operations`
- `automated-systems`
- `autonomous-systems`
- `decision-support`
- `workplace-automation`
- `healthcare`
- `logistics`
- `manufacturing`

## Preferred granularity

Prefer labels that are:

- broad enough to recur
- specific enough to separate scholars in later positioning

Good:

- `shared-control`
- `eye-tracking`
- `automated-driving`
- `maritime-operations`
- `supervisory-control`

Too broad:

- `ai`
- `psychology`
- `modeling`

Too narrow:

- `brake-capacity-warning-response`
- `worker-robot-relationship-workshop`

## Bucket choice examples

- `shared-control`
  - bucket: `topic_labels`
  - not `domain_labels`

- `supervisory-control`
  - bucket: `topic_labels`
  - not `method_labels`

- `haptic-interface-design`
  - bucket: `method_labels`
  - not `topic_labels`

- `driving`
  - bucket: `application_labels`
  - not `domain_labels`

- `maritime-operations`
  - bucket: `application_labels`
  - not `domain_labels`

- `hri`
  - bucket: `domain_labels`
  - not `application_labels`

## Cross-application reminder

When a scholar repeatedly spans multiple deployment scenes:

- keep 1 broad label such as `automated-systems` only if it helps summarize the overall route
- also keep 1-3 concrete scene labels when they recur and matter analytically
- prefer `automated-systems` + concrete scenes over inventing a hybrid field label

Example:

- John D. Lee-like profile:
  - `automated-systems`
  - `highly-automated-vehicles`
  - `maritime-operations`
  - `uavs`

## Current-corpus reminder

This seed is intentionally shaped by the current corpus.
It should travel across nearby domains, but it is not the final universal vocabulary.
If the corpus shifts, keep the bucket logic and revise the seed.
