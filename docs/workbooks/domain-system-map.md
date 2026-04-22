# PM Domain System Map

## 1. 仓库定位

`pm-skills` 是一个面向产品经理高频工作场景的 `skill-only` 能力仓。

它现在额外补了一个轻量 Codex hub skill：`pm-skills-router`。这个入口只负责判断“该先调用哪个 PM skill”，不把整个仓库改成重型系统仓。

它当前解决的是：

- 需求结构化
- 评审预演
- 优先级判断
- 路线图规划
- 数据分析与实验设计
- 埋点、调研、竞品、复盘
- 截图 / 网址到原型

它当前还不是：

- 插件化多层系统仓
- 以 workflow spec 为主入口的工作流仓
- 带完整项目目录标准的交付仓

## 2. 服务对象

| 对象 | 典型处境 | 现在最急的问题 |
|------|----------|----------------|
| 产品经理 | 日常事项多、重复劳动重 | 想减少每次从头写和从头想 |
| 产品负责人 | 要兼顾需求、排期、沟通 | 想更快拿到可讨论的结构化结果 |
| 独立开发者 / 创业者 | 兼任 PM 工作 | 想用最少方法论成本补齐 PM 产出 |

## 3. 核心能力域

| 能力域 | 核心 Skill | 最小闭环 |
|------|------------|----------|
| 需求设计 | `pm-prd-writer` | 想法 -> PRD 草稿 |
| 方案评审 | `pm-review-board` | 草稿 -> 评审意见 |
| 决策排序 | `pm-prioritization-engine` | 需求池 -> 排序建议 |
| 路线规划 | `pm-roadmap-planner` | 目标 -> 里程碑 |
| 数据判断 | `pm-analytics` / `pm-experiment-designer` / `pm-tracking-spec-writer` | 现象 -> 判断 -> 验证方案 |
| 用户研究 | `pm-survey-designer` / `pm-competitor-deconstructor` | 问题 -> 调研结构 |
| 复盘沉淀 | `pm-postmortem-writer` | 事件 -> 复盘结论 |
| 原型加速 | `pm-image2proto` / `pm-image2pencil` / `pm-url2proto` | 参考物 -> 原型资产 |

## 4. 真实边界

这个仓库负责的是“产品经理工作颗粒度”的技能化，不直接负责：

- 完整项目系统路由
- 跨插件协同调度
- 复杂交付仓编排

因此这轮回修的标准不是把它硬改成系统仓，而是让它作为 `skill-only` 仓也满足新版母仓库的入口表达要求。

## 5. 后续升级方向

如果后续继续扩域，建议按下面顺序升级：

1. 先沉淀高频 workflow spec，不急着补空壳命令文件
2. 再补 `workflow-spec-map.md`
3. 最后再考虑 plugin 分层或按能力域拆仓
