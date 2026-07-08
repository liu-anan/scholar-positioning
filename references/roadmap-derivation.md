# Roadmap Derivation Protocol

Use this reference only when the user explicitly wants a `roadmap`.

`roadmap` is a derived artifact.
It is downstream of `positioning`, not a replacement for it.

After drafting a roadmap, run [roadmap-eval-checklist.md](roadmap-eval-checklist.md).

## What roadmap is

A `roadmap` is an action hypothesis built from existing scholar artifacts.

It should answer questions such as:

- which route is most worth studying next
- which benchmark chain is the most operationally useful
- which missing scholars or methods block stronger judgment
- which transfer path is worth testing first

It should not pretend to be:

- a field fact
- a forecast with independent evidence
- a substitute for `full-profile`
- a substitute for `positioning`

## Trigger condition

Derive a roadmap only when the user explicitly asks for one, for example:

- `接下来路线怎么走`
- `从这个 positioning 派生 roadmap`
- `给我一个研究路线图`
- `我下一步该对标谁 / 补谁 / 学哪条链`

Do not derive a roadmap automatically just because a positioning map exists.

## Required inputs

A roadmap requires all of the following:

1. at least one reusable `positioning` artifact
2. the upstream `full-profile` artifacts used by that positioning
3. visible evidence and coverage boundaries in those upstream artifacts

Do not derive roadmap directly from:

- a scholar-name list
- one thin profile
- an unfinished source-pack
- a map whose key links are mostly `E3/E4`

## Readiness gate

Roadmap is allowed only when all are true:

- the current positioning already answers:
  - key differences
  - benchmark roles
  - bridge scholars
  - at least one plausible transfer route
- the main route-defining links are at least `E2`
- the map is not relying on `C3 sparse abstract-only` nodes for its central chain

If any of these fail:

- keep the output at `positioning`
- or produce only a very weak roadmap sketch with explicit downgrade

## Evidence inheritance

Roadmap does not create stronger evidence than the upstream artifacts.

Inheritance rules:

- `E1/E2` positioning links may support roadmap prioritization
- `E3` links may support exploration ideas, not hard sequencing
- `E4` links may appear only in a clearly separated speculation block
- `C3` nodes must not define the main roadmap spine

Default rule:

- roadmap claims inherit the lower bound of the weakest critical upstream link

This means:

- if the key bridge in the chain is only `E3`, the roadmap cannot be written as if the chain were confirmed

## What a roadmap may conclude

Allowed:

- recommended benchmark chain
- recommended next scholars to profile
- recommended transfer experiment or idea-reconstruction direction
- recommended reading / benchmarking order
- explicit missing evidence that blocks stronger route judgment

Not allowed:

- claiming a single inevitable field future
- presenting speculative sequencing as settled strategy
- inventing missing scholar roles that the positioning did not support

## Output shape

Use this filename:

- `Scholar_Roadmap__{focus}__{scope}.md`

Required section order:

1. 快速摘要
2. 当前输入基础
3. 推荐主路线
4. 为什么是这条路线
5. 补档优先级
6. 方法迁移与 idea 重构机会
7. 不确定点与停止线
8. 附录：证据继承

At the top, include:

```md
## 快速摘要

- Current best route:
- Why this route:
- First benchmark target:
- First missing scholar or method:
- Main caution:
```

## Section intent

### 1. 当前输入基础

State clearly:

- which positioning artifact is being used
- which profiles are upstream
- whether the current corpus is narrow, medium, or broad

### 2. 推荐主路线

Give:

- one primary route only
- at most two secondary alternatives

Do not produce five equal-priority routes.

### 3. 为什么是这条路线

Explain:

- which benchmark chain supports it
- which bridge scholars make it coherent
- which competing routes were not chosen and why

### 4. 补档优先级

List only the scholars, methods, or evidence gaps that would most change the route judgment.

### 5. 方法迁移与 idea 重构机会

Keep this operational:

- what can be borrowed
- from whom
- into which layer
- with what evidence strength

### 6. 不确定点与停止线

Say explicitly when the roadmap should not be strengthened further.

Minimum prompts:

- which conclusion is still only `E3`
- what missing evidence would most likely flip the judgment
- what this roadmap intentionally does not claim

## Downgrade rules

If the corpus is still narrow:

- keep to one recommended route
- avoid future-tense field forecasting
- emphasize benchmark and transfer sequencing over "future of the field"

If the central chain includes a weak bridge:

- mark the chain provisional
- separate `可执行优先级` from `启发性方向`

If the evidence is too weak overall:

- do not produce roadmap
- return to `positioning` with explicit missing-input notes
