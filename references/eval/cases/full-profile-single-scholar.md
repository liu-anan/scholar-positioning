# Eval Case: Full-Profile Single Scholar

## 目标

验证单学者请求不会偷偷升级成 `positioning` 或 `roadmap`，并且 `full-profile` 保持 heavy dossier 厚度。

## 推荐输入

```text
使用 scholar-positioning，给 Donald Norman 建一个 full-profile。
```

## 必查点

1. mode 必须是 `full-profile`
2. 只允许输出 `{ScholarName}_Research_Map.md`
3. 不应生成 positioning doc / canvas / roadmap
4. `Research Trajectory` 必须有 phase logic
5. `Intellectual Genealogy` 不应只有图，没有解释
6. `Substantive Analysis of Core Findings` 不应退化成 topic list
7. `Evidence Boundary` 必须保留

## 常见失败模式

- 把档案压成摘要
- 顺手生成 map
- 用流畅 prose 掩盖薄检索
- 用 biography 代替 genealogy

## 建议判定

- 只要出现 pipeline 漂移，直接 `FAIL`
- 只要 dossier 厚度明显下降，至少 `WARN`
