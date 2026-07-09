# User Overlay Contract

这份文档定义 `user overlay` 的最小约束。

## 目的

- 允许个性化
- 防止个性化越界改 core protocol
- 保持不同用户 overlay 之间可维护

## user overlay 允许改什么

允许改的应集中在 presentation layer：

- 默认语言
- 标题语言偏好
- human-first / balanced / AI-first 阅读倾向
- 摘要前置或后置偏好
- 关键差异是否前置
- 证据边界展示位置
- 默认领域倾向

## user overlay 不允许改什么

不允许改：

- artifact model
- router logic
- evidence protocol
- coverage protocol
- taxonomy definitions
- profile -> map dependency
- roadmap 的默认产物地位

## 建议的一级字段

当前建议只使用这些一级字段：

- `language_defaults`
- `readability_defaults`
- `summary_density_defaults`
- `evidence_boundary_presentation`
- `default_task_tendency`
- `domain_tendency`

如果要新增一级字段，应先判断：

- 这是用户风格问题，还是协议问题？

只有前者才适合进入 overlay。

## 文件来源建议

用户 overlay 推荐来源：

1. `onboarding-prompt.md`
2. `onboarding-mapping.zh-CN.md`
3. `template/preferences.template.md`

不要直接凭感觉手写一堆额外字段。

## 命名和位置

推荐位置：

```text
references/users/<user-name>/preferences.md
```

推荐内容风格：

- 尽量简短
- 尽量结构稳定
- 尽量避免自由散文式描述

## 评审问题

修改一个 user overlay 前，至少问自己：

1. 这是在改展示偏好，还是在改协议行为？
2. 这个字段会不会影响其他用户的可迁移性？
3. 这项个性化是不是应该通过 README / example 表达，而不是进入 overlay？
