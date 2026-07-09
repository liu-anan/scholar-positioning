# Source-Pack Contract

这份文档是 `source-pack workflow` 的 canonical contract。

它的目标不是重复 [../source-pack.md](../source-pack.md) 的所有解释，
而是把 `source-pack` 的最小结构职责和前后边界压缩成稳定协议。

当前约定：

- `source-pack.md` 仍保留为兼容入口
- 但 `source-pack workflow` 的结构边界优先以本文件理解

## 1. Role

`source-pack` 是：

- public retrieval 和 `full-profile` prose 之间的 staging layer
- 证据压缩层
- pre-drafting gate 的输入物

它不是：

- 最终 `profile`
- 轻量 biographical note
- 可以直接拿去做 `positioning` 的 map node

## 2. Required Visibility

一个可用 `source-pack` 至少要让下列内容可见：

- `identity confidence`
- `coverage level`
- `source families recovered`
- `representative works spread`
- `trajectory / phase clues`
- `genealogy / context clues`
- `method clues`
- `neighbor clues`
- `claims to avoid`

如果这些东西在 pack 里不可见，后续 profile 通常会靠补 prose 来掩盖检索不足。

## 3. Position in Workflow

固定顺序：

1. stabilize scholar identity
2. gather source families
3. build `source-pack`
4. run pre-drafting gate
5. draft `full-profile`
6. mark evidence / coverage boundary

禁止跳过：

- 直接从少量 URL 跳到完整 dossier
- 跳过 pre-drafting gate 直接写 profile

## 4. Minimum Structure

一个 `source-pack` 最少应覆盖：

1. identity block
2. source inventory
3. representative works
4. timeline / phase clues
5. genealogy / context clues
6. method clues
7. neighbor clues
8. coverage notes
9. claims to avoid

推荐直接结合：

- [../source-pack-template.md](../source-pack-template.md)
- [../source-pack-eval-checklist.md](../source-pack-eval-checklist.md)

## 5. Pass / Warn / Stop Contract

`source-pack` 只允许三种 gate 结果：

- `PASS`
- `WARN`
- `STOP`

### `PASS`

表示：

- 当前 evidence 足以支持 `full-profile`
- 但仍要在 `Evidence Boundary` 中保留 coverage limits

### `WARN`

表示：

- 允许写 `full-profile`
- 但某些 section 必须显式降级
- 特别是 `Genealogy`、`Competitive Landscape`、`Basic Information`

### `STOP`

表示：

- 不应继续写“稳定 heavy dossier”
- 应继续检索
- 或只输出明确降级的 partial draft

## 6. Full-Profile Handoff Contract

`source-pack` 通过 gate 后，至少要能支持：

- `Timeline Clues` -> `Research Trajectory`
- `Genealogy / Context Clues` -> `Intellectual Genealogy`
- `Method Clues` -> `Method Stamp`
- `Neighbor Clues` -> `Competitive Landscape`
- `Coverage Notes` -> `Evidence Boundary`

如果 handoff 关系不清楚，说明 `source-pack` 仍然不够稳定。

## 7. Non-Goals

`source-pack` 不负责：

- 最终中文/英文 prose 风格
- 用户级 summary placement
- benchmark chain 的完整 multi-scholar judgment
- roadmap 派生

这些职责分别属于：

- `user overlay`
- `full-profile`
- `positioning`
- `roadmap`

## 8. Review Questions

维护时至少问：

1. 这个改动是在提高 evidence staging 质量，还是只是在美化中间笔记？
2. 这个改动有没有让 pack 更像最终 profile，而不是证据层？
3. 这个改动会不会导致 `PASS/WARN/STOP` 边界变得更含糊？
