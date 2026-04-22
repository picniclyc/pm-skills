# PM Skills Sample Repo

这是一个把 **产品经理高频工作** 组织成轻量 skills 集合的样板仓。

它解决的不是“多几个 PM prompt”，而是三个更真实的问题：

- 需求、评审、优先级、路线图、数据、实验、原型这些动作很散，不知道先用哪个 skill
- 未来要复制出其他领域 skills 仓，但不知道轻量仓库最小应该长什么样
- 不想一开始就上重型系统仓，只想先把 `10-15` 个核心 skills 组织清楚

进入这个样板仓后，应该先得到的不是一堆目录，而是：

- 哪 `13` 个 PM skills 是核心能力
- 哪些场景可以直接调用单点 skill
- 哪些场景适合沉淀为 workflow spec 或 route skill
- 这套结构如何复制到下一个领域仓库

## 1. 这是什么

这是一个 **13 个 PM skills + 1 个轻量 Codex hub skill + 候选 workflow spec 清单** 的样板仓。

它适合三类使用目标：

- 快速安装一套 PM skills
- 学习轻量 skills 仓库怎么组织
- 后续复制出增长、运营、设计、咨询等其他领域仓库

当前真实状态：

- `13` 个核心 PM skills
- `2` 个原型方向兼容别名：`space-image2proto`、`space-url2proto`
- `1` 个轻量 Codex hub skill：`pm-skills-router`
- 暂未补正式 `commands/` workflow spec 目录

## 2. 创作来源

这个样板仓基于 `zephyrwang6/pm-skills` 当前的 `pm-*` skills 结构整理而来。

我保留了原仓里最有价值的部分：

- PM 工作场景边界清楚
- Skill 命名和触发条件相对稳定
- 从需求、评审、优先级、路线图到数据、实验、原型的链路完整

同时按母仓新版标准补齐了轻量入口说明：不再把 `/xxx` 误写成 Codex 可自动触发命令，而是区分 `hub skill / atom skill / workflow spec`。

## 3. 工作说明

### 3.1 Skills 说明

| Skill | 干什么 |
|-------|--------|
| `pm-skills-router` | Codex 总入口：当任务很模糊时，先判断该调用哪个 PM skill |
| `pm-prd-writer` | 把一段模糊描述变成可以过评审的 PRD |
| `pm-review-board` | 模拟 6 个角色同时 review 需求，提前发现问题 |
| `pm-prioritization-engine` | 用 RICE / ICE / Kano 同时打分，减少拍脑袋排序 |
| `pm-roadmap-planner` | 输入目标和人力，输出带节奏和依赖的路线图 |
| `pm-analytics` | 指标异常时先做归因，再给可执行建议 |
| `pm-experiment-designer` | 把实验假设、分流、样本量、止损规则一次设计清楚 |
| `pm-tracking-spec-writer` | 把用户链路拆成埋点事件，补齐字段、口径和 QA 校验 |
| `pm-survey-designer` | 从调研目标到问卷题目，让每道题都服务一个假设 |
| `pm-competitor-deconstructor` | 从策略、功能、体验、增长四维拆竞品 |
| `pm-postmortem-writer` | 做 5-Why 复盘和行动项沉淀，复盘报告可直接发团队 |
| `pm-image2proto` | 根据截图快速生成可运行的 HTML 原型 |
| `pm-image2pencil` | 根据截图生成 Pencil 设计稿并补结构说明 |
| `pm-url2proto` | 根据网址快速生成本地 Next.js 原型工程 |

### 3.2 候选 Workflow Spec 说明

这些 `/xxx` 目前是候选 workflow spec，不是 Codex 菜单命令。只有当某条链路被反复高频使用、输入输出稳定时，才建议升级成 route skill。

| 候选 workflow spec | 什么场景用 | 链路 | 会先得到什么 |
|--------------------|------------|------|--------------|
| `/run-discovery` | 需求还没想清楚，需要先做调研、竞品和问题框架 | `pm-survey-designer` -> `pm-competitor-deconstructor` -> `pm-prd-writer` | 调研框架、竞品拆解和 PRD 起点 |
| `/write-prd-package` | 已经知道要做一个需求，要补 PRD、评审和埋点 | `pm-prd-writer` -> `pm-review-board` -> `pm-tracking-spec-writer` | 一版可评审 PRD、评审意见和埋点方案 |
| `/prioritize-roadmap` | 已经有一批需求，要先排优先级再出路线图 | `pm-prioritization-engine` -> `pm-roadmap-planner` | 优先级结果和路线图草稿 |
| `/analyze-experiment-loop` | 已经有数据问题，要分析、设计实验、最后沉淀复盘 | `pm-analytics` -> `pm-experiment-designer` -> `pm-postmortem-writer` | 原因分析、实验方案和复盘闭环 |
| `/prototype-from-reference` | 已经有截图或网址，要快速做原型 | `pm-url2proto` 或 `pm-image2proto` 或 `pm-image2pencil` | HTML / Pencil / Next.js 原型路径 |

## 4. 怎么用

1. 如果你已经知道要做什么，直接调用对应 atom skill。
2. 如果你只知道“这是一个 PM 问题”，但不知道先从哪下手，用 `pm-skills-router` 先判断。
3. 如果同一条组合链反复出现，再把它写进 `docs/workbooks/workflow-spec-scenarios.md`，不要急着建空壳 `commands/`。
4. 只有当 workflow spec 高频、稳定、值得出现在 Codex 菜单里时，再升级为 route skill。

最推荐的启动方式：

| 你现在手头有什么 | 建议入口 | 会先得到什么 |
|------------------|----------|--------------|
| 一段口头想法、会议纪要、聊天记录 | `pm-prd-writer` 或 `pm-skills-router` | 需求结构化草稿 |
| 一份草稿需求文档 | `pm-review-board` | 漏项、风险和质疑点 |
| 一批待选需求 | `pm-prioritization-engine` | 排序结果与版本建议 |
| 一组业务数据或现象 | `pm-analytics` | 解释框架和下一步建议 |
| 一张页面截图或一个网址 | `pm-image2proto` / `pm-url2proto` | 原型化结果 |

## 5. 仓库结构

```text
pm-skills/
├── .agents/
│   └── skills/
│       └── pm-skills-router/
├── docs/
│   └── workbooks/
│       ├── domain-system-map.md
│       └── workflow-spec-scenarios.md
├── pm-analytics/
├── pm-competitor-deconstructor/
├── pm-experiment-designer/
├── pm-image2pencil/
├── pm-image2proto/
├── pm-postmortem-writer/
├── pm-prd-writer/
├── pm-prioritization-engine/
├── pm-review-board/
├── pm-roadmap-planner/
├── pm-survey-designer/
├── pm-tracking-spec-writer/
├── pm-url2proto/
├── space-image2proto/
└── space-url2proto/
```

## 6. 入口架构

- `hub skill`：`pm-skills-router`，负责模糊 PM 任务分流
- `atom skill`：13 个 PM 单点能力，负责具体产出
- `workflow spec`：记录高频组合链，暂不等于 Codex 菜单命令
- `route skill`：未来只有高频稳定链路才升级

一句话概括：

`pm-skills-router` 负责先选路，`pm-*` skills 负责做事，workflow spec 负责沉淀组合经验。

## Updates 更新

- `2026-04-20`：按新版母仓库标准补齐 `docs/workbooks/domain-system-map.md`，明确这是一个轻量 PM skills 样板仓。
- `2026-04-20`：补齐 `docs/workbooks/workflow-spec-scenarios.md`，记录候选组合链和后续升级方向。
- `2026-04-20`：重写首页 README，把“服务谁、解决什么、先走哪个入口、会先得到什么”放到首页前部。
- `2026-04-20`：新增根级 `CHANGELOG.md`，把结构回修正式记录下来。
- `2026-04-23`：按母仓新版 skill cluster 标准补充 `pm-skills-router` hub skill，并把候选 `/xxx` 口径改为候选 workflow spec。

## 相关项目

- [career.skill](https://github.com/zephyrwang6/career.skill)

made with Claude Code，以及很多不想再重复手写 PRD 和复盘的工作日
