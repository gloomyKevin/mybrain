# Claude 资产索引

> 这里列出 Claude 手里**所有** Obsidian 默认看不见的资产：`.claude/skills/`（vault 内 dotfile，Obsidian 不索引）和 `~/.claude/projects/-Users-admin-mybrain/memory/`（vault 外）。
>
> **维护规则**：Claude 对任一资产做增删改，必须同步更新本文件（见 memory `feedback_asset_index_sync`）。
>
> **点击打开**：链接会在系统默认 markdown 应用打开（通常是 VSCode / Claude Code），不是 Obsidian 内打开。如果点击没反应，说明 Obsidian 对该类链接的处理有限制，可以用下方路径手动打开。

---

## 一、Skills（`.claude/skills/`）

### 内容运营 / 自媒体

| 名称 | 一句话 | 打开 |
|---|---|---|
| lidan-writing-framework | 李诞七步写作框架，深度讲解型长文 / 知识普及的叙事结构 | [SKILL.md](../.claude/skills/lidan-writing-framework/SKILL.md) |
| humanizer-zh | 去 AI 味，编辑/审阅文本、去除 AI 生成痕迹 | [SKILL.md](../.claude/skills/humanizer-zh/SKILL.md) |

### 通用 / 技术辅助（Kepano Obsidian skills）

| 名称 | 一句话 | 打开 |
|---|---|---|
| defuddle | 从网页抽干净 markdown，省 token，替代 WebFetch | [SKILL.md](../.claude/skills/defuddle/SKILL.md) |
| json-canvas | 读写 `.canvas` 文件（Obsidian 白板） | [SKILL.md](../.claude/skills/json-canvas/SKILL.md) |
| obsidian-bases | 读写 `.base` 文件（Obsidian 数据视图） | [SKILL.md](../.claude/skills/obsidian-bases/SKILL.md) |
| obsidian-cli | 用 CLI 操作 vault（读写笔记、搜索、管理属性） | [SKILL.md](../.claude/skills/obsidian-cli/SKILL.md) |
| obsidian-markdown | 处理 Obsidian 专有 markdown 语法（wikilink / callout / frontmatter） | [SKILL.md](../.claude/skills/obsidian-markdown/SKILL.md) |

---

## 二、Memory（`~/.claude/projects/-Users-admin-mybrain/memory/`）

### 通用行为规则（feedback_）

| 名称                                | 一句话                         | 打开                                                                                                          |
| --------------------------------- | --------------------------- | ----------------------------------------------------------------------------------------------------------- |
| feedback_challenge_framing        | 主动挑战用户 framing，不要礼貌性顺着走     | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_challenge_framing.md)        |
| feedback_confirm_before_write     | 先对话给 draft，点头再 Write，不把讨论固化 | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_confirm_before_write.md)     |
| feedback_exploration_phase_memory | 摸索期不写长期定位式 memory           | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_exploration_phase_memory.md) |
| feedback_asset_index_sync         | 改 skill/memory 同步更新本索引      | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_asset_index_sync.md)         |
| feedback_auto_git_sync            | vault 改动自动 commit + push 到 origin/main | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/feedback_auto_git_sync.md)            |

### 项目上下文（project_）

| 名称                         | 一句话                                   | 打开                                                                                                   |
| -------------------------- | ------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| project_mybrain_lark_split | mybrain 是 OPC 内容生产 vault；4/24 硬约束发第一条 | [md](file:///Users/admin/.claude/projects/-Users-admin-mybrain/memory/project_mybrain_lark_split.md) |
|                            |                                       |                                                                                                      |

### 已删除（转移留档）

以下 memory 已删除。原内容保留在 git 历史里，对应归档文件在 `废案/2026-04-24-运营沉淀 v0.3/`：

- `project_content_methodology` — 必读 `运营-Claude 沉淀.md` §8 checklist
- `project_doulaoshi_baituo` — 豆老师小号人设档指针
- `project_content_topic_doc_engineering` — 第一条走 image2-prompt 结构拆解的方向决策
- `feedback_internalization_protocol` — 新材料内化协议 v1（待新 skill 清单后重写 v2）

