# Eval Rubric

这份 rubric 用来评估一次 skill 变更是否破坏了核心行为。

采用 3 档结果：

- `PASS`
- `WARN`
- `FAIL`

## 1. Mode Selection

检查：

- 单学者请求是否只输出 `full-profile`
- 多学者但未要求连接时，是否仍停在逐个建档
- `positioning` 是否只在明确 map 意图时触发
- `roadmap` 是否只在明确要求时触发

判定：

- `PASS` mode 选择完全正确
- `WARN` mode 正确，但有多余 pipeline 倾向
- `FAIL` mode 走错或 silently upgrade

## 2. Artifact Boundary

检查：

- `full-profile` 是否仍是重型 dossier
- `positioning` 是否仍是 multi-scholar structure，而不是 scholar summaries
- `roadmap` 是否仍是 derived artifact，而不是主产物

判定：

- `PASS` 边界清楚
- `WARN` 某一产物有压缩或混用倾向
- `FAIL` artifact 职责混淆

## 3. Evidence / Coverage

检查：

- `E1-E4` 是否可见
- `C1-C3` 或等价 coverage 降级是否可见
- 弱结论是否被标成弱结论

判定：

- `PASS` 边界清楚
- `WARN` 边界在，但不够前后一致
- `FAIL` 推断被写成事实

## 4. Profile Thickness

检查：

- `Research Trajectory` 是否保留 phase logic
- `Intellectual Genealogy` 是否不止一张图
- `Core Findings` 是否解释“为什么重要”
- `Competitive Landscape` 是否不是随手列 3 个名字

判定：

- `PASS` 保持 heavy dossier
- `WARN` 某一部分有轻量化倾向
- `FAIL` 压缩成薄摘要或 map-input brief

## 5. Positioning Usefulness

检查：

- 差异是否前置
- cluster / bridge / role split 是否清楚
- 是否能回答“我该拿谁对标什么”
- 是否区分 evidence-backed link 与 hypothesis-only link

判定：

- `PASS` 能直接支撑 benchmarking / transfer 判断
- `WARN` 图能看，但分析层仍偏弱
- `FAIL` 不能支撑实际 positioning 决策

## 6. Roadmap Drift

检查：

- 是否只有一条主路线
- 是否继承上游证据强度
- 是否说明缺哪些人/证据会改变路线判断
- 是否有停止线

判定：

- `PASS` roadmap 保持 operational
- `WARN` 有少量 field-forecast 漂移，但已降级
- `FAIL` roadmap 被写成未来趋势判断

## 7. Personalization Boundary

检查：

- 个性化是否仍停留在 overlay / preferences 层
- core protocol 是否没有被写成某个用户的习惯

判定：

- `PASS` 边界稳定
- `WARN` 有一些 presentation default 漏进 core
- `FAIL` core 被个体偏好污染

## 推荐结论写法

评估一个改动时，建议最后给出：

1. `PASS/WARN/FAIL`
2. 受影响的 case
3. 受影响的 contract
4. 是否建议合并
