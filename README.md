# PM Skills Sample Repo

这是一个把 **产品经理常见工作流** 组织成轻量技能仓库的样板仓。

它解决的不是“缺几个 PM prompt”，而是更高频的几个问题：

- 需求、调研、优先级、路线图、实验、原型这些动作很散，不知道怎么串成一条顺的链路
- 想学 skills 仓库怎么搭，但又不想一上来上重型系统
- 想复用一套样板去扩别的领域仓库，但不知道最小骨架应该长什么样

进入这套样板仓后，应该先得到的不是一堆目录，而是：

- 哪 13 个 PM skills 值得保留
- 哪 5 条命令最适合调度这些 skills
- 一套可复制到别的领域仓库里的轻量结构

## 1. 这是什么

这不是一个单纯的 PM prompt 集合，而是一个 **13 个 PM skills + 5 条 workflow commands + 1 个主 plugin** 的轻量样板仓库。

它最适合三类使用目标：

- 快速安装一套 PM skills
- 学习轻量技能仓库怎么组织
- 后续继续复制出别的领域样板仓库

这个样板真正卖点不是“内容很大”，而是：

- 结构够轻
- 命令够清楚
- 技能边界够稳定
- 很适合复制成下一套仓库

## 2. 创作来源

这个样板仓库基于 `zephyrwang6/pm-skills` 当前这 13 个 `pm-*` skills 构建，并补齐了仓库级的 `plugin / command / catalog / docs` 结构。

## 3. 怎么用

先按你现在手头的任务选命令，不要先逐个翻 skill。

### 3.1 按你现在的任务启动

| 你现在要做什么 | 建议命令 | 会先得到什么 |
|----------------|----------|--------------|
| 需求还没想清楚，要先跑调研、竞品和问题框架 | `/run-discovery` | 调研问题框架、竞品拆解方向和 PRD 起点 |
| 已经知道要做一个需求，要补 PRD、评审和埋点 | `/write-prd-package` | 一版可评审 PRD、评审意见和埋点方案 |
| 已经有一批需求，要先排优先级再出路线图 | `/prioritize-roadmap` | 优先级结果、路线图草稿和节奏建议 |
| 已经有数据问题，要分析、设计实验、最后沉淀复盘 | `/analyze-experiment-loop` | 原因分析、实验方案和复盘闭环 |
| 已经有截图或网址，要快速做原型 | `/prototype-from-reference` | 对应的 HTML / Pencil / Next.js 原型路径 |

### 3.2 推荐用法

1. 先走命令，再看 skills。命令是入口，skill 是单点能力。
2. 一组轻量仓库优先控制在 `10-15` 个核心 skills，再补 `3-5` 条 commands。
3. command 只负责编排，不要把 skill 内容全文复制进去。
4. 如果这是给别人学结构用的样板仓，README 要优先讲清“这是什么、怎么用、会先得到什么”。
5. 这套 README 里的“怎么用”已经合并了最佳实践，不再单独拆一章重复说明。

## 4. 工作说明

### 4.1 Skills 说明

| Skill | 干什么 |
|-------|--------|
| `pm-prd-writer` | 把一段模糊的描述变成可以过评审的 PRD |
| `pm-review-board` | 模拟 6 个角色同时 review 需求，提前发现问题 |
| `pm-prioritization-engine` | 用 RICE / ICE / Kano 同时打分，需求排序不再拍脑袋 |
| `pm-roadmap-planner` | 输入目标和人力，输出带节奏和依赖的路线图 |
| `pm-analytics` | 数据跌了，先找原因，再给建议，再形成分析闭环 |
| `pm-experiment-designer` | 实验假设、分流方案、样本量计算、止损规则一次设计清楚 |
| `pm-tracking-spec-writer` | 把用户链路拆成埋点事件，补齐字段、口径和 QA 校验 |
| `pm-survey-designer` | 从调研目标到问卷题目，让每道题都服务一个假设 |
| `pm-competitor-deconstructor` | 从策略、功能、体验、增长四维拆竞品 |
| `pm-postmortem-writer` | 做 5-Why 复盘和行动项沉淀，复盘报告可直接发团队 |
| `pm-image2proto` | 根据截图快速生成可运行的 HTML 原型 |
| `pm-image2pencil` | 根据截图生成 Pencil 设计稿并补结构说明 |
| `pm-url2proto` | 根据网址快速生成本地 Next.js 原型工程 |

### 4.2 工作流命令说明

| Command | 什么场景用 | 典型输入 | 会先得到什么 |
|---------|------------|----------|--------------|
| `/run-discovery` | 需求还没想清楚时，先把调研、竞品和问题框架跑一遍 | 模糊需求、用户问题、竞品名单 | 调研框架、竞品拆解和 PRD 起点 |
| `/write-prd-package` | 把一个需求从 PRD 写作推进到评审和埋点方案 | 功能描述、需求背景、目标用户 | 一版可评审 PRD、评审意见和埋点方案 |
| `/prioritize-roadmap` | 先排优先级，再转成路线图，适合版本规划场景 | 需求池、资源约束、目标 | 优先级结果和路线图草稿 |
| `/analyze-experiment-loop` | 先分析数据，再设计实验，最后沉淀复盘 | 指标问题、数据结果、实验目标 | 原因分析、实验方案和复盘闭环 |
| `/prototype-from-reference` | 根据截图或网址，选择最合适的原型落地路径 | 页面截图、网址、原型目标 | HTML / Pencil / Next.js 原型路径 |

命令链路，单独看更清楚：

- `/run-discovery`：`pm-survey-designer` → `pm-competitor-deconstructor` → `pm-prd-writer`
- `/write-prd-package`：`pm-prd-writer` → `pm-review-board` → `pm-tracking-spec-writer`
- `/prioritize-roadmap`：`pm-prioritization-engine` → `pm-roadmap-planner`
- `/analyze-experiment-loop`：`pm-analytics` → `pm-experiment-designer` → `pm-postmortem-writer`
- `/prototype-from-reference`：`pm-url2proto` 或 `pm-image2proto` 或 `pm-image2pencil`

## 5. 仓库结构

```text
pm-skills-sample/
├── .claude-plugin/
│   └── marketplace.json
├── AGENTS.md
├── CLAUDE.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── README.md
├── catalog/
│   ├── commands-index.yaml
│   └── skills-index.yaml
├── docs/
│   ├── 01-sample-repo-architecture.md
│   ├── 02-how-to-use-this-sample-repo.md
│   ├── 03-source-origin.md
│   └── 04-test-cases.md
└── plugins/
    └── pm-core/
        ├── .claude-plugin/plugin.json
        ├── README.md
        ├── commands/
        └── skills/
```

- `.claude-plugin/`：仓库级 marketplace 元数据
- `catalog/`：skills 与 commands 的索引层
- `docs/`：样板说明、使用说明、来源说明与测试案例
- `plugins/pm-core/`：PM 主 plugin，承载真实 skills 与 commands

## 6. 三层架构

- `skill`：解决单点任务
- `command`：把多个 skill 串成一条工作流
- `plugin`：把同一能力域打包成可分发单元

你可以把它理解成一句话：

- `skill` 解决单点问题
- `command` 负责流程编排
- `plugin` 负责整组分发

## 7. 如何使用

### 方式一：安装单个 skill

```bash
cp -r plugins/pm-core/skills/pm-prd-writer ~/.claude/skills/
cp -r plugins/pm-core/skills/pm-analytics ~/.claude/skills/
```

### 方式二：安装整组 PM skills

```bash
cp -r plugins/pm-core/skills/* ~/.claude/skills/
```

### 方式三：按 command 学 workflow

如果你不是只想安装，而是想学习“仓库怎么设计”，优先看：

- `plugins/pm-core/commands/run-discovery.md`
- `plugins/pm-core/commands/write-prd-package.md`
- `plugins/pm-core/commands/prioritize-roadmap.md`

## Updates 更新

- `2026-04-20`：README 按最新版母仓库标准重写，统一成“强需求 + 怎么用 + 去重后的工作说明”结构。
- `2026-04-20`：命令说明统一改成“场景 + 典型输入 + 会先得到什么”的入口写法。
- `2026-04-20`：工作流命令说明改成“表格 + 单独链路”结构，避免表格渲染时出现重复阅读。
- `2026-04-20`：样板仓库切换为基于 `zephyrwang6/pm-skills` 的 13 个 `pm-*` skills 重建。
- `2026-04-19`：仓库升级为 `marketplace + plugin + commands + catalog + docs` 的样板结构。
