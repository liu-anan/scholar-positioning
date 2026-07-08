# Label Aliases

Use this reference to normalize:

- legacy metadata labels
- human-readable phrases
- near-duplicate labels
- deprecated labels

The output labels written into new scholar profiles should stay in `kebab-case`.

## Normalization rules

- normalize case
- replace spaces with hyphens
- remove punctuation unless needed for meaning
- prefer the canonical label listed here over legacy variants
- keep the label in the correct bucket even if the source mixed buckets

## Legacy metadata

Some existing note systems use:

- `scholar_domain`
- `research_focus`
- `method_labels`
- `application_labels`

For new `scholar-positioning` outputs:

- map `scholar_domain` into `domain_labels`
- map `research_focus` into `topic_labels`
- keep `method_labels` and `application_labels` but normalize values

Do not copy legacy value casing or spacing into new saved artifacts.

## Canonical aliases by bucket

### Domain aliases

- `Human factors` -> `human-factors`
- `Automated driving` -> `automated-driving`
- `Automation` -> `automation`
- `Human-robot interaction` -> `hri`
- `HRI` -> `hri`
- `Driver behavior` -> `driver-behavior`
- `Cognitive modeling` -> `cognitive-modeling`
- `Cognitive engineering` -> `cognitive-engineering`
- `Engineering psychology` -> `engineering-psychology`
- `Neuroergonomics` -> `neuroergonomics`
- `Transportation safety` -> `transport-safety`
- `Traffic psychology` -> `traffic-psychology`
- `Transport human factors` -> `human-factors`
- `Transport engineering` -> `transport-engineering`
- `Computer vision` -> `computer-vision`
- `Robot learning` -> `robot-learning`
- `AI alignment` -> `ai-alignment`
- `Cognitive AI` -> `cognitive-ai`
- `Social robotics` -> `social-robotics`
- `Choice modeling` -> `choice-modeling`

### Topic aliases

- `human-AI teaming` -> `human-ai-teaming`
- `human ai teaming` -> `human-ai-teaming`
- `supervisory control` -> `supervisory-control`
- `human supervisory control` -> `supervisory-control`
- `driver distraction` -> `driver-distraction`
- `driver inattention` -> `driver-inattention`
- `glance behavior` -> `glance-behavior`
- `situation awareness` -> `situation-awareness`
- `automation supervision` -> `automation-supervision`
- `automation safety` -> `automation-safety`
- `trust` -> `trust-in-automation` when the context is human-automation trust
- `trust in automation` -> `trust-in-automation`
- `takeover behavior` -> `takeover`
- `shared control` -> `shared-control`
- `meaningful human control` -> `meaningful-human-control`
- `hazard perception` -> `hazard-perception`
- `evidence accumulation` -> `evidence-accumulation`
- `collision risk` -> `collision-risk`
- `reward learning` -> `reward-learning`
- `legible motion` -> `legible-motion`
- `commonsense reasoning` -> `commonsense-reasoning`

### Method aliases

- `human factors theory` -> `framework-synthesis` when the label is being used for synthesis and design-guidance rather than a domain
- `system design` -> `framework-synthesis` when the label is being used as a recurrent design-guidance method
- `eye tracking` -> `eye-tracking`
- `naturalistic driving analysis` -> `naturalistic-driving-analysis`
- `haptics` -> `haptic-interface-design` when the label is being used as a design route rather than a topic
- `behavioral experiments` -> `behavioral-experiments`
- `driving simulation` -> `driving-simulation`
- `behavioral modeling` -> `behavioral-modeling`
- `computational modeling` -> `computational-modeling`
- `risk modeling` -> `risk-modeling`
- `deep learning` -> `deep-learning`
- `machine learning` -> `machine-learning`
- `preference learning` -> `preference-learning`
- `discrete choice modeling` -> `discrete-choice-modeling`
- `safety evaluation` -> `safety-evaluation`
- `safety validation` -> `safety-validation`

### Application aliases

- `driving safety` -> `driving-safety`
- `traffic safety` -> `traffic-safety`
- `ADAS` -> `adas`
- `automated vehicles` -> `automated-vehicles`
- `highly automated vehicles` -> `highly-automated-vehicles`
- `highly-automated driving` -> `highly-automated-vehicles` when the context is deployment scene rather than field
- `autonomous systems` -> `autonomous-systems`
- `maritime automation` -> `maritime-operations`
- `maritime operations` -> `maritime-operations`
- `shipping` -> `maritime-operations` when the context is automation or operational control
- `uav` -> `uavs`
- `uavs` -> `uavs`
- `unmanned aerial vehicles` -> `uavs`
- `drones` -> `uavs` when the context is operational deployment rather than consumer devices
- `deep space exploration` -> `space-operations`
- `space exploration` -> `space-operations`
- `space operations` -> `space-operations`
- `air traffic control` -> `air-traffic-control`
- `workforce` -> `workplace-automation` when the context is human-robot work systems

## Deprecated labels

Use these only as migration clues, not as preferred outputs:

- `human-automation-interaction`
  - preferred replacement: choose `automation-supervision` as topic or `human-factors` / `automation` as domain depending context
- `out-of-the-loop-performance`
  - preferred replacement: `out-of-the-loop`
- `automotive-human-factors`
  - preferred replacement: usually `human-factors` + `driving` or `automated-driving`
- `applied-cognition`
  - preferred replacement: choose `human-factors`, `cognitive-engineering`, or `driver-behavior` depending context
- `transport-human-factors`
  - preferred replacement: usually `human-factors` plus transport application labels

## Context-dependent cautions

Some legacy labels are ambiguous and should not be normalized blindly:

- `haptics`
  - as a topic: keep `haptics`
  - as a method route: use `haptic-interface-design`

- `automation`
  - as a field: `automation` in `domain_labels`
  - as a topic: prefer something more specific such as `automation-supervision` or `automation-safety`

- `simulation`
  - as a method: `simulation`
  - do not use as an application label

- `automation`
  - as a broad deployment scene across many contexts: `automated-systems`
  - as a field: `automation` in `domain_labels`
  - do not collapse concrete recurring scenes into `automated-systems` if maritime / UAV / vehicle distinctions matter

- `driver behavior modeling`
  - choose `driver-behavior` for domain
  - choose `behavioral-modeling` or `computational-modeling` for method

## Practical rule

When a legacy label can map to multiple canonical labels:

1. decide the bucket first
2. choose the canonical label second
3. avoid inventing a hybrid label unless the existing seed clearly fails
