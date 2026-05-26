# 状态说明（2026-05-26）

> 这份文件是旧版 Claude 资产索引，仍有参考价值，但当前入口已迁移到 `00-系统/资产索引.md`。
> 如果两份索引冲突，以 `00-系统/资产索引.md` 和 `00-系统/当前协议.md` 为准。

# Claude 资产索引

> Claude 在本 vault 工作时可以调用或参考的**全部资产**的索引。按**功能 tier** 组织：Tier 0 永远生效 → Tier 1 情境触发 → Tier 2 按需加载 → Tier 3 内容资产。
>
> Tier 2 内部按**业务目的**分层（选题 / 结构 / 文字 / 参考风格 / Prompt 备档 / 技术辅助），不按"可见性"或"触发机制"分——用户从业务视角查找。
>
> **维护规则**：任何资产增删改同步更新本文件（memory `feedback_asset_index_sync`），按 `feedback_auto_git_sync` 判断是否 commit + push。

---

## Tier 0 · 约束（永远生效）

启动时已加载，每次会话都在上下文里。

| 资产 | 说明 | 位置 |
|---|---|---|
| CLAUDE.md | 员工手册、硬约束、命名规范 | [CLAUDE.md](【需要更新，去掉硬约束】CLAUDE.md) |
| 自我.md | 自我画像（失败模式、动机、提示） | [自我.md](【一般，claude%20旧版】自我.md) |
| OPC 规划.md | 6 个月路径 + 硬约束 | [OPC 规划.md](【旧，但有价值】OPC%20规划.md) |
| SOP.md | 操作流程手册（触发词 + 步骤） | [SOP.md](【旧，ai早期写的】SOP.md) |
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

## Tier 2 · 工具与方法论（按需加载）

按**业务目的**分层。同层单一职责；跨层可串行组合（选题 → 结构 → 文字 → 参考风格校准）。

### 2a · 选题 / 研究（Content Discovery）

确定"写什么"之前的深度调研。

| 资产 | 一句话 | 触发 | 位置 |
|---|---|---|---|
| hv-analysis | 横纵分析深度研究 skill：联网信息收集 + 纵向时间线 + 横向竞品对比 → PDF 研究报告 | 自动 | [SKILL.md](../.claude/skills/hv-analysis/SKILL.md) |

> hv-analysis 依赖 Python + `weasyprint` + `markdown`，已装（`pip install --break-system-packages`）

### 2b · 内容结构（叙事骨架）

"怎么组织"文章的结构方法论。

| 资产 | 一句话 | 触发 | 位置 |
|---|---|---|---|
| lidan-writing-framework | 李诞七步框架：开场故事→矛盾→定义→历史→论证→应用→升华，深度讲解型长文叙事 | 自动 | [SKILL.md](../.claude/skills/lidan-writing-framework/SKILL.md) |

### 2c · 文字表达（活人感 / 净化）

写完后对文字层面的处理。

| 资产 | 一句话 | 触发 | 位置 |
|---|---|---|---|
| humanizer-zh | 去 AI 味：修掉夸大象征 / 宣传语 / 破折号过度 / 三段式 / 否定排比等 AI 痕迹 | 自动 | [SKILL.md](../.claude/skills/humanizer-zh/SKILL.md) |

### 2d · 参考风格（Reference Voices）

带人设 / 完整写作工作流的 skill。**默认不触发**，用户显式说"按 X 风格写"才启用；未来累积多个时，我会在开写前问"这次用谁"。

| 资产 | 人设 / 平台倾向 | 包含 | 位置 |
|---|---|---|---|
| khazix-writer | 卡兹克 / AI 博主 / 公众号长文 | HKR 选题质检 + 四层自检 + "讲人话"价值观 + AI 角色边界 | [SKILL.md](../.claude/skills/khazix-writer/SKILL.md) |

### 2e · Prompt 备档（显式引用，非 skill）

单次粘贴型 prompt，不进 Claude Code 自动触发系统，位置在 vault 内可直接搜索引用。需要时我主动读，或者你在对话里 @。

| 资产 | 一句话 | 位置 |
|---|---|---|
| 横纵分析法-卡兹克版.md | 轻量 Deep Research prompt，粘贴到任何 AI 对话 / Deep Research 里可用 | [md](横纵分析法-卡兹克版.md) |

### 2f · 技术辅助（开发环境）

Kepano 的 Obsidian skills + 网页抓取。和内容创作无直接关系，但处理 vault 文件 / 网页素材时会用。

| skill | 一句话 | 位置 |
|---|---|---|
| defuddle | 从网页抽干净 markdown，替代 WebFetch | [SKILL.md](../.claude/skills/defuddle/SKILL.md) |
| obsidian-markdown | 处理 Obsidian 专有 markdown 语法 | [SKILL.md](../.claude/skills/obsidian-markdown/SKILL.md) |
| obsidian-bases | 读写 `.base` 文件（Obsidian 数据视图） | [SKILL.md](../.claude/skills/obsidian-bases/SKILL.md) |
| obsidian-cli | 用 CLI 操作 vault | [SKILL.md](../.claude/skills/obsidian-cli/SKILL.md) |
| json-canvas | 读写 `.canvas` 文件 | [SKILL.md](../.claude/skills/json-canvas/SKILL.md) |

### 2h · 视频/动效制作（跨项目工具，全局安装）

非内容创作类业务工具：跨项目可用，装在 `~/.agents/skills/`（symlink → `~/.claude/skills/`）。

| 资产 | 一句话 | 触发 |
|---|---|---|
| hyperframes | 写 composition / 字幕 / 转场 / 音频反应动画的主笔 | 自动 |
| hyperframes-cli | dev loop：init / lint / preview / render / doctor | 自动 |
| hyperframes-media | TTS（Kokoro）/ 转录（Whisper）/ 背景去除（u2net） | 自动 |
| hyperframes-registry | 装第三方 block / 组件模板 | 自动 |
| gsap | GSAP 时间轴动画核心 | 自动 |
| lottie | Lottie / dotLottie 嵌入 | 自动 |
| three | Three.js / WebGL 三维场景 | 自动 |
| animejs | Anime.js 时间轴 | 自动 |
| css-animations | CSS keyframes 动画 | 自动 |
| waapi | Web Animations API | 自动 |
| tailwind | Tailwind v4 浏览器运行时 | 自动 |
| website-to-hyperframes | 网站抓取 → 视频管线 | 自动 |
| remotion-to-hyperframes | Remotion 项目迁移到 hyperframes | 自动 |

> 仓库源码备查：`~/research/hyperframes/`
> 能力卡：[[hyperframes 能力卡]]
> 安装：`npx skills add heygen-com/hyperframes -y -g`
> 卸载：删除 `~/.agents/skills/<skill-name>/`
> 第一个 demo：`~/research/hyperframes-demos/01-what-is-skill/`

### 2g · 候选仓库（未完全消化，暂存 `.claude/sources/`，主仓库 .gitignored）

原作者有独立版本源，不做二次版本化。选中上架的 skill 会**复制**到 `.claude/skills/` 一起 commit；sources 可整个删不影响已上架。

| 仓库 | URL | 类型 | 状态 | 上次拉取 |
|---|---|---|---|---|
| khazix-skills | https://github.com/KKKKhazix/khazix-skills | skill + prompt | ✅ 已调研 · 上架 2 skill + 1 prompt | 2026-04-24 |
| baoyu-skills | https://github.com/JimLiu/baoyu-skills | 工程仓库（21 skill：图文生成 / 发布 / 工具） | 📋 已调研 · 按需激活（详见 [调研/宝玉-skill仓库.md](宝玉-skill仓库.md)） | 2026-04-24 |
| Viral_Writer_Skill | https://github.com/nashsu/Viral_Writer_Skill | 推测 skill | 排队 | - |
| erduo-skills | https://github.com/rookie-ricardo/erduo-skills | 混合（skill/tool） | 排队 | - |

**调研流程**（每仓一个循环）：clone → 侦察 → 清单 → 挑选 → 上架挑中的。

## Tier 3 · 内容资产（vault 目录，Claude 可读写）

### 生产流水线

| 目录 | 角色 |
|---|---|
| [收件箱.md](【旧，考虑废弃】收件箱.md) | 唯一捕获入口 |
| [素材库/](../素材库/) | 经历 / 金句 / 外部参考（**原料**，未加工事实清单） |
| [选题库/](../选题库/) | 从素材提炼的创意 + 骨架 + 钩子（**半成品**，不抄素材细节，只指针引用） |
| [草稿/](../草稿/) | 正在写的具体内容 |
| [已发布/](../已发布/) | 发布存档 + 数据 |
| [废案/](../废案/) | 历史留档（不主动回看，但保留完整原文以便回看） |

**实际流水线**：`收件箱 → 素材库 → 选题库 → 草稿 → 已发布`

> CLAUDE.md 里的流水线图未包含"选题库/"（建于 2026-04-24），待用户决定是否更新 CLAUDE.md。当前以本索引为准。

### 行为锚点（非流水线，决策前参考）

| 资产 | 角色 |
|---|---|
| [原则.md](原则.md) | 跨选题的认知 / 立场 / 方法论。选题方向、素材入库、skill 激活、架构决策时**主动读**。Claude 仅在用户明确授权下新增条目 |
| [运营/](.) | 资产索引、prompt 备档、未来人设档 / 配方等 |

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

## 架构约定

- **增删改任一 Tier 0/1/2 资产** → 本文件同步更新（feedback_asset_index_sync）
- **本文件改动** → 触发 commit + push 规则（feedback_auto_git_sync）
- **2d 参考风格 skill 默认不触发**：Claude Code 虽然会自动识别这些 skill 的触发词，但对写稿场景我会优先用 2b 结构 + 2c 文字处理，只有用户显式说"按 X 风格"才调用 2d
- **多平台矩阵立场**：好东西的价值判断 ≠ 单平台适用性。skill 装进来是因为方法论本身有价值，下游到哪个平台分发是"用的时候剪裁"的问题
- **上架即复制**：选中的 skill 从 `.claude/sources/<repo>/xxx/` **复制**到 `.claude/skills/<xxx>/`；两份独立
- **候选仓库不进主仓库 git**：原作者有独立版本源，避免二次版本化和仓库膨胀
