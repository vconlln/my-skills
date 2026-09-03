# my-skills

个人 Agent 技能库（Claude Code / 兼容 SKILL.md 约定的 Agent 均可使用）。

## 技能清单

| 技能 | 目录 | 简介 |
|------|------|------|
| 开发流程五步法 | [dev-workflow/](dev-workflow/) | 需求理解 → 方案设计 → 代码实现 → 代码审查 → Bug 修复，各阶段自动落盘到 `docs/` |
| 规范驱动编码 | [spec-driven-coding/](spec-driven-coding/) | 依据开发规范与公共库编码：需求分解 → 熟悉规范与公共库 → 实现 → shell_check 检查优化；规范与公共库知识库可自行填充 |
| 场景驱动方案设计 | [solution-design/](solution-design/) | 有旧代码/旧方案背景的深度方案设计：现状摸底 → 质询式需求识别（结构化模板）→ 升级/新开发判定 → 可追溯的方案产出 |
| 技能创建指南 | [skill-create/](skill-create/) | 创建新 Agent Skill 的方法论：结构约定、描述写法、常见反模式 |

## 开发流程闭环

五阶段路由（轻量默认 → 深度版按需升级）：

| 阶段 | 默认（轻量） | 深度版 |
|------|--------------|--------|
| 需求理解 | dev-workflow | solution-design Step 1-3（质询式 + 结构化需求模板） |
| 方案设计 | dev-workflow | solution-design（旧方案参考 + 升级/新开发判定） |
| 代码实现 | dev-workflow | spec-driven-coding（规范 + 公共库 + shell_check 门禁） |
| 代码审查 | dev-workflow（review-kit） | — |
| Bug 修复 | dev-workflow | — |

需要人工补充的留空项与刻意不做的边界，见各技能 README 的「留空待填充」「已知边界」小节。

## 使用方式

克隆后把需要的技能软链到 Agent 的技能目录，例如 Claude Code：

```bash
git clone https://github.com/<your-username>/my-skills.git
ln -s $(pwd)/my-skills/solution-design ~/.claude/skills/solution-design
```

## 目录约定

```
my-skills/
├── <skill-name>/
│   ├── SKILL.md            # 技能主文件（frontmatter + 流程）
│   ├── README.md           # 人类阅读的说明与维护指引
│   └── reference/          # 模板与知识库
└── licenses/               # 第三方来源的许可文件
```

## 第三方来源致谢

- [dev-workflow](dev-workflow/) 与 [skill-create](skill-create/) 源自 [xstongxue/best-skills](https://github.com/xstongxue/best-skills)（Apache 2.0，许可文本见 [licenses/APACHE-2.0.txt](licenses/APACHE-2.0.txt)）
- [solution-design](solution-design/) 的质询式访谈机制参考了 [mattpocock/skills](https://github.com/mattpocock/skills) 的 grilling / domain-modeling 思想（未复制其代码）
