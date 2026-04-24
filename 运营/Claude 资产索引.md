# Claude 资产索引

> Claude 在本 vault 工作时可以调用或参考的**全部资产**的索引。不分"可见/不可见"（实现细节），按**功能 tier** 组织，对应我们的架构约定：Tier 0 永远生效 → Tier 1 情境触发 → Tier 2 按需加载 → Tier 3 内容资产。
>
> **维护规则**：任何资产增删改，我必须同步更新本文件（memory `feedback_asset_index_sync`）。同时按照 `feedback_auto_git_sync` 的规则判断是否 commit + push。

---

## Tier 0 · 约束（永远生效）

启动时已加载 / 硬引用，每次会话都在上下文里。

| 资产 | 说明 | 位置 |
|---|---|---|
| CLAUDE.md | 员工手册、硬约束、命名规范、禁止项 | [CLAUDE.md](../CLAUDE.md) |
| 自我.md | 自我画像（失败模式、动机、提示） | [自我.md](../自我.md) |
| OPC 规划.md | 6 个月路径 + 硬约束（4/24 第一条小红书等） | [OPC 规划.md](../OPC%20规划.md) |
| SOP.md | 操作流程手册（触发词 + 步骤） | [SOP.md](../SOP.md) |
| memory: project_mybrain_lark_split | 项目定位、git 远端 | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/project_mybrain_lark_split.md) |

## Tier 1 · 行为偏好（情境触发）

`feedback_` 类 memory，在相关情境下自动召回。

| 名称 | 一句话 | 打开 |
|---|---|---|
| feedback_challenge_framing | 主动挑战用户 framing，不要礼貌性顺着走 | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_challenge_framing.md) |
| feedback_confirm_before_write | 先对话给 draft，点头再 Write | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_confirm_before_write.md) |
| feedback_exploration_phase_memory | 摸索期不写长期定位式 memory | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_exploration_phase_memory.md) |
| feedback_asset_index_sync | 改 skill/memory 同步更新本索引 | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_asset_index_sync.md) |
| feedback_auto_git_sync | vault 改动自动 commit + push 到 origin/main | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_auto_git_sync.md) |

## Tier 2 · 工具（按需加载）

### 2a · 内容运营 skills（已激活，Claude Code 自动触发）

按抽象层归类。同层职责不重叠，跨层串行组合（结构 → 文字 → 审查）。

| 层 | skill | 一句话 | 打开 |
|---|---|---|---|
| 结构层 | lidan-writing-framework | 李诞七步框架，深度讲解型长文 / 知识普及 | [SKILL.md](../.claude/skills/lidan-writing-framework/SKILL.md) |
| 文字层 | humanizer-zh | 去 AI 味、文本净化 | [SKILL.md](../.claude/skills/humanizer-zh/SKILL.md) |
| 审查层 | _（空）_ | | |
| 平台层 | _（空）_ | 比如未来"小红书短句口语化" | |

### 2b · 通用辅助 skills（已激活）

| skill | 一句话 | 打开 |
|---|---|---|
| defuddle | 从网页抽干净 markdown，省 token，替代 WebFetch | [SKILL.md](../.claude/skills/defuddle/SKILL.md) |
| obsidian-markdown | 处理 Obsidian 专有 markdown 语法（wikilink/callout/frontmatter） | [SKILL.md](../.claude/skills/obsidian-markdown/SKILL.md) |
| obsidian-bases | 读写 `.base` 文件（Obsidian 数据视图） | [SKILL.md](../.claude/skills/obsidian-bases/SKILL.md) |
| obsidian-cli | 用 CLI 操作 vault | [SKILL.md](../.claude/skills/obsidian-cli/SKILL.md) |
| json-canvas | 读写 `.canvas` 文件（Obsidian 白板） | [SKILL.md](../.claude/skills/json-canvas/SKILL.md) |

### 2c · 候选仓库（未激活，暂存在 `.claude/sources/`，主仓库 .gitignored）

这些仓库里可能混有 skill / agent / tool，需要逐个调研后决定上架哪些。

| 仓库 | URL | 本地路径 | 类型 | 状态 | 上次拉取 |
|---|---|---|---|---|---|
| khazix-skills | https://github.com/KKKKhazix/khazix-skills | `.claude/sources/khazix-skills/` | 待确认 | 调研中 | 2026-04-24 |
| Viral_Writer_Skill | https://github.com/nashsu/Viral_Writer_Skill | 未拉取 | 推测 skill | 排队 | - |
| baoyu-skills | https://github.com/JimLiu/baoyu-skills | 未拉取 | 推测 skill | 排队 | - |
| erduo-skills | https://github.com/rookie-ricardo/erduo-skills | 未拉取 | 混合（skill/tool） | 排队 | - |

**调研流程**（每仓一个循环）：clone → Agent 侦察 → 给清单 → 用户挑 → 上架挑中的（复制到 `.claude/skills/` 并 commit）。未选中的留在 sources，将来需要时再用。

## Tier 3 · 内容资产（vault 目录，Claude 可读写）

| 目录 | 角色 |
|---|---|
| [收件箱.md](../收件箱.md) | 唯一捕获入口 |
| [素材库/](../素材库/) | 清洗后的外部参考（一文件一条） |
| [草稿/](../草稿/) | 正在写的内容 |
| [已发布/](../已发布/) | 发布存档 + 数据 |
| [废案/](../废案/) | 历史留档（不主动回看） |

核心流水线：`收件箱 → 素材库 → 草稿 → 已发布`。详见 `CLAUDE.md`。

---

## 废弃留档

### 已删除的 memory（留 git 历史）
- `project_content_methodology` — v0.3 沉淀前置 checklist
- `project_doulaoshi_baituo` — 豆老师人设指针
- `project_content_topic_doc_engineering` — 文档工程→image2-prompt 方向决策
- `feedback_internalization_protocol` — 新材料内化协议 v1（v0.3 配套）

### 已归档的 vault 文件
- `废案/2026-04-24-运营沉淀 v0.3/` — v0.3 `运营-Claude 沉淀.md` + 豆老师人设档
- `废案/` 下更早的文档工程方向 / image2-prompt 旧版等

---

## 维护约定

- **增删改任一 Tier 0/1/2 资产** → 本文件同步更新（feedback_asset_index_sync）
- **本文件改动** → 触发 commit + push 规则（feedback_auto_git_sync）
- **候选仓库调研**：一次一个，每个走"clone → 侦察 → 清单 → 挑选 → 上架"五步，不批量
- **上架即复制**：选中的 skill 从 `.claude/sources/<repo>/xxx/` **复制**到 `.claude/skills/<xxx>/`；两份独立，sources 可以整个删除不影响已上架
