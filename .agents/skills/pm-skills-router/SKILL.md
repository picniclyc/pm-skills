---
name: pm-skills-router
description: Use this skill when the user has a product-management task but is not sure which PM skill to invoke, or when they mention /start-from-feature-idea, /start-from-product-data, /start-from-roadmap-question, /start-from-research-question, /start-from-reference-ui, PM skills, PRD, review, prioritization, roadmap, analytics, experiment, tracking, survey, competitor analysis, postmortem, or prototype routing. This is a lightweight router for the pm-skills repository, not a replacement for the atom skills.
---

# PM Skills Router

Use this as the Codex-facing entrance to the `pm-skills` repository.

## First Judgment

Classify the user's PM work before invoking atom skills:

| User intent | Primary skill | Follow-up skill |
|-------------|---------------|-----------------|
| 模糊需求、功能想法、会议纪要 | `pm-prd-writer` | `pm-review-board` |
| 需求过会、方案查漏补缺 | `pm-review-board` | `pm-tracking-spec-writer` |
| 需求太多、优先级冲突 | `pm-prioritization-engine` | `pm-roadmap-planner` |
| 路线图、版本规划、阶段排期 | `pm-roadmap-planner` | `pm-prioritization-engine` |
| 指标异常、漏斗问题、归因分析 | `pm-analytics` | `pm-experiment-designer` 或 `pm-tracking-spec-writer` |
| A/B 实验、灰度、样本量 | `pm-experiment-designer` | `pm-analytics` |
| 埋点、指标口径、QA 校验 | `pm-tracking-spec-writer` | `pm-analytics` |
| 调研问卷、用户访谈 | `pm-survey-designer` | `pm-competitor-deconstructor` |
| 竞品拆解、对标分析 | `pm-competitor-deconstructor` | `pm-prioritization-engine` |
| 复盘、上线总结、事故 RCA | `pm-postmortem-writer` | `pm-roadmap-planner` |
| 截图或网址转原型 | `pm-image2proto` / `pm-image2pencil` / `pm-url2proto` | `pm-review-board` |

## Output Standard

Every routing answer should state:

- 当前问题类型
- 推荐先用哪个 skill
- 是否需要串联第二个 skill
- 第一批输出物是什么
- 缺少哪些输入会影响质量

## Guardrails

- Do not invent a `/command` as if it is available in Codex. Candidate `/xxx` entries are workflow specs until implemented as route skills.
- Prefer atom skills directly when the user intent is already clear.
- Use this router only when the PM task is mixed, vague, or needs a skill chain.
