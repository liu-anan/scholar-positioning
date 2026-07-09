# Artifact Contract

这份文档是 `scholar-positioning` 当前最重要的结构协议收敛点之一。

它把最容易漂移的内容压缩成短 contract：

- artifact 边界
- mode 选择
- 上下游依赖
- 最小完成标准
- 何时允许进入下一阶段

如果 `SKILL.md`、README、示例文档之间出现理解分歧，当前应优先以：

1. `SKILL.md`
2. 本文件

为准。

## 1. Artifact Types

只允许这三类主产物：

1. `profile`
   - 单学者重型档案
   - 回答：这个学者是谁、怎么长出来、适合拿来对标什么
2. `positioning`
   - 多学者定位结构
   - 回答：这些学者彼此如何分工、分簇、搭桥、形成 benchmark chain
3. `roadmap`
   - 从已有 artifact 派生出的行动假设
   - 回答：下一步优先补谁、学哪条链、迁移哪类方法

禁止把：

- `profile` 写成轻量摘要
- `positioning` 写成 scholar list summary
- `roadmap` 写成 field forecast

## 2. Upstream Dependency

依赖关系固定如下：

```text
source-pack -> full-profile -> positioning -> roadmap
```

规则：

- `source-pack` 只是 `full-profile` 的证据 staging layer
- `positioning` 只能消费 `full-profile`
- `roadmap` 只能消费 `positioning` 及其上游 `full-profile`
- 不允许 `map -> profile` 反推
- 不允许 `roadmap -> positioning` 反推

## 3. Mode Contract

### `full-profile`

触发条件：

- 单学者拆解
- scholar dossier / archive / Research Map
- 多个名字但没有明确要求连起来看

允许输出：

- `{ScholarName}_Research_Map.md`

禁止输出：

- positioning doc
- canvas
- roadmap

### `build-map`

触发条件：

- 用户明确要求 connect / compare / cluster / map / positioning

允许输出：

- `Scholar_Positioning__{focus}__{scope}.md`
- `Scholar_Positioning__{focus}__{scope}.canvas`

前提：

- scope 内所有 scholar 都必须有可复用 `full-profile`
- 缺档时先补 `full-profile`

### `roadmap`

触发条件：

- 用户明确要求 roadmap / next-step route / benchmark sequence

允许输出：

- `Scholar_Roadmap__{focus}__{scope}.md`

前提：

- 至少一个稳定 `positioning`
- 其关键链路不是由 `C3` / `E3` 充当主 spine

## 4. Full-Profile Minimum Contract

`full-profile` 最少必须包含：

- `Basic Information`
- `Intellectual Genealogy`
- `Research Trajectory`
- `Method Stamp`
- `Substantive Analysis of Core Findings`
- `Researcher Type`
- `Competitive Landscape`
- `Positioning Summary`
- `Evidence Boundary`

它必须能够回答：

1. scholar 的核心问题是什么
2. scholar 的学术路径如何形成
3. scholar 的方法印章是什么
4. 研究轨迹如何分 phase 演化
5. 最实质的贡献是什么
6. 与相邻 scholar 的本质差异是什么
7. 周围竞争格局如何
8. 在后续 positioning 中最适合被拿来做什么

如果不能稳定回答以上 8 个问题，就不是稳定 `full-profile`。

## 5. Map-Eligible Gate

只有满足以下条件的 `full-profile` 才是稳定 map 输入：

- 有完整 `domain/topic/method/application` labels
- 有完整 `Positioning Summary`
- `Intellectual Genealogy` 至少覆盖训练链/影响层中的两类关系
- `Competitive Landscape` 在证据允许时给出至少 3 个相邻 scholar / route
- `Evidence Boundary` 足够支持 benchmark-role 判断

否则：

- 它可以是 draft `full-profile`
- 但不能被当作稳定 `build-map` 节点

## 6. Positioning Minimum Contract

`positioning` 最少必须回答：

1. 这些 scholar 如何分簇
2. 这些 scholar 在分簇前最关键的差异是什么
3. 每个 scholar 最适合对标哪一层
4. 谁是桥梁 scholar
5. 哪些 link 是 evidence-backed
6. 哪些 link 只是 transfer hypothesis

最少应包含这些 section function：

1. quick summary 或等价 scan layer
2. one-line overview
3. scope and focus
4. key differences and role split
5. main clusters
6. relationship sketch
7. key bridges
8. benchmark positioning
9. method and route comparison
10. shared progress and direction hypotheses
11. transfer and idea reconstruction
12. suggested profiles to add
13. evidence boundary and notes

## 7. Roadmap Minimum Contract

`roadmap` 不是默认产物。

只有在以下条件同时成立时才允许：

- 用户显式要求
- 已有稳定 `positioning`
- 上游关键 route-defining links 至少达到 `E2`
- 中心链路不依赖 `C3` node

最少必须包含：

1. 当前输入基础
2. 推荐主路线
3. 为什么是这条路线
4. 补档优先级
5. 方法迁移与 idea 重构机会
6. 不确定点与停止线
7. 证据继承

## 8. Naming Contract

文件名固定使用：

- `profile`: `{ScholarName}_Research_Map.md`
- `positioning`: `Scholar_Positioning__{focus}__{scope}.md`
- `positioning canvas`: `Scholar_Positioning__{focus}__{scope}.canvas`
- `roadmap`: `Scholar_Roadmap__{focus}__{scope}.md`

避免继续产出：

- `Scholar_Relation_Map.md`
- `Scholar_Relation_Map.canvas`

## 9. Drift Checks

评审一个改动时，至少问：

1. 这个改动是在改 artifact contract，还是只改呈现偏好？
2. 这个改动有没有把 `profile -> positioning -> roadmap` 的依赖顺序打乱？
3. 这个改动有没有降低 `full-profile` 的档案厚度？
4. 这个改动有没有让 roadmap 漂成 field forecast？
