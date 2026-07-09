# Domain Pack Contract

这份文档定义 `domain pack` 的最小约束，防止后续多人扩展时结构漂移。

## 目的

- 让不同方向的成员按同一框架扩展
- 避免每个领域包都长成不同风格
- 保持 domain layer 和 core layer 的边界清楚

## 一个 domain pack 最少应该说明什么

至少应包含：

1. 这个领域包适用于什么问题域
2. 它补充的是哪些领域特定内容
3. 它当前是否已经接管任何顶层入口
4. 它不应该改什么

## 适合放进 domain pack 的内容

- 领域标签 seed
- alias 规则
- recurring benchmark-role patterns
- 领域常见 route names
- 领域常见 scholar cluster names

## 不适合放进 domain pack 的内容

- artifact model
- router logic
- evidence protocol
- coverage protocol
- 全局命名规则

## 目录建议

每个领域目录至少应有：

- `README.md`

后续如果领域真的成熟，再逐步补：

- `seed-taxonomy.<domain>.md`
- `label-aliases.<domain>.md`
- `benchmark-patterns.<domain>.md`

但不要为了“看起来完整”先机械铺文件。

## 命名建议

领域目录名应：

- 使用 `kebab-case`
- 尽量是稳定问题域，不是临时项目名

例如：

- `automated-driving`
- `accident-safety`
- `energy-management`

## 当前兼容规则

如果某个领域包还只是占位或说明层，必须明确写出：

- 当前顶层 references 仍然生效
- 本领域包尚未完全接管对应协议部分

## 评审问题

新增一个 domain pack 时，至少问自己：

1. 这个目录是在补领域特异信息，还是在偷偷改 core？
2. 这个命名是长期稳定的，还是某次项目临时说法？
3. 这个 README 有没有写清楚当前接管范围和未接管范围？
