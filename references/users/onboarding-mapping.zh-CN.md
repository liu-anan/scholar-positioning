# 首次配置字段映射表

这份文档用来解释：

- 首次启动问答里的 5 个问题
- 是如何映射到 `preferences.md` 字段里的
- 哪些字段可以从回答直接确定
- 哪些字段只能保守推断

这是一份中文维护说明，不是新的协议层。

## 用途

- 给维护者快速看懂问答结果怎么落盘
- 给第一次配置的用户理解“我刚才的回答会改哪里”
- 降低把自然语言回答转成字段时的随意性

## 总原则

### 1. 先映射显式答案，再做最小推断

优先使用用户明确说出的偏好。  
只有在非常直接的情况下，才补少量推断字段。

### 2. 推断只作用于呈现层

允许补的通常是：

- `preferred heading style`
- `prefer quick summary at top`
- `prefer key differences early in maps`

不允许借机改动：

- artifact model
- router logic
- evidence protocol
- coverage protocol
- domain taxonomy definitions

### 3. 不确定就保守

如果用户回答不足以支撑某个字段：

- 保留为空
- 或写成中性默认值
- 不要擅自补成强个性化设定

---

## 问题 1：默认输出语言

用户题目：

- 中文
- 英文
- 中英混合（中文为主，术语保留英文）

### 主要映射

- `中文`
  - `language_defaults.default language: Chinese`
  - `language_defaults.keep technical terms in English when helpful: optional / default yes if domain is technical`
- `英文`
  - `language_defaults.default language: English`
  - `language_defaults.keep technical terms in English when helpful: yes`
- `中英混合`
  - `language_defaults.default language: Chinese`
  - `language_defaults.keep technical terms in English when helpful: yes`

### 可补充推断

- `preferred heading style: Chinese-first`
  - 仅当用户偏中文或中英混合时

---

## 问题 2：主要给谁看

用户题目：

- 人读优先
- 平衡
- AI/结构化消费优先

### 主要映射

- `人读优先`
  - `readability_defaults.primary audience: human-first`
- `平衡`
  - `readability_defaults.primary audience: balanced`
- `AI/结构化消费优先`
  - `readability_defaults.primary audience: AI-first`

### 可补充推断

- 当用户选 `人读优先` 或 `平衡` 时，通常可补：
  - `readability_defaults.prefer quick summary at top: yes`
- 当用户选 `人读优先` 时，通常可补：
  - `readability_defaults.prefer key differences early in maps: yes`

### 不建议直接推断

不要仅凭这个答案就改：

- `default_task_tendency`
- `domain_tendency`

---

## 问题 3：摘要密度

用户题目：

- 简洁
- 中等
- 稠密

### 主要映射

- `简洁`
  - `summary_density_defaults.profile summary density: light`
  - `summary_density_defaults.positioning summary density: light`
- `中等`
  - `summary_density_defaults.profile summary density: medium`
  - `summary_density_defaults.positioning summary density: medium`
- `稠密`
  - `summary_density_defaults.profile summary density: dense`
  - `summary_density_defaults.positioning summary density: dense`

### 推荐保守规则

如果用户只回答了一个整体密度，不要强行把 roadmap 也设得很激进。  
默认可写：

- `summary_density_defaults.roadmap route count preference: one primary route`

只有用户明显偏探索型时，再考虑：

- `one primary + one secondary`
- `broader exploration`

---

## 问题 4：证据边界展示方式

用户题目：

- 前面就提示
- 平衡分布
- 放后面/附录

### 主要映射

- `前面就提示`
  - `evidence_boundary_presentation.put detailed evidence boundary: early`
- `平衡分布`
  - `evidence_boundary_presentation.put detailed evidence boundary: balanced`
- `放后面/附录`
  - `evidence_boundary_presentation.put detailed evidence boundary: late / appendix`

### 可补充推断

如果用户偏 `前面就提示`，通常可补：

- `show Minimal Source Notes by default: yes`

如果用户偏 `放后面/附录`，通常可补：

- `show Claims intentionally not made by default: when needed`
- `show Minimal Source Notes by default: when coverage is thin`

### 注意

这里改的是展示顺序，不是证据标准本身。  
不能因为用户想后置展示，就放松 `E1-E4` 或 `C1-C3` 的要求。

---

## 问题 5：主要研究方向

用户题目：

- automated-driving
- accident-safety
- energy-management
- 其他（可补充）

### 主要映射

- `automated-driving`
  - `domain_tendency.main domain pack: automated-driving`
- `accident-safety`
  - `domain_tendency.main domain pack: accident-safety`
- `energy-management`
  - `domain_tendency.main domain pack: energy-management`
- `其他`
  - `domain_tendency.main domain pack: <user provided label or unspecified>`

### 次领域怎么写

如果用户没有明确给第二方向，保守写：

- `domain_tendency.secondary domain pack: unspecified`

只有用户明确说了另一个长期方向，才补 second domain。

### 不要混淆

主领域倾向不等于：

- 当前单次任务主题
- 核心 taxonomy 已经被替换
- build-map 默认只在这个领域工作

---

## 建议的默认补全规则

如果用户只回答了 5 个选择题，没有补充更多自由描述，可采用下面这套最小默认补全：

- `preferred heading style: Chinese-first`
  - 当默认语言是中文或中英混合
- `prefer quick summary at top: yes`
  - 当 primary audience 不是 `AI-first`
- `prefer key differences early in maps: yes`
  - 当 primary audience 是 `human-first` 或 `balanced`
- `roadmap route count preference: one primary route`
  - 除非用户明显说自己偏探索型
- `prefer profile-first before map by default: yes`
  - 作为当前 skill 的兼容式默认

---

## 一个最小映射示例

用户回答：

```text
1. 中英混合
2. 平衡
3. 中等
4. 放后面/附录
5. automated-driving
```

可落成：

```text
- language_defaults:
  - default language: Chinese
  - keep technical terms in English when helpful: yes
  - preferred heading style: Chinese-first
- readability_defaults:
  - primary audience: balanced
  - prefer quick summary at top: yes
  - prefer key differences early in maps: yes
- summary_density_defaults:
  - profile summary density: medium
  - positioning summary density: medium
  - roadmap route count preference: one primary route
- evidence_boundary_presentation:
  - put detailed evidence boundary: late / appendix
  - show `Claims intentionally not made` by default: when needed
  - show `Minimal Source Notes` by default: when coverage is thin
- default_task_tendency:
  - most common use: full-profile
  - prefer profile-first before map by default: yes
- domain_tendency:
  - main domain pack: automated-driving
  - secondary domain pack: unspecified
```

---

## 和其他文件的关系

这几个文件的分工应保持清楚：

- `onboarding.md`
  - 解释什么时候做首次配置
- `onboarding-prompt.md`
  - 给出实际要问用户的 5 个问题
- `onboarding-mapping.zh-CN.md`
  - 解释答案怎么映射成字段
- `examples/onboarding-output.preferences.example.md`
  - 展示最终落成的成品样子
- `template/preferences.template.md`
  - 作为真正可填写或保存的模板

不要把这几个文件混成一个大说明。
