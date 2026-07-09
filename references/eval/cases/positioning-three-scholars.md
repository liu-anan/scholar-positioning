# Eval Case: Positioning Three Scholars

## 目标

验证 `positioning` 仍然是“先建档，再建图”，并且能真正回答 benchmark / bridge / difference 问题。

## 推荐输入

```text
使用 scholar-positioning，把 Trent Victor、Gustav Markkula、Natasha Merat 连起来做 positioning。
```

## 必查点

1. mode 必须是 `build-map`
2. 若缺 profile，应先补 `full-profile`
3. `key differences` 必须前置
4. 必须看得到 cluster / bridge / role split
5. 必须能回答“谁适合对标哪一层”
6. 不能把弱相似性直接写成 influence
7. 证据边界必须仍然可见

## 常见失败模式

- 直接拿 scholar list 开始建图
- 只讲相似，不讲差异
- 只讲关系，不讲 benchmark role
- 混淆 evidence-backed relation 和 hypothesis-only relation

## 建议判定

- 不能回答 role split，至少 `WARN`
- 若 map 没有 profile upstream，直接 `FAIL`
