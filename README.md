# pm-skills

面向产品经理的 AI 工作技能仓。它服务的是那些每天都在重复写 PRD、排优先级、做分析、补埋点、跑评审的人，解决的是“每次都像从头做一遍”的高频摩擦。

用户进来后，应该先得到两件事：一是知道自己的问题属于哪一类 PM 工作，二是知道当前该调用哪个 Skill，能先产出什么。

## 1. 这是什么

这个仓库目前是一个 **skill-only PM 能力仓**：

- `13` 个核心 PM Skills
- `2` 个原型方向的兼容别名目录：`space-image2proto`、`space-url2proto`
- 目前还没有单独的 `commands/` 入口层

它的定位不是“产品经理百科”，而是把 PM 的高频重复工作拆成一组可以直接调用的执行型技能：

- 需求整理与评审
- 优先级与路线图
- 数据分析与实验设计
- 埋点与调研
- 竞品、复盘与原型转换

如果你的目标是把模糊输入更快变成能评审、能讨论、能交付的结构化结果，这个仓库就是为这个目标准备的。

## 2. 怎么用

这类仓库的推荐用法不是先读文档，而是先按你当前的问题进入对应 Skill。

### 2.1 先按问题类型找入口

| 你现在要解决什么 | 建议 Skill | 会先得到什么 |
|------|------------|----------------|
| 一段模糊需求，需要写成正式文档 | `pm-prd-writer` | 一版可评审 PRD 草稿 |
| 需求马上要过会，想先做预评审 | `pm-review-board` | 多角色问题清单和风险点 |
| 一堆需求排不出先后 | `pm-prioritization-engine` | 一版优先级排序和取舍理由 |
| 要做路线图、版本规划或阶段排期 | `pm-roadmap-planner` | 里程碑、依赖和节奏建议 |
| 指标跌了、漏斗掉了、想找原因 | `pm-analytics` | 归因假设和决策建议 |
| 要设计 A/B 实验 | `pm-experiment-designer` | 实验方案、指标和判定规则 |
| 需求要补埋点 | `pm-tracking-spec-writer` | 事件表、字段表和校验清单 |
| 要做用户调研或问卷 | `pm-survey-designer` | 结构化问卷或调研提纲 |
| 要拆竞品 | `pm-competitor-deconstructor` | 四维竞品拆解和可借鉴点 |
| 要写复盘 | `pm-postmortem-writer` | 结构化复盘报告和行动项 |
| 有截图，想快速变原型 | `pm-image2proto` / `pm-image2pencil` | HTML 原型或 Pencil 设计稿 |
| 有参考网址，想本地复刻 | `pm-url2proto` | 一版本地可跑的原型项目 |

### 2.2 再按你手头已有的素材选入口

| 你手头有什么 | 建议先走什么 | 会先得到什么 |
|------|------------|----------------|
| 一段口头想法、会议纪要、聊天记录 | `pm-prd-writer` | 需求结构化草稿 |
| 一份草稿需求文档 | `pm-review-board` | 漏项、风险和质疑点 |
| 一批待选需求 | `pm-prioritization-engine` | 排序结果与版本建议 |
| 一组业务数据或现象 | `pm-analytics` | 解释框架和下一步建议 |
| 一张页面截图或一个网址 | `pm-image2proto` / `pm-url2proto` | 原型化结果 |

### 2.3 当前使用规范

这个仓库已经适合直接用，但它还不是“命令仓”。

当前最稳妥的使用方式是：

1. 先判断问题属于哪类 PM 工作
2. 直接调用对应 Skill
3. 需要跨多个 Skill 串联时，再由使用者自己做人工编排

如果你现在只想最快落地，优先从上表里选一个 Skill 直接开始。

## 3. 工作说明

### 3.1 能力域梳理

| 能力域 | 对应 Skill | 解决什么问题 |
|------|------------|--------------|
| 需求设计 | `pm-prd-writer` | 把模糊问题变成可评审需求 |
| 方案评审 | `pm-review-board` | 提前暴露跨角色疑问和风险 |
| 决策排序 | `pm-prioritization-engine` | 给需求排序、做版本取舍 |
| 节奏规划 | `pm-roadmap-planner` | 把目标拆成里程碑和节奏 |
| 数据判断 | `pm-analytics` / `pm-experiment-designer` / `pm-tracking-spec-writer` | 做归因、实验和埋点设计 |
| 用户洞察 | `pm-survey-designer` / `pm-competitor-deconstructor` | 做调研和竞品拆解 |
| 复盘沉淀 | `pm-postmortem-writer` | 沉淀复盘与改进行动 |
| 原型加速 | `pm-image2proto` / `pm-image2pencil` / `pm-url2proto` | 把参考物转成原型资产 |

### 3.2 当前工作流命令状态

按新版母仓库口径，这个仓库已经适合补命令层，但现在还没有正式 `commands/` 目录。

当前的真实状态是：

- 已有稳定 Skill 层
- 已有清晰能力域
- 缺的是“按素材状态进入”的命令入口层

优先级最高的候选命令是：

| 候选命令 | 适合场景 | 预计会先得到什么 |
|------|----------|------------------|
| `/start-from-feature-idea` | 只有功能想法或会议纪要 | PRD 草稿 + 评审建议 |
| `/start-from-product-data` | 只有指标问题或数据异常 | 分析结论 + 实验 / 埋点建议 |
| `/start-from-roadmap-question` | 只有优先级冲突或排期问题 | 排序建议 + 路线图草案 |
| `/start-from-reference-ui` | 只有截图或参考网址 | 原型结果 + 后续产品化建议 |

### 3.3 仓库边界

这个仓库主要负责产品经理日常工作的结构化与提效，不负责：

- 纯视觉设计系统
- 纯工程实现
- 复杂多插件路由中台

如果未来要升级成“完整产品工作系统仓”，再补 `commands/`、`docs/workbooks/command-chain-map.md` 和插件分层会更合适。

## 4. 仓库结构

```text
pm-skills/
├── README.md
├── CHANGELOG.md
├── docs/
│   └── workbooks/
│       ├── domain-system-map.md
│       └── workflow-command-scenarios.md
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

## Updates 更新

- `2026-04-20`：按新版母仓库标准补齐 `docs/workbooks/domain-system-map.md`，明确这是一个 `skill-only PM 能力仓`，不是插件化系统仓
- `2026-04-20`：按新版母仓库标准补齐 `docs/workbooks/workflow-command-scenarios.md`，明确当前命令层缺口与优先补建方向
- `2026-04-20`：重写首页 README，把“服务谁、解决什么、先走哪个入口、会先得到什么”放到首页前部
- `2026-04-20`：新增根级 `CHANGELOG.md`，把这轮结构回修正式记录下来

## 相关项目

- [career.skill](https://github.com/zephyrwang6/career.skill)

made with Claude Code，以及很多不想再重复手写 PRD 和复盘的工作日
