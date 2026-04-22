# PM Workflow Spec Scenarios

## 1. 当前结论

`pm-skills` 当前没有正式 `commands/` workflow spec 层，用户仍以直接调用 atom skill 为主。

这不影响使用，但会带来两个问题：

- 用户需要先自己理解 skill 边界
- 多 skill 串联场景缺少标准入口

因此，按新版母仓库标准，这个仓库最值得补的不是更多 atom skill，而是：

- 一个轻量 Codex hub skill：`pm-skills-router`
- 一批候选 workflow spec，用于未来沉淀高频组合链

## 2. 推荐优先补建的 Workflow Specs

| 候选 workflow spec | 适合场景 | 典型输入 | 会先得到什么 | 推荐调度对象 |
|------|----------|----------|--------------|--------------|
| `/start-from-feature-idea` | 只有功能想法、会议纪要、聊天记录 | 想法、背景、目标用户 | PRD 草稿 + 评审建议 | `pm-prd-writer` -> `pm-review-board` |
| `/start-from-product-data` | 只有数据异常或指标问题 | 指标、时间段、现象 | 分析结论 + 实验 / 埋点建议 | `pm-analytics` -> `pm-experiment-designer` / `pm-tracking-spec-writer` |
| `/start-from-roadmap-question` | 需要版本排序或里程碑规划 | 需求池、目标、资源约束 | 排序建议 + 路线图草案 | `pm-prioritization-engine` -> `pm-roadmap-planner` |
| `/start-from-research-question` | 要做调研、竞品或复盘 | 问题背景、样本、目标 | 调研结构或复盘结论 | `pm-survey-designer` / `pm-competitor-deconstructor` / `pm-postmortem-writer` |
| `/start-from-reference-ui` | 只有截图或参考网址 | 图片、链接、改造目标 | HTML / Pencil 原型结果 | `pm-image2proto` / `pm-image2pencil` / `pm-url2proto` |

## 3. README 可直接回写的入口说明草稿

如果后续补 `commands/`，首页可以先这样写：

- `/start-from-feature-idea`
  适合手头只有模糊需求、会议纪要或聊天记录时使用，会先得到一版 PRD 草稿和预评审问题清单。
- `/start-from-product-data`
  适合手头只有指标异常或漏斗问题时使用，会先得到一版分析判断，以及后续实验或埋点建议。
- `/start-from-roadmap-question`
  适合需求很多但排不出先后时使用，会先得到优先级排序和路线图草案。
- `/start-from-reference-ui`
  适合只有截图或网址，但想快速把想法可视化时使用，会先得到一版原型结果。

## 4. 后续 Updates 更新应记录什么

后续如果正式加 workflow spec 层，`README` 和 `CHANGELOG` 至少应同步记录：

- 新增了哪些 workflow spec
- 每条 workflow spec 优先服务什么场景
- 每条 workflow spec 会先得到什么结果
- 每条 workflow spec 默认串起了哪些 skill

## 5. 这轮回修的原则

这轮不强行补空壳 `commands/*.md`。

原因是：

- 当前仓库还没有统一的项目目录规范
- 直接补命令文件容易形成“文件有了，但不可执行”的假标准

所以这轮先补 `pm-skills-router`，再把 workflow spec 需求梳理清楚，保留下一轮正式建设空间。
