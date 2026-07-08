# scholar-positioning

这是一个给 Codex/skills 体系使用的研究型 skill。  
它的作用不是简单“总结学者”，而是更系统地帮你做三类事情：

1. 给单个学者建立带证据边界的科研档案
2. 把多个学者连起来做定位图（positioning）
3. 在定位图基础上，谨慎派生 roadmap

这个 skill 适合下面这类场景：

- 你想系统拆解一个学者，而不是只看几篇代表作
- 你想比较几个学者的方法路线、研究簇、桥梁关系
- 你想知道“我该拿谁对标什么”
- 你想做方法迁移、idea 重构、领域定位，但又不希望 AI 把推断说得像事实

它的核心原则只有一句：

> 允许推断，但不允许不标注的推断。

---

## 一、如果你完全没用过 skills，先看这里

### 1. `skill` 是什么

可以把 `skill` 理解成一套可复用的“任务协议”。

它不只是一个 prompt，也不只是一个模板。它通常会包含：

- 主说明文件：告诉 AI 这类任务应该怎么做
- 参考规则：告诉 AI 应该遵守哪些边界
- 模板或脚手架：帮助 AI 输出更稳定的结构

这个仓库就是这样一个 skill 包。  
安装后，Codex 在需要时可以读取这里的规则，用它来生成更稳定的学者档案和定位图。

### 2. 这个仓库不是做什么的

它不是：

- 学术搜索引擎
- 私有知识库
- 自动保证“所有学者都能被完整重建”的魔法工具
- 一个只会产出漂亮图、不关心证据质量的可视化模板

它更像是一个“研究分析协议”：

- 规定先建档，再建图
- 规定证据强弱怎么标
- 规定什么时候只能弱结论
- 规定 roadmap 只能是派生产物，不能冒充事实预测

---

## 二、这个 skill 到底能产出什么

这个 skill 只处理三类 artifact：

### 1. `profile`

单学者档案。回答的是：

> 这个学者是谁，他的研究是怎么长出来的，他的方法印章是什么，他在领域里处在什么位置？

典型输出文件名：

- `{ScholarName}_Research_Map.md`

### 2. `positioning`

多学者定位图。回答的是：

> 这些学者彼此怎么分工、怎么分簇、谁是桥梁、谁适合对标什么？

典型输出文件名：

- `Scholar_Positioning__{focus}__{scope}.md`
- `Scholar_Positioning__{focus}__{scope}.canvas`

### 3. `roadmap`

从定位图派生出来的下一步行动路线。回答的是：

> 如果我想对标、迁移、补人、补方法，下一步应该怎么走？

典型输出文件名：

- `Scholar_Roadmap__{focus}__{scope}.md`

### 很重要的边界

三者不是一回事：

- `profile` 不是 `positioning`
- `positioning` 不是 `roadmap`
- `roadmap` 不是领域事实预测

这个 skill 的设计原则是：

- 先建 `profile`
- 再做 `positioning`
- 最后视情况派生 `roadmap`

---

## 三、这个 skill 解决什么常见问题

很多“学者分析 prompt”会犯下面几种错误：

### 1. 太早压缩

明明应该做一个厚档案，结果只生成一页摘要。  
最后你知道“这个人很厉害”，但不知道他到底厉害在哪一层。

### 2. 建档和建图混在一起

一上来就把几个人连起来讲，但每个人本身都没建清楚。  
最后图是有了，节点却很虚。

### 3. 弱证据硬推断

只看几篇摘要，就说谁影响了谁、谁代表未来路线、谁是领域中心。  
这很容易误导判断。

### 4. roadmap 偷偷变成“领域预测”

明明只是基于当前样本做的工作假设，最后却写得像未来必然趋势。

这个 skill 的协议，就是专门拿来压这些风险的。

---

## 四、仓库结构说明

先看最重要的几个文件：

- [SKILL.md](./SKILL.md)  
  主协议。核心规则都在这里。

- [agents/openai.yaml](./agents/openai.yaml)  
  给 agent/UI 用的基础说明。

- [references/source-pack.md](./references/source-pack.md)  
  建 `full-profile` 前的中间材料协议。

- [references/retrieval-protocol.md](./references/retrieval-protocol.md)  
  公开资料检索顺序、停手条件、证据边界。

- [references/seed-taxonomy.md](./references/seed-taxonomy.md)  
  初始标签体系。

- [references/roadmap-derivation.md](./references/roadmap-derivation.md)  
  roadmap 的派生规则。

### 当前的分层架构

这个仓库正在往三层结构收敛：

#### 1. `core`

放稳定协议，不应轻易被个人习惯改写。

包括：

- artifact 模型
- evidence / coverage 协议
- source-pack 工作流
- roadmap 工作流

入口说明：

- [references/core/README.md](./references/core/README.md)

#### 2. `domains`

放领域相关的内容。

例如：

- taxonomy seed
- alias 规则
- 某个领域反复出现的 benchmark pattern

当前仓库里已经有一个示例领域包：

- [references/domains/automated-driving/README.md](./references/domains/automated-driving/README.md)

#### 3. `users`

放用户层个性化配置，不改核心协议，只改呈现偏好。

包括这类内容：

- 默认中文还是英文
- 更偏人读还是更偏机器消费
- 摘要要不要放前面
- 证据边界要不要后置

相关文件：

- [references/users/onboarding.md](./references/users/onboarding.md)
- [references/users/template/README.md](./references/users/template/README.md)
- [references/users/template/preferences.template.md](./references/users/template/preferences.template.md)

当前仓库里还放了一个真实示例：

- [references/users/liutingnan/README.md](./references/users/liutingnan/README.md)
- [references/users/liutingnan/preferences.md](./references/users/liutingnan/preferences.md)

这个示例只是演示“怎么做 overlay”，不是要求所有人都照抄。

---

## 五、安装方法

这里先按“你是第一次用 skills”来写。

### 方案 A：手动安装到本地 skills 目录

通常你可以把这个仓库放到本地的 skills 目录里，例如：

```bash
git clone https://github.com/liu-anan/scholar-positioning.git ~/.codex/skills/scholar-positioning
```

如果你的环境不是用 `~/.codex/skills`，就放到你自己当前 agent/skills 体系要求的位置。

安装完成后，关键是这个文件要存在：

```bash
~/.codex/skills/scholar-positioning/SKILL.md
```

### 方案 B：先下载 ZIP，再手动放进去

如果你不想用 git，也可以：

1. 在 GitHub 下载这个仓库
2. 解压
3. 把整个目录放到你的 skills 目录
4. 确认 `SKILL.md` 在正确位置

### 安装后怎么验证

至少做两件事：

1. 确认目录结构完整
2. 确认 agent 能读到 `SKILL.md`

最小结构应该至少包含：

```text
scholar-positioning/
├── SKILL.md
├── README.md
├── agents/
└── references/
```

---

## 六、5 分钟快速开始

如果你不想先通读完整协议，可以直接按下面做一遍。

### 第 1 步：安装

```bash
git clone https://github.com/liu-anan/scholar-positioning.git ~/.codex/skills/scholar-positioning
```

### 第 2 步：确认文件在

```bash
ls ~/.codex/skills/scholar-positioning
```

你至少应该能看到：

- `SKILL.md`
- `README.md`
- `references/`

### 第 3 步：先不要改协议，只做最小 personalize

如果你是第一次用，先复制模板，再按自己的阅读习惯改最少几项：

```text
references/users/template/preferences.template.md
```

如果你希望 AI 直接带你完成第一次配置，优先用这份首次启动问答：

- [首次启动问答 prompt](./references/users/onboarding-prompt.md)
- [onboarding 说明](./references/users/onboarding.md)

如果你想直接参考现成示例，看这里：

- [自动驾驶示例](./references/users/examples/automated-driving.preferences.example.md)
- [事故安全示例](./references/users/examples/accident-safety.preferences.example.md)
- [能量管理示例](./references/users/examples/energy-management.preferences.example.md)

### 第 4 步：先跑一个单学者请求

先用 `full-profile` 验证这套 skill 是否符合你的预期：

```text
使用 scholar-positioning，给 Donald Norman 建一个 full-profile。
```

### 第 5 步：再跑一个多学者请求

确认单人档案没问题后，再试 `positioning`：

```text
使用 scholar-positioning，把 Trent Victor、Gustav Markkula、Natasha Merat 连起来做 positioning。
```

### 第 6 步：检查结果是不是走对模式

你应该重点检查两件事：

1. 单学者请求有没有只生成 `full-profile`
2. 多学者 `positioning` 有没有先建立可复用 profile，再做连接

如果这两步都对，说明这个 skill 已经基本接上你的工作流了。

---

## 七、第一次使用怎么开始

### 1. 最简单的用法

你可以直接在支持 skills 的环境里，对 AI 提类似这样的请求：

```text
使用 scholar-positioning，给 Donald Norman 建一个 full-profile。
```

或者：

```text
使用 scholar-positioning，把 Trent Victor、Gustav Markkula、Natasha Merat 连起来做 positioning。
```

### 2. skill 会怎么决定走哪条路

这个 skill 内部会先判断你的请求属于哪种模式。

#### 如果你只给一个学者

默认走：

- `full-profile`

也就是说，它只应该给你建单人档案，不应该偷偷顺手做 map。

#### 如果你给多个学者，但没说“连起来看”

默认仍然应该走：

- 多个独立的 `full-profile`

也就是说：

- 有多个人名，不等于自动要建图

#### 只有你明确说要比较、连接、cluster、map

才应该走：

- `build-map`

而且这时它应该先检查这些学者有没有可复用的 `full-profile`。  
如果没有，先补档，再建图。

### 3. 输出会长什么样

#### `full-profile` 应该更像“厚档案”

不是一句话简介，也不是几条 bullet。  
正常应该至少包含这些部分：

- 快速摘要
- 基本信息
- 学术谱系
- 研究轨迹
- 方法论印章
- 核心发现实质分析
- 学者类型定位
- 竞争格局
- Positioning Summary
- 证据边界

#### `positioning` 应该更像“带判断的关系图说明”

它应该尽快回答这些问题：

- 这几个人主要差在哪
- 谁适合拿来对标哪一层
- 谁是桥梁
- 哪些关系只是启发，不是事实

而不是先铺很多背景，再迟迟不说关键差异。

---

## 八、第一次个性化配置怎么做

这是很多人最关心的地方。

### 1. 这个 skill 支持个性化，但不建议默认偷偷读你全部历史记录

当前推荐做法是：

- 第一次启动时，做一个很短的 onboarding
- 根据 onboarding 结果生成你的 user preferences

而不是：

- 默认静默扫描你所有历史对话
- 自动给你下长期人格判断

原因很简单：

- 这样更可控
- 更容易让团队成员共用
- 也更不容易把个人习惯硬写死进核心协议

### 2. 第一次建议配置哪些内容

参考：

- [references/users/onboarding.md](./references/users/onboarding.md)
- [references/users/onboarding-prompt.md](./references/users/onboarding-prompt.md)
- [references/users/examples/README.md](./references/users/examples/README.md)

最少建议配置这 5 类：

1. 输出语言
2. 更偏人读还是更偏 AI 消费
3. 摘要密度
4. 证据边界放前面还是放后面
5. 你的主要领域倾向

### 3. 怎么创建自己的配置

以模板为起点：

- [references/users/template/preferences.template.md](./references/users/template/preferences.template.md)

建议流程：

1. 复制模板
2. 新建一个自己的用户目录
3. 填入偏好
4. 后续按使用情况再微调

比如你可以做成：

```text
references/users/your-name/preferences.md
```

如果你只是想快速起步，不想从空白模板填起，可以先复制最接近你的那份示例，再做少量修改：

- [自动驾驶示例](./references/users/examples/automated-driving.preferences.example.md)
- [事故安全示例](./references/users/examples/accident-safety.preferences.example.md)
- [能量管理示例](./references/users/examples/energy-management.preferences.example.md)

### 4. 哪些东西适合个性化，哪些不适合

适合放进个性化层的：

- 默认中文/英文
- 摘要前置还是后置
- 更重可读性还是更重结构化
- 是否喜欢“一句话总览 + 主簇 + 桥梁”这种阅读节奏

不适合放进个性化层的：

- router 逻辑
- evidence protocol
- coverage protocol
- artifact model
- 核心 taxonomy 原则

也就是说：

- 风格可以个性化
- 协议边界不要个性化到失真

---

## 九、适合哪些团队一起用

这个仓库不是只给一个人用的。

如果你的课题组有人做：

- 自动驾驶
- 事故安全
- 能量管理
- 人因
- HRI
- 方法迁移或 benchmark 分析

这套结构都能复用。

正确姿势不是每个人都 fork 一套逻辑，而是：

- 共用同一套 `core`
- 按方向补自己的 `domain pack`
- 每个人维护自己的 `user overlay`

当前仓库里已经有：

- [automated-driving 领域说明](./references/domains/automated-driving/README.md)
- [accident-safety 占位说明](./references/domains/accident-safety/README.md)
- [energy-management 占位说明](./references/domains/energy-management/README.md)

这样后面维护成本最低，也不容易越改越散。

---

## 十、几个常见误解

### 误解 1：给一串学者名字，就一定要出 map

不对。  
如果没有明确说“连起来看 / 比较 / 建图”，默认应该只是逐个建档。

### 误解 2：map 可以反推 profile

不对。  
这个 skill 的设计明确要求：

- 只有 `profile` 才能稳定支撑 `map`
- 不能用弱 map 去倒推一个本来没有建清楚的学者档案

### 误解 3：full-profile 就是多写一点摘要

不对。  
`full-profile` 应该是重型档案，不是“加长版简介”。

### 误解 4：证据边界会限制 AI 发散

也不对。  
这个 skill 不是不让推断，而是要求：

- 推断要标注强弱
- 启发不要伪装成事实

这反而更适合做 idea 迁移，因为你知道哪些是稳的，哪些只是可探索假设。

---

## 十一、建议怎么用这个 skill

如果你是第一次上手，建议按下面的顺序：

### 第一步：先拿 1 个学者试 `full-profile`

先看它能不能把一个人真正建清楚。  
如果单人档案都很薄，后面的 map 基本也不会稳。

### 第二步：再拿 3-5 个学者试 `positioning`

这时重点看：

- 差异是不是说得够早
- 主簇和桥梁是不是清楚
- 证据边界有没有藏到附录层而不是喧宾夺主

### 第三步：最后再决定要不要派生 roadmap

不要一开始就追 roadmap。  
如果上游 `profile` 和 `positioning` 不稳，roadmap 只会放大偏差。

---

## 十二、这个仓库当前的状态

当前版本已经具备这些能力：

- 单学者 `full-profile`
- 多学者 `build-map`
- evidence / coverage 边界
- taxonomy seed
- roadmap 派生协议
- `core + domain + user` 的兼容式分层架构

当前还额外提供了：

- 新手向中文 README
- `Quick Start`
- 3 份最小 personalize 示例
- 2 个额外领域占位目录，方便团队后续扩展

当前版本的实现策略是：

- 保留旧的顶层 `references/*.md` 路径，避免破坏现有效果
- 同时逐步补齐分层结构，方便开源后给更多人用

也就是说，它现在是：

- 可用的
- 可扩展的
- 但仍然在继续收敛文档和配置层

---

## 十三、给维护者的建议

如果你准备把这个 skill 继续长期维护下去，建议坚持下面三条：

### 1. 不要把当前某个用户的写作习惯直接写死进 core

应该放到 `users/` 层。

### 2. 不要为了“更整齐”把 full-profile 压缩成薄摘要

人能读、能复用、能更新，比看起来整齐更重要。

### 3. 不要让 roadmap 偷偷升级成强预测

roadmap 是派生产物。  
它必须继承上游证据边界。

---

## 十四、快速入口

如果你现在就想开始，按这个顺序看：

1. [README.md](./README.md)
2. [SKILL.md](./SKILL.md)
3. [references/users/onboarding.md](./references/users/onboarding.md)
4. [references/users/onboarding-prompt.md](./references/users/onboarding-prompt.md)
5. [references/users/template/preferences.template.md](./references/users/template/preferences.template.md)
6. [references/users/examples/README.md](./references/users/examples/README.md)
7. [references/retrieval-protocol.md](./references/retrieval-protocol.md)

如果你想看“这个 skill 的个性化层长什么样”，看这里：

- [references/users/liutingnan/preferences.md](./references/users/liutingnan/preferences.md)
- [references/users/examples/automated-driving.preferences.example.md](./references/users/examples/automated-driving.preferences.example.md)
- [references/users/examples/accident-safety.preferences.example.md](./references/users/examples/accident-safety.preferences.example.md)
- [references/users/examples/energy-management.preferences.example.md](./references/users/examples/energy-management.preferences.example.md)

---

## License

MIT。见 [LICENSE](./LICENSE)。
