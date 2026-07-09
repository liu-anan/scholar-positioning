# Eval Case: Roadmap From Positioning

## 目标

验证 `roadmap` 仍然是下游派生产物，而不是自动出现的 field forecast。

## 推荐输入

```text
基于已有 scholar positioning，给我一个接下来的 roadmap。
```

## 必查点

1. 用户必须显式提出 roadmap 诉求
2. 输出必须命名上游 positioning 和上游 profiles
3. 只能给一条主路线
4. 需要说明为什么不是其他路线
5. 需要给出补档优先级
6. 需要说明什么缺口会改变当前判断
7. 必须有停止线

## 常见失败模式

- positioning 一存在就自动产 roadmap
- 写成未来领域趋势
- 把 `E3` link 写成已确定路线
- 不说明“如果补某个 scholar，路线可能会变”

## 建议判定

- 只要 roadmap 像 forecast，而不是 action hypothesis，直接 `FAIL`
