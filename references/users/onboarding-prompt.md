# First-Run Onboarding Prompt

Use this prompt when a user installs `scholar-positioning` for the first time and has no stable user overlay yet.

Purpose:

- collect the minimum personalization inputs
- avoid silently scanning historical conversations by default
- produce a usable `preferences.md` draft quickly

Do not use this prompt to:

- infer a long-term user profile without confirmation
- override core protocol
- rewrite taxonomy, evidence rules, or router behavior

## Agent instructions

When no user-specific preferences file exists, or when the user explicitly asks to configure personalization for the first time, ask the following short onboarding block.

Keep the interaction short.
Do not ask broad biography questions.
Do not ask more than these unless the user volunteers extra constraints.

## Suggested user-facing prompt

```text
我先用 5 个很短的问题帮你完成 scholar-positioning 的首次个性化配置。  
这些问题只影响输出呈现和默认使用习惯，不会改动核心协议。

1. 你希望默认输出语言是什么？
- 中文
- 英文
- 中英混合（中文为主，术语保留英文）

2. 你更希望输出主要给谁看？
- 人读优先
- 平衡
- AI/结构化消费优先

3. 你更喜欢什么摘要密度？
- 简洁
- 中等
- 稠密

4. 关于证据边界，你更偏好哪种展示方式？
- 前面就提示
- 平衡分布
- 放后面/附录

5. 你目前最主要的研究方向更接近哪类？
- automated-driving
- accident-safety
- energy-management
- 其他（可补充）
```

## After the user answers

Convert the answers into a compact preferences draft using the template categories:

- `language_defaults`
- `readability_defaults`
- `summary_density_defaults`
- `evidence_boundary_presentation`
- `default_task_tendency`
- `domain_tendency`

Also infer cautiously:

- `preferred heading style`
- whether to put quick summary at top
- whether to surface key differences early in positioning maps

Only make these inferences when they are straightforward from the answers.
If not straightforward, leave them explicit or mark them as defaults.

## Suggested confirmation block

```text
我根据你的回答整理出一版初始偏好：

- 默认语言：
- 可读性倾向：
- 摘要密度：
- 证据边界展示：
- 主要领域：

这版只影响输出风格和默认阅读顺序，不影响 scholar-positioning 的核心协议。  
确认后，我会把它写成你的 `preferences.md`。
```

## Output target

Default target path:

```text
references/users/<user-name>/preferences.md
```

If the user does not yet want to write files:

- provide the draft only
- do not silently persist it

## Minimal mapping guidance

- `中文` -> `default language: Chinese`
- `英文` -> `default language: English`
- `中英混合` -> `default language: Chinese`, `keep technical terms in English when helpful: yes`
- `人读优先` -> `primary audience: human-first`
- `平衡` -> `primary audience: balanced`
- `AI/结构化消费优先` -> `primary audience: AI-first`
- `简洁 / 中等 / 稠密` -> map to `light / medium / dense`
- `前面就提示 / 平衡分布 / 放后面` -> map to `early / balanced / late / appendix`

## Guardrail reminder

This onboarding prompt is a user-overlay bootstrap only.
It must not be used to:

- change artifact names
- change profile -> map dependency
- downgrade evidence labeling rules
- turn roadmap into a default output
