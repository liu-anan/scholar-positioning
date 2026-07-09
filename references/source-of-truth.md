# Source of Truth

这份文档用来说明当前 `scholar-positioning` 的生效层次，避免维护时改错地方。

## 当前状态

这个项目目前处于**兼容式分层阶段**。

意思是：

- 顶层 `references/*.md` 仍然是当前真实生效入口
- `core / domains / users` 是正在收敛中的分层结构
- 分层目录已经开始承载说明和约束，但还没有完全替代顶层入口

## 当前真实生效入口

优先按下面理解：

### 1. 主入口

- `SKILL.md`

这是整个 skill 的总协议入口。

### 2. 当前真实协议参考入口

这些顶层文件当前仍然是主要参考源：

- `source-pack.md`
- `source-pack-template.md`
- `source-pack-eval-checklist.md`
- `retrieval-protocol.md`
- `seed-taxonomy.md`
- `label-aliases.md`
- `taxonomy-update-rules.md`
- `roadmap-derivation.md`
- `roadmap-eval-checklist.md`

如果出现“顶层文件”和分层说明不一致”的情况，当前应以：

1. `SKILL.md`
2. 顶层 `references/*.md`

为准。

## 分层目录当前的职责

### `core/`

职责：

- 标识稳定协议应该放哪里
- 给未来收敛提供清晰边界

当前状态：

- 主要是说明层
- 不是完整替代层

### `domains/`

职责：

- 承载领域扩展包
- 逐步沉淀 taxonomy / alias / recurring patterns

当前状态：

- 仍以说明和占位为主
- 不应假设 domain pack 已完全接管顶层 taxonomy

### `users/`

职责：

- 承载 presentation-layer personalization
- 不改 core protocol

当前状态：

- 已经比较接近稳定用途
- 但仍应受 user overlay contract 约束

## 维护时怎么判断该改哪里

### 改协议行为、artifact 边界、evidence / coverage

先看：

- `SKILL.md`
- 顶层 `references/*.md`

### 改用户个性化、首次配置、示例偏好

看：

- `references/users/`

### 改领域扩展说明或未来领域包

看：

- `references/domains/`

## 当前不建议做的事

- 不要只改 `core/README.md` 就以为协议已经变了
- 不要把 domain pack README 当作当前唯一 taxonomy 来源
- 不要把 user overlay 写成隐藏的协议改写层

## 后续理想状态

未来更理想的收敛方式是：

1. `SKILL.md` 保持总入口
2. `core/` 真正承载稳定协议正文
3. `domains/` 真正承载领域扩展资产
4. `users/` 只承载用户个性化
5. 顶层旧入口逐步退为兼容壳层或索引层

但当前还没完全走到那一步。
