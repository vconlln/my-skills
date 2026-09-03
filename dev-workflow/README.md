# dev-workflow · 开发流程五步法

```
需求理解 → 方案设计 → 代码实现 → 代码审查 → Bug 修复
```

各阶段按 reference 文件执行，产物自动落盘 `docs/<module>/`（追加写入，带时间标题）。

## 生态位

本技能是五步法的**默认轻量路径与落盘引擎**：

| 阶段 | 需要升级时改用 |
|------|----------------|
| ② 方案设计（有旧代码/旧方案、要判升级还是新开发） | `solution-design` |
| ③ 代码实现（需要开发规范/公共库约束 + 检查门禁） | `spec-driven-coding` |
| ①④⑤ | 本技能即为最终版本，无深度版 |

落盘的 `docs/**/方案设计.md` 同时是 `solution-design` 的历史方案来源——用得越多，方案库越厚。

## reference 清单

| 文件 | 对应阶段 | 内容 |
|------|----------|------|
| [requirement.md](reference/requirement.md) | 需求理解 | 信息收集、需求拆解（P0/P1/P2）、验收标准（Given-When-Then）、需求文档模板 |
| [design.md](reference/design.md) | 方案设计 | 技术选型、架构、接口/数据模型设计、方案文档模板 |
| [implementation.md](reference/implementation.md) | 代码实现 | 实现阶段流程 |
| [review.md](reference/review.md) + review-kit/ | 代码审查 | 14 份语言/专题审查指南（C、C++、Go、Java、Python、Qt、Rust、React、TypeScript、Vue、CSS、架构、性能、安全、常见 Bug 清单）+ PR 审查模板 |
| [bug-fix.md](reference/bug-fix.md) | Bug 修复 | 修复阶段流程 |

## 留空待填充

**无** —— 各 reference 内容完整，开箱即用。

## 已知边界（刻意留白，不内置）

- **无独立「测试」步骤**：测试要求融入代码实现与代码审查两个阶段；需要正式测试规范时填入 `spec-driven-coding` 的 `reference/STANDARDS.md`，或另行创建测试技能
- **无术语表（CONTEXT.md）沉淀机制**：需要时另行自建独立技能，本技能不内置也不依赖外部实现
- **落盘只到 docs/ 目录**：不做 issue 跟踪、CI 集成等工程化动作
