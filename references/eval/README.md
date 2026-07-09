# Eval

这个目录放 `scholar-positioning` 的最小回归评估资产。

目标不是做 benchmark leaderboard，而是防止后续维护时把关键行为悄悄改坏。

## 这套 eval 现在检查什么

当前只检查 3 类高价值行为：

1. 单学者 `full-profile`
2. 多学者 `positioning`
3. 从已有 `positioning` 派生 `roadmap`

## 这套 eval 不检查什么

目前不检查：

- scholar 事实是否绝对完整
- 检索结果是否每次都完全一样
- prose 风格是否字句一致

它主要检查：

- mode 有没有走错
- artifact 边界有没有漂
- 证据和 coverage 有没有被抹掉
- `roadmap` 有没有漂成 field forecast

## 使用顺序

先看：

1. [rubric.md](./rubric.md)
2. `cases/` 下与你要改动最接近的 case

## 当前 case

- [cases/full-profile-single-scholar.md](./cases/full-profile-single-scholar.md)
- [cases/positioning-three-scholars.md](./cases/positioning-three-scholars.md)
- [cases/roadmap-from-positioning.md](./cases/roadmap-from-positioning.md)

## 维护原则

- 先保住结构行为，再追求文风优化
- 优先看 fail mode，不看华丽表达
- gold case 用来检验协议是否漂移，不用来强行模板化 prose
